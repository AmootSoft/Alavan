# نحوه استفاده از API مدل اصلاح علائم نگارشی

این مدل برای **اصلاح علائم نگارشی در متون فارسی به‌طور خودکار** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**, مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **text**, **متن پیام** خود را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v3/Model/Punctuation' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "text": "متن پیام"
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v3/Model/Punctuation"
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}

data = {
    "text": "متن پیام"
}

response = requests.post(url, headers=headers, json=data)

print("Status Code:", response.status_code)
print("Response:", response.text)
```

```javascript
const fetch = require("node-fetch");

const url = "https://service.alavan.co.ir/api/v3/Model/Punctuation";
const token = "Bearer توکن دریافتی از پرتال آلاوان";

const body = {
  text: "متن پیام"
};

fetch(url, {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    "Authorization": token
  },
  body: JSON.stringify(body)
})
  .then(res => res.json())
  .then(data => console.log("✅ Response:", data))
  .catch(err => console.error("❌ Error:", err));
```
