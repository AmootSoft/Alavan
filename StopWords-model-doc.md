# نحوه استفاده از API مدل حذف ایست واژه

این مدل برای **حذف ایست واژه در متون فارسی** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **text**، **متن پیام** را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v3/Model/StopWords' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "text": "متن",
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v3/Model/StopWords"
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
const url = "https://service.alavan.co.ir/api/v3/Model/StopWords";

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