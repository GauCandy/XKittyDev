# XKittyDev
# giải thích ngắn gọn nhất tên file là tên lệnh

<tên file>.py

```python
import disnake

async def execute(message: disnake.Message, bot: disnake.Client, data: dict):
    # code sử lí ở đây
    # ví dụ lệnh này là say.py
    thì chỉ cần thêm mã sử lí để bot gửi lại những gì người dùng gửi
    await message.channel.send(message.content) # khi message.content chứa nội dung tin nhắn của người dùng
```
# trong data: dict khi 
```python
print(data)
```
# nó sẽ trả về một danh sách như sau
```{'Terms': True, 'Lang': 'vi', 'prefix': ['>', '?'], 'request': None}```

# muốn lấy các dữ liệu trong danh sách thì dùng # 

```data.get["tên dữ liệu muốn lấy"]```
# ví dụ
```python
du_lieu = data.get["Terms"]
print("du_lieu")
```
# khi print du_lieu nó sẽ trả về True vì trong danh sách data đang để là true
# có thể thay đổi dữ liệu in ra bằng cách vào
[bot.py](https://files.catbox.moe/fi59a8.png)
# sửa lại data ở đó thì du_lieu print ra sẽ khác
