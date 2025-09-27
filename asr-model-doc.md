# نحوه استفاده از API مدل تبدیل گفتار به نوشتار

این مدل برای **تبدیل صدا به متن فارسی یا انگلیسی** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**, مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **AudioFile**, **مسیر فایل صوتی** خود را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/ASR' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--form 'AudioFile=@"مسیر فایل صوتی"'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/Model/ASR"
headers = {
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}

file_path = "مسیر فایل صوتی"

with open(file_path, "rb") as audio:
    files = {"AudioFile": ("output.wav", audio, "audio/wav")}
    response = requests.post(url, headers=headers, files=files)

print("Status Code:", response.status_code)
print("Response:", response.text)
```

```javascript
const fetch = require("node-fetch");
const FormData = require("form-data");
const fs = require("fs");

const url = "https://service.alavan.co.ir/api/v1/Model/ASR";
const token = "Bearer توکن دریافتی از پرتال آلاوان";

// Replace with the path to your converted WAV file
const filePath = "مسیر فایل صوتی";

const form = new FormData();
form.append("AudioFile", fs.createReadStream(filePath));

fetch(url, {
  method: "POST",
  headers: {
    Authorization: token,
    ...form.getHeaders()
  },
  body: form
})
  .then(res => res.text())
  .then(data => console.log("✅ ASR Response:", data))
  .catch(err => console.error("❌ Error:", err));

```
