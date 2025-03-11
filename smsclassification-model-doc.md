## نحوه استفاده از مدل Sms Classification آلاوان

### ساختار آدرس
ساختار آدرس به صورت زیر می‌باشد:

```Text
{BaseUrl}/api/v2/SmsValidation/SmsClassification
```

1 - این سرویس به صورت Post می باشد 

2 - در ورودی دو پارامتر متن پیام و نوع خط را با عناوین زیر دریافت می کند

3 - :
- **خدماتی**
  
- **خط اختصاصی**

- **خط تبلیغاتی**

- **خط خدماتی اختصاصی**

- **خط خدماتی عمومی**

- **خط عمومی**

- **خطوط ویژه**

```json
{
  "text": "string",
  "lineKind": "string"
}
```

و در header مقدار Token دریافتی از portal را وارد کنید

```bash
curl --location 'https://service.alavan.co.ir/api/v2/SmsValidation/SmsClassification' \
--header 'Token: توکن دریافتی از پرتال آلاوان' \
--header 'Content-Type: application/json' \
--data '{
  "text": "string",
  "lineKind": "خدماتی"
}'
```

### نمونه پاسخ:

```json
{
    "data": {
        "prediction": {
            "status": "0",
            "message": "تایید"
        }
    },
    "result": true,
    "message": "عملیات با موفقیت انجام شد"
}
```

