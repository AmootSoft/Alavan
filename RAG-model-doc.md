# نحوه استفاده از API مدل پاسخگوی هوشمند مبتنی بر جستجو
  
این مدل برای **تولید پاسخ‌ های دقیق، مرتبط و مبتنی بر منبع اطلاعاتی متنی ارائه شده** طراحی شده است.

---

این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **documentID**، **آیدی دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **query**، **سوال خود** را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v1/Rag/Ask
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "ducumentId": آیدی دریافتی از پرتال آلاوان,
  "query": "سوال",
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/Rag/Ask"
headers = {
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان",
    "Content-Type": "application/json"
}

data = {
    "documentId": 123456789012345678,  # آیدی دریافتی از پرتال آلاوان
    "query": "چه سالی کارت ملی هوشمند جایگزین شد؟"
}

response = requests.post(url, headers=headers, json=data)

print("Status Code:", response.status_code)
print("Response:", response.json())

```

```javascript
const url = "https://service.alavan.co.ir/api/v1/Rag/Ask";
const token = "توکن_دریافتی_از_پرتال_آلاوان";

const data = {
  documentId: 123456789012345678,  // آیدی دریافتی از پرتال آلاوان
  query: "چه سالی کارت ملی هوشمند جایگزین شد؟"
};

fetch(url, {
  method: "POST",
  headers: {
    "Authorization": `Bearer ${token}`,
    "Content-Type": "application/json"
  },
  body: JSON.stringify(data)
})
.then(response => response.json())
.then(result => console.log("Response:", result))
.catch(error => console.error("Error:", error));

```
