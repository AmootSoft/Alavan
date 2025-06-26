# نحوه استفاده از API مدل حذف اطلاعات شخصی از متن

این مدل برای **حذف کردن اطلاعات شخصی در متن فارسی** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **text**، **متن پیام** وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v3/Model/AnonymizeNames' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "text": "متن",
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v3/Model/AnonymizeNames"
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
const url = "https://service.alavan.co.ir/api/v3/Model/AnonymizeNames";

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