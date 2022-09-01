---
title: "2D platform game - Phần 1: Logic cơ bản"
last_modified_at: 2022-09-02
author: Tran-Thanh-Tung
author_profile: true
categories:
  - writing
tags:
  - game
  - pygame
---

Như đã nói ở bài viết về Pygame lần trước, mình là một người rất thích game. Mình vẫn còn nhớ
cảm giác mong chờ, thích thú hồi bé khi nhìn anh bạn nhà giàu hàng xóm chơi Mario, vẫn nhớ cảm
xúc vui sướng khi lần đầu được anh bạn đó cho chơi cùng. Có lẽ với một đứa trẻ chỉ quen với đồng quê thì game là một thứ vô cùng mới lạ, thú vị và niềm yêu thích chơi game bắt đầu từ đó.

Và có một điều đặc biệt đó là hầu hết các game mình chơi từ bé đến lớn đều có chung thể
loại 2D platform như: Mario, Contra, Ninja school,...và gần đây nhất là Dead Cells. Vì vậy
mình luôn có sự hứng thú với các game thể loại này. Nên mình đã quyết định viết một loạt
các bài viết hướng dẫn làm một game 2D platform vừa để thỏa mãn nhu cầu bản thân, vừa để gợi ý
thêm một chủ đề về project cho các bạn học viên.

Chém gió thế đủ rồi, chúng ta sẽ vào phần nội dung luôn nha.

## 1. Thiết kế game

Theo mình, thiết kế cơ bản của một game 2D platform bao gồm 3 phần chính:
- Main character: là nhân vật chính của game do người chơi điều khiển bao gồm các hành động
chính là di chuyển và nhảy
- Plartfrom: là mặt đất nơi mà nhân vật thực hiện các hành động
- Enemies: là kẻ thù của nhân vật chính, người chơi sẽ phải điều khiển nhân vật đánh bại các kẻ thù để qua mà chơi

Ngoài những thứ cơ bản trên, tựa game mà mình sẽ làm bao gồm thêm những thứ sau:
- Để tiêu diệt kẻ thù người chơi phải điều khiển nhân vật nhảy lên trên kẻ thù
- Thêm các vật phẩm người chơi có thể thu thập
- Thêm một hệ thống tính điểm mỗi khi người chơi tiêu diệt kẻ thù hoặc thu thập được các vật phẩm
trên

## 2. Tài nguyên sử dụng

- [Hình ảnh](https://pixelfrog-assets.itch.io/pixel-adventure-1)

- [Hiệu ứng âm thanh](https://jdwasabi.itch.io/8-bit-16-bit-sound-effects-pack)

- [Nhạc nền](https://timbeek.itch.io/royalty-free-music-pack)

- [Repo project](https://github.com/thanhtung1005/Pixel-Adventure-Pygame)

Game này mình có ý định phát triển lâu dài (trong lúc rảnh), khi có gì mới mình sẽ cập nhật và viết bài.
Các bạn có thể theo dõi trên repo cũng như trang web của MIMPython.

## 3. Cấu trúc thư mục

Sau khi đã lên ý tưởng cơ bản cho game, mình tạo một project với cấu trúc thư mục như sau:
```
2D-Platform-Game _____Code
                 \____Assets ____Image
                             \___Sound
```
Trong đó thư mục `Code` sẽ chứa các code của game. Thư mục `Image` chứa các hình ảnh của game,
`Sound` chứa âm thanh của game.

## 4. Khung game cơ bản

Sau bước chuẩn bị, ta sẽ bắt đầu với việc tạo bộ khung cơ bản cho game, hiểu đơn giản thì ở bước này
ta coi các đối tượng trong game là các hình khối đơn sắc và xử lý các tương tác vật lý giữa chúng.
Sau khi đã hoàn thiện một bộ khung chắc chắn, ta mới bắt đầu thêm hoạt ảnh cũng như âm thanh, hiệu ứng
để game trở nên thú vị.

### 4.1. Tile

Các bản đồ trong các trò chơi không phải là một ảnh được vẽ sẵn, mà được ghép
từ nhiều mảng nhỏ gọi là tile (thường có cỡ 16x16, 32x32 hoặc 64x64).
Tập hợp các tile theo một chủ đề gọi là tileset. Bằng cách tạo ra nhiều tileset với nhiều chủ đề khác
nhau người thiết kế game có thể dễ dàng tùy biến các bản đồ hoặc sinh ngẫu nhiên bản đồ từ các tileset
có sẵn như trong game Dead Cells (tựa game này khá hay, mọi người nên chơi thử).

Dưới đây là hình ảnh của tileset mình sẽ sử dụng cho trò chơi này

<div>
    <img src="/assets/images/post/2022-09-02-2DPlatformGame-Part1/tileset.png"
    style="width:80%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

Tạo class `Tile` trong thư mục `tiles.py`, vì mới chỉ tạo phần khung cho game
nên ta chưa sử dụng tileset bên trên mà chỉ tô màu các tile bằng màu có mã `#6E85B7`.

```py
# tiles.py
import pygame

class Tile(pygame.sprite.Sprite):

    def __init__(self, position, size):
        super().__init__()
        self.image = pygame.Surface(size)
        self.image.fill('#6E85B7')
        self.rect = self.image.get_rect(topleft=position)

```

### 4.2. Player

Tương tự như trên, tạo file `player.py` với class `Player`.
```py
# player.py
import pygame

class Player(pygame.sprite.Sprite):

    def __init__(self, position: tuple, size: tuple) -> None:
        super().__init__()
        self.image = pygame.Surface(size)
        self.image.fill('#F94892')
        self.rect = self.image.get_rect(topleft=position)

```

### 4.3. Level

Tạo class `Level` để mô tả một màn chơi.

```py
# level.py
import pygame

from player import Player
from tiles import Tile

class Level:

    def __init__(self, map: list, tileSize: tuple, playerSize: tuple) -> None:
        self.map = self.setupMap(map, tileSize, playerSize)

    def setupMap(self, map: list, tileSize: tuple, playerSize: tuple) -> None:
        self.tiles = pygame.sprite.Group()
        self.player = pygame.sprite.GroupSingle()

        for rowIndex, row in enumerate(map):
            for colIndex, tile in enumerate(row):

                if tile == 'X':
                    tilePosition = (colIndex * tileSize[0],
                                    rowIndex * tileSize[1])
                    tile = Tile(tilePosition, tileSize)
                    self.tiles.add(tile)

                if tile == 'P':
                    playerPosition = (colIndex * playerSize[0],
                                        rowIndex * playerSize[1])
                    player = Player(playerPosition, playerSize)
                    self.player.add(player)

    def update(self, screen) -> None:
        self.player.draw(screen)
        self.tiles.draw(screen)

```
Ý tưởng cơ bản của đoạn code trên chỉ đơn giản là tính tọa độ của từng tile và nhân vật sau đó vẽ
lên màn hình.

### 4.4. File thực thi

Tạo file `main.py` để chạy game với các đối tượng đã tạo.

```py
# main.py
import sys

import pygame

from level import Level

map = [
'              ',
'              ',
'              ',
' XX    XXX    ',
' XX P         ',
' XXXX         ',
' XXXX       XX',
' XX    X  XXXX',
'       X  XXXX',
' P  XXXX  XXXX',
'XXXXXXXX  XXXX']

tileSize = (64, 64)
playerSize = (32, 64)

screenWidth = len(map[0]) * tileSize[0]
screenHeight = len(map) * tileSize[1]

# Pygame setup
pygame.init()
screen = pygame.display.set_mode((screenWidth,screenHeight))
clock = pygame.time.Clock()
level = Level(map, tileSize, playerSize)

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

Và đây là kết quả

<div>
    <img src="/assets/images/post/2022-09-02-2DPlatformGame-Part1/setupLevel.png"
    style="width:80%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

Trong file `main.py` có một biến như sau:
```py
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
' P  XXXX  XXXX',
'XXXXXXXX  XXXX']
```

Đây là biến mô phỏng màn chơi này, các vị trí có ký tự `X` là các tile, `P` là vị
trí bắt đầu của người chơi, còn lại là các vị trí trống. Đây là một cách lưu dữ liệu một màn
chơi, tất nhiên về sau khi có nhiều đối tượng hơn trong một màn chơi ta sẽ phải chọn kiểu
dữ liệu phù hợp hơn để xử lý.

### 4.5. Chuyển động và điều khiển nhân vật

Nhân vật của chúng ta không thể cứ đứng yên mà cần chuyển động dựa trên tín hiệu truyền vào của người
chơi. Để thực hiện điều này, chỉnh sửa class `Player` như sau:

```py
import pygame

class Player(pygame.sprite.Sprite):

    def __init__(self, position: tuple, size: tuple) -> None:
        super().__init__()
        self.image = pygame.Surface(size)
        self.image.fill('#F94892')
        self.rect = self.image.get_rect(topleft=position)

        # Player movement
        self.direction = pygame.math.Vector2(0, 0)
        self.speed = 8
        self.gravity = 0.8
        self.jumpSpeed = -16

    def getEvent(self) -> None:
        # Get event
        keys = pygame.key.get_pressed()

        # Move event
        if keys[pygame.K_d]:
            self.direction.x = 1
        elif keys[pygame.K_a]:
            self.direction.x = -1
        else:
            self.direction.x = 0
        # Jump event
        if keys[pygame.K_w]:
            self.jump()

	def move(self) -> None:
        self.rect.x += self.direction.x * self.speed

    def jump(self) -> None:
        self.direction.y = self.jumpSpeed

    def applyGravity(self) -> None:
        self.direction.y += self.gravity
        self.rect.y += self.direction.y

    def update(self) -> None:
        self.getEvent()
        self.move()
        self.applyGravity()

        if self.rect.bottom >= 650:
            self.rect.bottom = 650

```

Ở đây mình đã thêm các thuộc tính sau cho nhân vật:
- `direction`: hướng di chuyển của nhân vật
- `speed`: tốc độ di chuyển của nhân vật
- `gravity`: trọng lực
- `jumpSpeed`: tốc độ nhảy của nhân vật

Và các hàm xử lý chuyển động và điều khiển nhân vật:
- `getEvent`: lấy tín hiệu đầu vào
- `move`: di chuyển nhân vật sang 2 bên
- `jump`: nhân vật nhảy
- `applyGravity`: áp dụng trọng lực vào nhân vật, hàm này sẽ liên tục được gọi
mỗi vòng lặp của game (cũng giống như việc chúng ta liên tục bị tác dụng bởi trọng
lực vậy).
- `update`: cập nhật trạng thái của nhân vật, trong hàm này có đoạn code

```py
if self.rect.bottom >= 650:
    self.rect.bottom = 650
```
đây là một giải pháp tạm thời được mình thêm vào để đảm bảo nhân vật không rơi ra khỏi màn hình.

Sau đó chỉnh sửa hàm `update` trong class `Level` như sau:
```py
def update(self, screen) -> None:
    self.tiles.draw(screen)
    self.player.update()
    self.player.draw(screen)
```

Kết quả khi chạy lại file `main.py`

<div>
    <img src="/assets/images/post/2022-09-02-2DPlatformGame-Part1/playerMovement.gif"
    style="width:80%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

### 4.6. Va chạm

Như vậy nhân vật của chúng ta đã có thể điều khiển nhân vật di chuyển, tuy nhiên vẫn chưa
có sự tương tác giữa nhân vật với các tile và ta cần xử lý điều đó.

Ý tưởng xử lý va chạm là khi nhân vật đang di chuyển mà va chạm với tile thì nhân
vật sẽ dừng lại tại đúng vị trí va chạm.
Mình sẽ sử dụng phương thức `colliderect` để thực hiện ý tưởng này.

Trong class `Level` thêm các hàm sau:

- Va chạm theo chiều ngang

```py
def horizontalMovementCollision(self) -> None:
    player = self.player.sprite
    player.move()

    for tile in self.tiles.sprites():
        if tile.rect.colliderect(player.rect):
            if player.direction.x == -1:
                player.rect.left = tile.rect.right
            elif player.direction.x == 1:
                player.rect.right = tile.rect.left
```

- Va chạm theo chiều dọc

```py
def verticalMovementCollision(self) -> None:
    player = self.player.sprite
    player.applyGravity()

    for tile in self.tiles.sprites():
        if tile.rect.colliderect(player.rect):
            if player.direction.y > 0:
                player.rect.bottom = tile.rect.top
                player.direction.y = 0
            elif player.direction.y < 0:
                player.rect.top = tile.rect.bottom
                player.direction.y = 0
```

Thay đổi các hàm update trong class `Player` và `Level` như sau:
- `Player`: bỏ những hàm không cần thiết và giải pháp tạm thời trong mục trước

```py
def update(self) -> None:
    self.getEvent()
```

- `Level`: thêm các hàm cần thiết

```py
def update(self, screen) -> None:
    self.tiles.draw(screen)
    self.player.update()
    self.horizontalMovementCollision()
    self.verticalMovementCollision()
    self.player.draw(screen)
```

Sau khi đã thực hiện các điều trên, thì đây là kết quả khi chạy lại file `main.py`

<div>
    <img src="/assets/images/post/2022-09-02-2DPlatformGame-Part1/collision.gif"
    style="width:80%;
    max-width:900px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding-top:20px;
    padding-bottom:20px;">
</div>

## 5. Lời kết

Vậy là mình đã hướng dẫn xong phần khung game cho các bạn, mong rằng các bạn cảm thấy thích
thú. Trong phần 2 mình sẽ hướng dẫn mọi người ghép hình ảnh cũng như animation vào game
nha. Hẹn gặp lại vào bài viết tiếp theo!

## 6. Tài liệu tham khảo

- [Pygame documentation](https://www.pygame.org/docs/)

- [DaFluffyPotato Youtube Channel](https://www.youtube.com/watch?v=xxRhvyZXd8I&list=PLX5fBCkxJmm3nAalPU6gGfRIFLlghRuYy)

- [Clear Code Youtube Channel](https://www.youtube.com/playlist?list=PL8ui5HK3oSiGXM2Pc2DahNu1xXBf7WQh-)

- [KidsCanCode Youtube Channel](https://www.youtube.com/playlist?list=PLsk-HSGFjnaG-BwZkuAOcVwWldfCLu1pq)
