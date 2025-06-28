# نحوه استفاده از API مدل شناسایی و استخراج متن داخل تصویر

این مدل برای **تبدیل خودکار متون داخل تصویر، به فرمت دیجیتال قابل ویرایش** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **ImageFile**، **مسیر فایل تصویر** را وارد نمایید.

در قسمت **Language**، **زبان متن داخل تصویر** را وارد نمایید.

زبان معتبر، زبان **انگلیسی** **( en )** و زبان **فارسی** **( fa )** می باشد.


```bash
curl --location 'https://service.alavan.co.ir/api/v3/model/ocr' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--form 'ImageFile=@"مسیر فایل تصویر"' \
--form 'Language="زبان"'
```

```python
import requests
import os

file_path = r"مسیر فایل تصویر"

# Confirm the file exists before proceeding
if not os.path.exists(file_path):
    print("File does not exist:", file_path)
else:
    url = "https://service.alavan.co.ir/api/v3/model/ocr"
    headers = {
        "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
    }

    # Use binary mode and tuple for file
    with open(file_path, "rb") as f:
        files = {
            "ImageFile": ("filename.png", f, "image/png"),
            "Language": (None, "زبان")
        }

        response = requests.post(url, headers=headers, files=files)

        print(response.status_code)
        print(response.text)
```

```javascript
const fetch = require("node-fetch");
const FormData = require("form-data");
const fs = require("fs");

const form = new FormData();
form.append("ImageFile", fs.createReadStream("مسیر فایل تصویر"));
form.append("Language", "زبان"); 

fetch("https://service.alavan.co.ir/api/v3/model/ocr", {
  method: "POST",
  headers: {
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان",
    ...form.getHeaders()
  },
  body: form
})
  .then(res => res.text())
  .then(text => console.log("Response:", text))
  .catch(err => console.error("Error:", err));
```
