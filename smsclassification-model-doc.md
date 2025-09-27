# نحوه استفاده از API مدل اعتبارسنجی هوشمند پيام

این مدل برای **بررسی و ارزیابی هوشمند پیام‌های متنی از نظر تایید یا عدم تایید محتوا بر اساس متن و نوع خط** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**, مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **text**, **متن پیام** خود را وارد نمایید.

در قسمت **lineKind**, **نوع خط** را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v1/SmsValidation/SmsClassification' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "text": "متن پیام",
  "lineKind": "نوع خط"
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/SmsValidation/SmsClassification"
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}
data = {
    "text": "متن پیام",
    "lineKind": "نوع خط"
}

response = requests.post(url, headers=headers, json=data)

print("Status Code:", response.status_code)
print("Response:", response.text)

```

```javascript
const fetch = require("node-fetch");

const url = "https://service.alavan.co.ir/api/v1/SmsValidation/SmsClassification";
const token = "Bearer توکن دریافتی از پرتال آلاوان";

const body = {
  text: "متن پیام",
  lineKind: "نوع خط"
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
