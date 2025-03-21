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
```{'Terms': True, 'Lang': 'vi', 'Prefix': ['>', '?'], 'Message': None}```

# muốn lấy các dữ liệu trong danh sách thì dùng # 

```data.get("tên dữ liệu muốn lấy")```
# ví dụ
```python
du_lieu = data.get("Terms")
print("du_lieu")
```
# khi print du_lieu nó sẽ trả về True vì trong danh sách data đang để là true
có thể thay đổi dữ liệu in ra bằng cách vào
![bot.py](https://github.com/GauCandy/XKittyDev/blob/main/ima2ge.png)
sửa lại data ở đó thì du_lieu print ra sẽ khác
# Terms sử dụng như điều khoản của bot
sử dụng Terms như là một điều kiện để xem người dùng có sử dụng được lệnh hay ko
một số lệnh như help thì có thể bỏ qua điều kiện này

# không cần thêm dòng này vào vì ở đầu mã đã sử lí để loại trừ tin nhắn của bot được truyền vào trong rồi
```python
if message.author.bot:
        return
```

# data.get("Prefix") thì nó sẽ có 2 giá trị
- giá trị đầu tiên là prefix mặc định của bot
- giá trị thứ 2 là prefix custom kiểu thay đổi prefix cho máy chủ
- lí do có 2 giá trị ở đây là để sau khi thay đổi prefix cho máy chủ thì prefix cũ vẫn dùng đc

# data.get("Message") sẽ chứa tin nhắn của người dùng đã được sử lí
- giải thích đơn giản thông thường khi người dùng sử dụng lệnh ">say hi"
- nếu sử dụng message.content của thư viện discord thì ta sẽ nhận được dữ liệu ">say hi"a
nhưng nếu sử dụng data.get("message") thì dữ liệu thay vì nhận được ">say hi"
thì dữ liệu nhận lại sẽ là "hi" Remove ">say"(prefix kèm tên lệnh đã được loại bỏ)

# data.get("Lang") sử dụng để hỗ trợ nhiều ngôn ngữ
ở đây sử dụng thư viện lang_custom
chi tiết [Lang_Custom](https://github.com/GauCandy/Lang_Custom)
mục đích ở đây là để bot hỗ trợ nhiều ngôn ngữ hơn
