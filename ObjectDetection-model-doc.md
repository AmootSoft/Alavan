# نحوه استفاده از API مدل شناسایی اشیاء

این مدل برای **شناسایی و تشخیص اشیاء در تصویر** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **ImageFile**، **مسیر فایل تصویر** را وارد نمایید.

---

لیست **اشیاء قابل تشخیص** توسط مدل:


surfboard, microwave, umbrella, horse, sports ball, skateboard, scissors, giraffe
handbag, boat, sheep, stop sign, sandwich, tv, person, backpack, wine glass, chair,
banana, dog, cake, laptop, toothbrush, cup, elephant, spoon, book, clock, tie, cat,
potted plant, snowboard, traffic light, toaster, tennis racket, train, baseball bat,
airplane, dining table, keyboard, hot dog, fire hydrant, baseball glove, remote,
cell phone, orange, bear, fork, mouse, skis, kite, dining table, zebra, tv, cow, oven,
parking meter, motorcycle, clock, apple, bowl, bottle, bird, fridge, bus, frisbee,
bench, sink, suitcase, car, hair drier, donut, keyboard, bed, couch, knife, giraffe,
broccoli, remote, vase, umbrella, teddy bear, bicycle, carrot


```bash
curl --location 'https://service.alavan.co.ir/api/v1/model/ObjectDetection' \
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
    url = "https://service.alavan.co.ir/api/v1/model/ObjectDetection"
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

fetch("https://service.alavan.co.ir/api/v1/model/ObjectDetection", {
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

