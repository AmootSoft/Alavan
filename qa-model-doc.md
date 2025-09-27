# نحوه استفاده از API سامانه پرسش و پاسخ خودکار

این مدل برای **پاسخ کوتاه و دقیق به پرسش‌های کاربران بر پایه متن مرجع** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**, مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **context**, **متن مرجع** خود را وارد نمایید.

در قسمت **question**, **سوال** خود را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/QA' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "context": "متن مرجع",
  "question": "سوال"
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/Model/QA"
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}
data = {
    "context": "متن مرجع",
    "question": "سوال"
}

response = requests.post(url, headers=headers, json=data)

print("Status Code:", response.status_code)
print("Response:", response.json())
```

```javascript
const url = "https://service.alavan.co.ir/api/v1/Model/QA";

const headers = {
  "Content-Type": "application/json",
  "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
};

const body = JSON.stringify({
  context: "متن مرجع",
  question: "سوال"
});

fetch(url, {
  method: "POST",
  headers: headers,
  body: body
})
  .then(response => response.json())
  .then(data => {
    console.log("✅ QA Response:", data);
  })
  .catch(error => {
    console.error("❌ Error:", error);
  });
```

