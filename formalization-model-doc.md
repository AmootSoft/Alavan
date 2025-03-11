## نحوه استفاده از مدل Formalization آلاوان
### ساختار آدرس
ساختار آدرس به صورت زیر می‌باشد:

```Text
{BaseUrl}/api/v1/Model/Formalization
```

1 - این سرویس به صورت Post می باشد 

2 - در ورودی یک پارامتر متن پیام دریافت می کند

```json
{
  "text": "string"
}
```

و در header مقدار Token دریافتی از portal را وارد کنید

```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/Formalization' \
--header 'Token: توکن دریافتی از پرتال آلاوان' \
--header 'Content-Type: application/json' \
--data '{
  "text": "string"
}'
```

### نمونه پاسخ:

```json
{
    "data": {
        "output_text": "این یک پیام تست است."
    },
    "result": true,
    "message": "عملیات با موفقیت انجام شد"
}
```

