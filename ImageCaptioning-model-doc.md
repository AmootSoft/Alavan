# نحوه استفاده از API مدل توصیف تصویر

این مدل برای **توصیف تصویر براساس محتوای آن** طراحی شده است.

---

این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **ImageFile**، **مسیر فایل تصویر** را وارد نمایید.

در قسمت **DoTranslate**، **زبان مورد نظر برای توصیف تصویر** را وارد نمایید.

زبان های معتبر **فارسی** (با مقدار **true**) و **انگلیسی** (با مقدار **false**) مشخص میشود.

```bash
curl --location 'https://service.alavan.co.ir/api/v3/Model/ImageCaptioning' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--form 'ImageFile=@"مسیر فایل تصویر"'\
--form 'DoTranslate=true'
```

```python
import requests
import os

file_path = r"مسیر فایل تصویر"

if not os.path.exists(file_path):
    print("File does not exist:", file_path)
else:
    url = "https://service.alavan.co.ir/api/v3/Model/ImageCaptioning"
    headers = {
        "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
    }

    with open(file_path, "rb") as f:
        files = {
            "ImageFile": ("image.jpg", f, "image/jpeg"),
        }
        data = {
            "DoTranslate": "true"
        }

        response = requests.post(url, headers=headers, files=files, data=data)

        print(response.status_code)
        print(response.text)
```

```javascript
import fetch from 'node-fetch';
import FormData from 'form-data';
import fs from 'fs';

const url = 'https://service.alavan.co.ir/api/v3/Model/ImageCaptioning';
const token = 'توکن دریافتی از پرتال آلاوان';
const imagePath = 'مسیر فایل تصویر';

const form = new FormData();
form.append('ImageFile', fs.createReadStream(imagePath));
form.append('DoTranslate', 'false');

fetch(url, {
  method: 'POST',
  headers: {
    'Authorization': `Bearer ${token}`,
    ...form.getHeaders()
  },
  body: form
})
.then(res => res.text())
.then(text => console.log(text))
.catch(err => console.error('Error:', err));
```