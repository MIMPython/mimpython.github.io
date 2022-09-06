---
title: "2D platform game - Phần 2: Ghép hoạt ảnh cho nhân vật"
last_modified_at: 2022-09-06
author: Tran-Thanh-Tung
author_profile: true
categories:
  - writing
tags:
  - game
  - pygame
---

Xin chào mọi người! Mình đã trở lại với phần 2 của serie 2D platform game.
Trong phần này mình sẽ hướng dẫn các bạn thêm hoạt ảnh nhân vật vào bộ khung
game ta đã làm trong phần trước nha!

## 1. Chuẩn bị hình ảnh

Để tiện cho việc đọc các hình ảnh của nhân vật, mình tạo file `utils.py` với hàm
`getSurfaceList` như sau:

```py
import os

from pathlib import Path

import pygame

def getSurfaceList(path: Path) -> None:
    surfaceList = []

    for imageFilename in os.listdir(path):
        pathToImage = path / imageFilename
        surface = pygame.image.load(pathToImage).convert_alpha()
        surfaceList.append(surface)

    return surfaceList
```

Các hình ảnh mô tả một hành động của nhân vật sẽ được đánh số và được lưu vào
trong một thư mục. Ví dụ, nhân vật hiện tại có 7 hình ảnh mô tả hành động chạy,
cấu trúc thư mục chứa các hình ảnh này có dạng như sau:

```
run ____1.png
   |\___2.png
   |____3.png
   |____4.png
   |____5.png
   |____6.png
   |____7.png
```
Hàm `getSurfaceList` sẽ nhận vào đường dẫn đến thư mục `run` và chuyển tất cả
các file ảnh trong đó thành Surface và lưu vào một list.

## 2. Thêm hoạt ảnh cho nhân vật

Ý tưởng chính của việc này là ta vẽ liên tục các hình ảnh của nhân vật sao cho ăn khớp với
hoạt động (trạng thái) hiện tại của nhân vật.

Cụ thể, tại mỗi vòng lặp game ta thực hiện các công việc sau:
- Nhận tín hiệu đầu vào từ người chơi
- Cập nhật trạng thái của nhân vật
- Cập nhật hình ảnh phù hợp với trạng thái
- Cập nhật tọa độ của nhân vật
- Vẽ lại nhân vật với hình ảnh mới và tọa độ mới

Với những công việc trên mình thay đổi class `Player` như sau:

```python
from pathlib import Path

import pygame

from utils import getSurfaceList

class Player(pygame.sprite.Sprite):

    def __init__(self, position: tuple) -> None:
        super().__init__()

        # Player status
        self.status = 'idle'
        self.facingRight = True
        self.onGround = False

        # Player image
        self.getAnimations()
        self.frameIndex = 0
        self.animationSpeed = 0.25
        self.image = self.animations[self.status][self.frameIndex]
        self.rect = self.image.get_rect(topleft=position)
        self.hitbox = pygame.Rect(position, (40, 50))
        self.hitbox.midbottom = self.rect.midbottom

        # Player movement
        self.direction = pygame.math.Vector2(0, 0)
        self.speed = 5
        self.gravity = 0.8
        self.smoothSpeed = 0.4
        self.jumpSpeed = -16


    def getAnimations(self) -> None:
        currentDirPath = Path(__file__).absolute().parents[1]
        characterFolder = 'Assets/Image/MainCharacters/PinkMan'
        characterAnimationsPath = currentDirPath / characterFolder

        self.animations = {'idle':[], 'run':[], 'jump': [], 'fall': []}
        for animation in self.animations.keys():
            characterAnimationPath = characterAnimationsPath / animation
            self.animations[animation] = getSurfaceList(path=characterAnimationPath)

    def getEvent(self) -> None:
        # Get event
        keys = pygame.key.get_pressed()

        # Move event
        if keys[pygame.K_d]:
            self.direction.x = 1
            self.facingRight = True
        elif keys[pygame.K_a]:
            self.direction.x = -1
            self.facingRight = False
        else:
            self.direction.x = 0
        # Jump event
        if keys[pygame.K_w] and self.onGround:
            self.jump()

    def getStatus(self) -> None:
        if self.direction.y < 0:
            self.status = 'jump'
        elif self.direction.y > self.gravity:
            self.status = 'fall'
        else:
            if self.direction.x != 0:
                self.status = 'run'
            else:
                self.status = 'idle'

    def animate(self):
        animation = self.animations[self.status]

        self.frameIndex += self.animationSpeed
        if self.frameIndex >= len(animation):
            self.frameIndex = 0

        image = animation[int(self.frameIndex)]
        if self.facingRight:
            self.image = image
        else:
            self.image = pygame.transform.flip(surface=image,
                                               flip_x=True,
                                               flip_y=False)

    def move(self) -> None:
        self.rect.x += self.direction.x * self.speed
        self.hitbox.x += self.direction.x * self.speed

    def jump(self) -> None:
        self.direction.y = self.jumpSpeed

    def applyGravity(self) -> None:
        self.direction.y += self.gravity
        self.rect.y += self.direction.y
        self.hitbox.y += self.direction.y

    def update(self) -> None:
        self.getEvent()
        self.getStatus()
        self.animate()

```

Các thuộc tính mới:
- `animations`: lưu trữ tất cả các hình ảnh tương ứng với các hành động của nhân vật
- `frameIndex`: số thứ tự của hình ảnh hiện tại
- `image`: hình ảnh hiện tại của nhân vật
- `animationSpeed`: tốc độ chuyển hình ảnh của nhân vật
- `status`: trạng thái hiện tại của nhân vật
- `facingRight`: dùng để xác định có lật hình ảnh hay không? Vì khi nhân vật hoạt động bên
trái hoặc phải thì các hình ảnh là đối xứng nhau, nên ta chỉ lưu các hình ảnh ở một phía và
sử dụng tham số này để lật ảnh khi nhân vật hoạt động ở phía còn lại
- `onGround`: xác định xem nhân vật có đang ở trên mặt đất không? (giới hạn số lần nhảy
của nhân vật)
- `hitbox`: hitbox của nhân vật (dùng cho va chạm)

Các phương thức mới:
- `getAnimations`: lấy tất cả hoạt ảnh của nhân vật
- `getStatus`: cập nhật của nhân vật
- `animate`: cập nhật hình ảnh của nhân vật (được gọi tại mỗi vòng lặp game,
để cập nhật hình ảnh của nhân vật liên tục, từ đó tạo thành hoạt ảnh)

## 3. Một số thay đổi khác

Thay đổi class `Level` để hiện thị hình ảnh của nhân vật
```py
import pygame

from player import Player
from tiles import Tile

class Level:

    def __init__(self, map: list, tileSize: tuple) -> None:
        self.map = self.setupMap(map, tileSize)

    def setupMap(self, map: list, tileSize: tuple) -> None:
        self.tiles = pygame.sprite.Group()
        self.player = pygame.sprite.GroupSingle()

        for rowIndex, row in enumerate(map):
            for colIndex, tile in enumerate(row):
                position = (colIndex * tileSize[0], rowIndex * tileSize[1])
                if tile == 'X':
                    tile = Tile(position, tileSize)
                    self.tiles.add(tile)

                if tile == 'P':
                    player = Player(position)
                    self.player.add(player)

    def horizontalMovementCollision(self) -> None:
        player = self.player.sprite
        player.move()

        for tile in self.tiles.sprites():
            if tile.rect.colliderect(player.hitbox):
                if player.direction.x == -1:
                    player.hitbox.left = tile.rect.right
                elif player.direction.x == 1:
                    player.hitbox.right = tile.rect.left
                player.rect.midbottom = player.hitbox.midbottom

    def verticalMovementCollision(self) -> None:
        player = self.player.sprite
        player.applyGravity()

        for tile in self.tiles.sprites():
            if tile.rect.colliderect(player.hitbox):
                if player.direction.y > 0:
                    player.hitbox.bottom = tile.rect.top
                    player.direction.y = 0
                    player.onGround = True
                elif player.direction.y < 0:
                    player.hitbox.top = tile.rect.bottom
                    player.direction.y = 0
                player.rect.midbottom = player.hitbox.midbottom

        if (player.onGround and player.direction.y < 0) or player.direction.y > 1:
            player.onGround = False

    def update(self, screen) -> None:
        self.tiles.draw(screen)
        self.player.update()
        self.horizontalMovementCollision()
        self.verticalMovementCollision()
        self.player.draw(screen)
```

Thay đổi hàm thực thi
```py
import sys

import pygame

from level import Level


map = [
'              ',
'              ',
'              ',
' XX    XXX    ',
' XX           ',
' XXXX         ',
' XXXX       XX',
' XX    X  XXXX',
'       X  XXXX',
'  P XXXXXXXXXX',
'XXXXXXXXXXXXXX']

tileSize = (64, 64)

screenWidth = len(map[0]) * tileSize[0]
screenHeight = len(map) * tileSize[1]

# Pygame setup
pygame.init()
screen = pygame.display.set_mode((screenWidth,screenHeight))
clock = pygame.time.Clock()
level = Level(map, tileSize)

while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    screen.fill('black')
    level.update(screen)

    pygame.display.update()
    clock.tick(60)
```

Sau khi thực hiện thì đây là kết quả
<div>
    <img src="/assets/images/post/2022-09-06-2DPlatformGame-Part2/animationCharacter.gif"
    style="width:80%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

## 4. Lời kết

Như vậy, chúng ta đã xong phần 2, phần này có hơi khó hiểu vì mình không dành nhiều
thời gian để trau chuốt câu từ, mong các bạn thông cảm. Mình sẽ cố gắng diễn đạt tốt hơn
cho những phần sau, khi có nhiều thơi gian để làm hơn.

Code chi tiết các bạn có thể tham khảo tại [repository](https://github.com/thanhtung1005/Pixel-Adventure-Pygame).

## 5. Tài liệu tham khảo

- [Pygame documentation](https://www.pygame.org/docs/)

- [DaFluffyPotato Youtube Channel](https://www.youtube.com/watch?v=xxRhvyZXd8I&list=PLX5fBCkxJmm3nAalPU6gGfRIFLlghRuYy)

- [Clear Code Youtube Channel](https://www.youtube.com/playlist?list=PL8ui5HK3oSiGXM2Pc2DahNu1xXBf7WQh-)

- [KidsCanCode Youtube Channel](https://www.youtube.com/playlist?list=PLsk-HSGFjnaG-BwZkuAOcVwWldfCLu1pq)
