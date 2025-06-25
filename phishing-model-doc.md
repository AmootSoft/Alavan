# نحوه استفاده از API مدل پیش‌بینی دامنه‌های فیشینگ

این مدل برای **شناسایی دامنه‌های وب مشکوک به فیشینگ** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**, مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **url**, **آدرس دامنه** مد نظر خود را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v3/Phishing/CreateList' \
--header 'Content-Type: application/json' \
--header 'Authorization: توکن دریافتی از پرتال آلاوان' \
--data '{
  "url": "آدرس دامنه"
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v3/Phishing/CreateList"
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}

data = {
    "url": "آدرس دامنه"
}

response = requests.post(url, headers=headers, json=data)

print("Status Code:", response.status_code)
print("Response:", response.text)
```

```javascript
const fetch = require("node-fetch");

const url = "https://service.alavan.co.ir/api/v3/Phishing/CreateList";
const token = "Bearer توکن دریافتی از پرتال آلاوان";

const body = {
  url: "آدرس دامنه"
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
