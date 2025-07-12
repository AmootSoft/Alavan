# نحوه استفاده از API مدل تشخیص سن

این مدل برای **شناسایی و تشخیص سن از طریق تصویر افراد** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **ImageFile**، **مسیر فایل تصویر** را وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v3/model/AgeDetection' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--form 'ImageFile=@"مسیر فایل تصویر"'
```

```python
import requests
import os

file_path = r"مسیر فایل تصویر"

if not os.path.exists(file_path):
    print("File does not exist:", file_path)
else:
    url = "https://service.alavan.co.ir/api/v3/model/AgeDetection"
    headers = {
        "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
    }

    with open(file_path, "rb") as f:
        files = {
            "ImageFile": ("filename.jpg", f, "image/jpeg")
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

fetch("https://service.alavan.co.ir/api/v3/model/AgeDetection", {
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
