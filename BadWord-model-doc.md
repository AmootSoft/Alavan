# نحوه استفاده از API مدل BadWord (تایید اتوماتیک محتوا)

مدل **BadWord** برای بررسی متن ورودی و تشخیص وجود/عدم وجود کلمات نامناسب استفاده می‌شود.  
خروجی این مدل به‌صورت **true/false** برمی‌گردد.

---

## 🧪 نوع درخواست

**POST application/json**

---

## 🔐 احراز هویت

در هدر درخواست وارد کنید:

Authorization : Bearer  توکن دریافتی از پرتال آلاوان

---

## ✅ شرایط و محدودیت‌ها (Validation)

- `Text` نباید `null` باشد  
- طول `Text` باید کمتر از `500` کاراکتر باشد

---

## 📥 پارامترهای ورودی

<table style="width:100%; background-color: #f4f4f4; border: 1px solid #ddd; border-collapse: collapse;">
  <thead>
    <tr>
      <th style="background-color: #2c3e50; color: white; padding: 10px;">نام فیلد</th>
      <th style="width:100%; background-color: #2c3e50; color: white; padding: 10px;">توضیح</th>
      <th style="background-color: #2c3e50; color: white; padding: 10px;">وضعیت</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">Text</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">متن ورودی جهت بررسی</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اجباری</td>
    </tr>
  </tbody>
</table>

---

## 🌀 نمونه درخواست cURL

```bash
curl --request POST \
  --url 'https://service.alavan.ai/api/v1/Model/BadWord' \
  --header 'Authorization: Bearer AlavanToken' \
  --header 'Content-Type: application/json' \
  --header 'accept: */*' \
  --data '{ "Text": "تست" }'

# Text: required (not null), length < 500
```

```python
import requests

url = "https://service.alavan.ai/api/v1/Model/BadWord"

headers = {
    "Authorization": "Bearer AlavanToken",
    "Content-Type": "application/json",
    "accept": "*/*"
}

payload = {
    "Text": "تست"
}

response = requests.post(url, headers=headers, json=payload)

print(response.status_code)
print(response.text)
```


```javascript
const url = "https://service.alavan.ai/api/v1/Model/BadWord";

async function callBadWordApi(text) {
  const response = await fetch(url, {
    method: "POST",
    headers: {
      "Authorization": "Bearer AlavanToken",
      "Content-Type": "application/json",
      "accept": "*/*"
    },
    body: JSON.stringify({ Text: text })
  });

  const data = await response.json();
  console.log("BadWord Response:", data);

  // نتیجه مدل:
  // data.data.modelOutput === true  => contains bad word
  // data.data.modelOutput === false => clean
  return data;
}

// Example:
callBadWordApi("تست");
```


