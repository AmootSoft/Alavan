##  نحوه استفاده از مدل Phishing آلاوان
* این سرویس به صورت post استفاده می شود
### endpoint
https://service.alavan.co.ir/api/v1/Phishing/CreateList
```markdown
# API درخواست Phishing با استفاده از cURL

با استفاده از این api نسبت به لیست بلک لیست آلاوان و سیستم امتیاز بندی و یادگیری ماشین می توانیم پیش بینی کنیم دامنه آلوده است یا خیر .

## نحوه استفاده

### درخواست:

```bash
curl --location 'https://service.alavan.co.ir/api/v1/Phishing/CreateList' \
--header 'Token: توکن دریافتی از پرتال آلاوان' \
--header 'Content-Type: application/json' \
--data '{
  "url": "دامنه مدنظر"
}'
```

### پارامترها:

- **url**: دامنه مدنظر 
- حتما باید از http یا https استفاده شود


### نکات:

1. امتیاز هرچی به 180 نزدیکتر باشد دامنه مورد تایید است و اگر از بازه 100 به پایین و نزدیک به 0 باشد دامنه احتمال فیشینگ دارد


### پاسخ:

در صورتی که درخواست موفق باشد، سرور پارامتر های امتیاز بندی را نشان میدهد و اگر دامنه داخل لیست سیاه یا غیرفعال باشد امتیاز 0 باز می گردد.

### مثال استفاده:

```bash
curl --location 'https://service.alavan.co.ir/api/v1/Phishing/CreateList' \
--header 'Token: توکن دریافتی از پرتال آلاوان' \
--header 'Content-Type: application/json' \
--data '{
  "url": "دامنه مدنظر"
}'
```

در این مثال، متن سلام وقت بخیر برای پردازش TTS ارسال می‌شود.

  
### نمونه پاسخ:

```json
{
  "data": {
    "id": 48,
    "url": "http://aminimawwtini.com",
    "isActive": false,
    "score": 0,
    "haveEnamad": false,
    "haveSsl": false,
    "isHttps": false,
    "clientRedirect": false,
    "serverRedirect": false,
    "changedUrl": null,
    "googleSafe": false,
    "domainRegistration": "N/A",
    "domainInformation": "N/A",
    "ipAddress": "N/A",
    "reverseDns": "N/A",
    "asn": "N/A",
    "serverLocation": "N/A",
    "latitudeLongitude": "N/A",
    "city": "N/A",
    "region": "N/A",
    "isBlacklisted": true,
    "modelPredict": "the domain is in the Alavan Blacklist"
  },
  "result": true,
  "message": "عملیات با موفقیت انجام شد"
}
```

---

##  نحوه استفاده از لیست سیاه آلاوان
* این سرویس به صورت get استفاده می شود
### endpoint
https://service.alavan.co.ir/api/v1/Phishing/GetBlackList


### پارامترها:

- **Token**: توکن دریافتی از پرتال آلاوان

```bash
curl --location 'https://service.alavan.co.ir/api/v1/Phishing/GetBlackList' \
--header 'Token: توکن دریافتی از پرتال آلاوان'
```

### پاسخ
```json
{
    "data": [
        {
            "url": "https://foodaneeet.com"
        },
        {
            "url": "https://foodaneeeeet.com"
        },
        {
            "url": "https://foodaneeeeییet.com"
        }
    ],
    "result": true,
    "message": ""
}
```
---
##  نحوه اضافه کردن به لیست سیاه آلاوان
* این سرویس به صورت POST استفاده می شود
### endpoint
https://service.alavan.co.ir/api/v1/Phishing/CreateInBlackList


### پارامترها:

- **Token**: توکن دریافتی از پرتال آلاوان
- **url**: دامنه مدنظر 
- حتما باید از http یا https استفاده شود


```bash
curl --location 'https://service.alavan.co.ir/api/v1/Phishing/CreateInBlackList' \
--header 'Token: توکن دریافتی از پرتال آلاوان' \
--header 'Content-Type: application/json' \
--data '{
  "url": "http://portal.alavan.co.ir"
}'
```

### پاسخ
```json
{
    "data": {
        "url": "http://portal.alavan.co.ir"
    },
    "result": true,
    "message": "عملیات با موفقیت انجام شد"
}
```
---
##  نحوه حذف کردن از لیست سیاه آلاوان
* این سرویس به صورت DELETE
* 
* استفاده می شود
### endpoint
https://service.alavan.co.ir/api/v1/Phishing/DeleteFromBlackList


### پارامترها:

- **Token**: توکن دریافتی از پرتال آلاوان
- **url**: دامنه مدنظر 
- حتما باید از http یا https استفاده شود


```bash
curl --location --request DELETE 'https://service.alavan.co.ir/api/v1/Phishing/DeleteFromBlackList' \
--header 'Token: توکن دریافتی از پرتال آلاوان' \
--header 'Content-Type: application/json' \
--data '{
  "url": "http://portal.alavan.co.ir"
}'
```

### پاسخ
```json
{
"data": null,
"result": true,
"message": "عملیات با موفقیت انجام شد"
}
```