# نحوه استفاده از API مدل شناسایی و استخراج متون داخل تصویر

این مدل برای تبدیل خودکار متن‌های داخل تصویر به فرمت دیجیتال قابل ویرایش طراحی شده است.

---


این سرویس به صورت **Post** می باشد:

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

مسیر فایل تصویر را وارد کنید.

زبان متن داخل تصویر را انتخاب کنید.

زبان معتبر ، زبان انگلیسی ( en ) و زبان فارسی ( fa ) است.


```bash
curl --location 'https://service.alavan.co.ir/api/v3/model/ocr' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--form 'ImageFile=@"مسیر فایل تصویر"' \
--form 'Language="fa"'
```

```python
import requests
import os

file_path = r"مسیر فایل عکس"

# Confirm the file exists before proceeding
if not os.path.exists(file_path):
    print("File does not exist:", file_path)
else:
    url = "https://service.alavan.co.ir/api/v3/model/ocr"
    headers = {
        "Authorization": "Bearer توکن خود راوارد کنید"
    }

    # Use binary mode and tuple for file
    with open(file_path, "rb") as f:
        files = {
            "ImageFile": ("filename.png", f, "image/png"),
            "Language": (None, "en") # "fa" / "en" زبان متن داخل تصویر را انتخاب کنید
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
form.append("ImageFile", fs.createReadStream("مسیر فایل عکس"));
form.append("Language", "en"); // "fa" / "en" زبان متن داخل تصویر را انتخاب کنید

fetch("https://service.alavan.co.ir/api/v3/model/ocr", {
  method: "POST",
  headers: {
    "Authorization": "Bearer توکن خود را وارد کنید"
    ...form.getHeaders()
  },
  body: form
})
  .then(res => res.text())
  .then(text => console.log("Response:", text))
  .catch(err => console.error("Error:", err));
```
