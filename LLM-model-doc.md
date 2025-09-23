
# نحوه استفاده از API مدل زبانی بزرگ
  
این مدل برای **تولید پاسخ‌ های دقیق، مرتبط و مبتنی بر فایل متنی ارائه شده** طراحی شده است.

---

این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **promptId**، **آیدی دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **userPrompt**، **متن مورد نیاز خود** را وارد نمایید.

در قسمت **reasoning**، **میزان توضیح مورد نیاز** را بر اساس لیست زیر وارد نمایید.

off, low, medium, high
```bash
curl --location 'https://service.alavan.co.ir/api/v1/LLM/Run
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "promptId": آیدی دریافتی از پرتال آلاوان,
  "userPrompt": "متن مورد نیاز خود",
  "reasoning": "میزان توضیح"
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/LLM/Run"
headers = {
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان",
    "Content-Type": "application/json"
}

data = {
    "promptId": 123456789012345678,  # آیدی دریافتی از پرتال آلاوان
    "userPrompt": "چه سالی کارت ملی هوشمند جایگزین شد؟",
    "reasoning": "off"
}

response = requests.post(url, headers=headers, json=data)

print("Status Code:", response.status_code)
print("Response:", response.json())

```

```javascript
const url = "https://service.alavan.co.ir/api/v1/LLM/Run";
const token = "توکن_دریافتی_از_پرتال_آلاوان";

const data = {
  promptId: 123456789012345678,  // آیدی دریافتی از پرتال آلاوان
  userPrompt: "چه سالی کارت ملی هوشمند جایگزین شد؟",
  reasoning: "off"
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

