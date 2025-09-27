# نحوه استفاده از API مدل تشخیص نوع احساس

این مدل برای تشخیص نوع احساس از جمله **شادی**، **ترس**، **تنفر**، **تعجب**، **ناراحتی** و **عصبانیت** در متن فارسی طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **text**، **متن پیام** را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/Emotion' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "text": "متن",
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/Model/Emotion"
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}
data = {
    "text": "متن",
}

response = requests.post(url, headers=headers, json=data)

print(response.status_code)
print(response.text)
```

```javascript
const url = "https://service.alavan.co.ir/api/v1/Model/Emotion";

const headers = {
  "Content-Type": "application/json",
  "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
};

const body = JSON.stringify({
  text: "متن"
});

fetch(url, {
  method: "POST",
  headers: headers,
  body: body
})
  .then(response => response.json())
  .then(data => {
    console.log("✅ Response:", data);
  })
  .catch(error => {
    console.error("❌ Error:", error);
  });

```
