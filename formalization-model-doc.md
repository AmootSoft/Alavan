# نحوه استفاده از API مدل تبدیل نوشتار محاوره‌ای به رسمی

این مدل برای تبدیل متون غیررسمی و محاوره‌ای به زبان رسمی طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در ورودی **text**, متن پیام را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/Formalization' \
--header 'Content-Type: application/json' \
--header 'Authorization: توکن خود راوارد کنید' \
--data '{
  "text": "متن"
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/Model/Formalization"

headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer توکن خود راوارد کنید"
}

data = {
    "text": "متن" # Replace this with your actual text
}

response = requests.post(url, headers=headers, json=data)

print("Status Code:", response.status_code)
print("Response Body:", response.text)

```

```javascript
const url = "https://service.alavan.co.ir/api/v1/Model/Formalization";

const headers = {
  "Content-Type": "application/json",
  "Authorization": "Bearer توکن خود را وارد کنید"
};

const body = JSON.stringify({
  text: "متن" // Replace this with your actual text
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
