## نحوه استفاده از مدل QA آلاوان
### ساختار آدرس
ساختار آدرس به صورت زیر می‌باشد:

```Text
{BaseUrl}/api/v1/Model/QA
```

1 - این سرویس به صورت Post می باشد 

2 - در ورودی یک پارامتر متن پیام دریافت می کند

```json
{
  "context": "string",
  "question": "string"
}
```

و در header مقدار Token دریافتی از portal را وارد کنید

```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/QA' \
--header 'Token: توکن دریافتی از پرتال آلاوان' \
--header 'Content-Type: application/json' \
--data '{
  "context": "string",
  "question": "string"
}'
```

### نمونه پاسخ:

```json
{
    "data": {
        "answer": "پاسخ"
    },
    "result": true,
    "message": "عملیات با موفقیت انجام شد"
}
```

