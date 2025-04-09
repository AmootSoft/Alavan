## نحوه استفاده از مدل OCR آلاوان

### ساختار آدرس
ساختار آدرس به صورت زیر می‌باشد:

```Text
{BaseUrl}/api/v1/model/ocr
```


1 - این سرویس به صورت Post می باشد 

2 - در ورودی دو پارامتر فایل تصویر و نوع زبان را با عناوین زیر دریافت می کند

3 - زبان معتبر ، زبان انگلیسی ( en ) و زبان فارسی ( fa ) است 
```json

{
  "ImageFile" : byte[] , 
  "Language" : string // fa , en
}

```

و در header مقدار Token دریافتی از portal را وارد کنید

```bash
curl --location 'https://service.alavan.co.ir/api/v1/model/ocr/' \
--header 'Token: مقدار توکن دریافتی از پرتال آلاوان' \
--form 'ImageFile=@"مسیر فایل عکس"' \
--form 'Language="fas"'
```
