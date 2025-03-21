##  نحوه استفاده از مدل TTS آلاوان
* این سرویس به صورت post استفاده می شود
### endpoint
https://service.alavan.co.ir/api/v1/Model/TTS

# API درخواست TTS با استفاده از cURL

این دستور `curl` برای ارسال متن به سرویس TTS (تبدیل متن به صوت) استفاده می‌شود تا متن  موجود به فایل صوتی تبدیل شود.

## نحوه استفاده

### درخواست:
```markdown

```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/TTS' \
--header 'Token: توکن دریافتی از پرتال آلاوان' \
--header 'Content-Type: application/json' \
--data '{
  "text": "سلام وقت بخیر",
  "modelType": "piper_farid"
}'
```

### پارامترها:

- **Token**: توکن احراز هویت مورد نیاز برای دسترسی به API. این توکن باید در هدر درخواست ارسال شود.
  - مثال: `مقدار توکن دریافتی از پرتال آلاوان`

- **text**: متن دلخواه شما برای تبدیل به صوت
- **modelType**:  مدل تایپ صدا های متفاوت با جنسیت های متقاوت است

### نکات:

1. انواع model type
* piper_ahmad
* piper_farid
* piper_hanieh
* piper_mozhgan
* piper_hani

### پاسخ:

در صورتی که درخواست موفق باشد، سرور متن را به گفتار تبدیل می کند و یک فایل صوتی به صورت پاسخ بازمی‌گرداند.

### مثال استفاده:

```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/TTS' \
--header 'Token: توکن دریافتی از پرتال آلاوان' \
--header 'Content-Type: application/json' \
--data '{
  "text": "سلام وقت بخیر",
  "modelType": "piper_farid"
}'
```

در این مثال، متن سلام وقت بخیر برای پردازش TTS ارسال می‌شود.

  
### نمونه پاسخ:

```json
{
    "data": {
        "audioFileUrl": "/media/tts/output/audio_39hKJFD.wav"
    },
    "result": true,
    "message": "عملیات با موفقیت انجام شد"
}
```

در صورت موفقیت، پاسخ شامل وضعیت موفقیت و فایل صوتی  خواهد بود.

### خطاهای احتمالی:





