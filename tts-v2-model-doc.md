# نحوه استفاده از API مدل تبدیل نوشتار به گفتار ورژن 2

مدل TTS-V2 برای تبدیل متن فارسی و انگلیسی به گفتار طبیعی طراحی شده است.  
در این نسخه، می‌توانید یک فایل صوتی به‌عنوان **Voice Reference** ارسال کنید تا مدل صدای خود شما را تقلید کند.  
اگر فایل ارسال نشود، مدل از صدای پیش‌فرض استفاده می‌کند.

---

## 🧪 نوع درخواست

**POST multipart/form-data**

---

## 🔐 احراز هویت

در هدر درخواست وارد کنید:

Authorization : Bearer  توکن دریافتی از پرتال آلاوان 


---

## 📥 پارامترهای ورودی


<table style="width:100%; background-color: #f4f4f4; border: 1px solid #ddd; border-collapse: collapse;">
  <thead>
    <tr>
      <th style="background-color: #2c3e50; color: white; padding: 10px;">نام فیلد</th>
      <th style="width:100%; background-color: #2c3e50; color: white; padding: 10px;">توضیح</th>
      <th style="background-color: #2c3e50; color: white; padding: 10px;">وضعیت</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">text</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">متن ورودی</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اجباری</td>
    </tr>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">VoiceReference</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">فایل صوتی رفرنس (mp3, wav, ogg, m4a)</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اختیاری</td>
    </tr>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">Preset</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">نوع تنظیمات صدا</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اجباری</td>
    </tr>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">Exaggeration</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">شدت بیان</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اختیاری</td>
    </tr>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">CfgWeight</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">وزن CFG</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اختیاری</td>
    </tr>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">Temperature</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">دمای مدل</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اختیاری</td>
    </tr>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">RepetitionPenalty</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">جلوگیری از تکرار</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اختیاری</td>
    </tr>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">MinP</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">حداقل احتمال</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اختیاری</td>
    </tr>
    <tr>
      <td style="background-color: #34495e; color: white; padding: 8px;">TopP</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">کنترل sampling</td>
      <td style="background-color: #34495e; color: white; padding: 8px;">اختیاری</td>
    </tr>
  </tbody>
</table>


Preset

- `1` → Custom  
- `2` → News  
- `3` → Story  
- `4` → Neutral  

اگر مقدار `Preset = Custom` باشد، پارامترهای تنظیم صدا باید ارسال شوند.

---

# 🌀 نمونه درخواست cURL (درست و تمیز + کامنت داخلی)

```bash
curl --request POST \
  --url 'https://service.alavan.ai/api/v1/Model/tts_v2' \
  --header 'Authorization: Bearer  توکن دریافتی از پرتال آلاوان' \
  --header 'Content-Type: multipart/form-data' \
  --form 'text=متن تست' \
  --form 'VoiceReference=@/path/to/voice-reference.mp3' \
  --form 'Preset=news' \
  --form 'Exaggeration=0.5' \
  --form 'CfgWeight=1.2' \
  --form 'Temperature=0.8' \
  --form 'RepetitionPenalty=1.1' \
  --form 'MinP=0.05' \
  --form 'TopP=0.9'

# VoiceReference: nullable - allowed: .wav .mp3 .ogg .m4a
# Preset values: Custom=1, News=2, Story=3, Neutral=4
# Other params are nullable

```


```python
import requests

url = "https://service.alavan.ai/api/v1/Model/tts_v2"

headers = {
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}

data = {
    "text": "متن تست",
    "Preset": "news",
    "Exaggeration": 0.5,
    "CfgWeight": 1.2,
    "Temperature": 0.8,
    "RepetitionPenalty": 1.1,
    "MinP": 0.05,
    "TopP": 0.9,
}

files = {
    "VoiceReference": open("voice-reference.mp3", "rb")  # optional
}

response = requests.post(url, headers=headers, data=data, files=files)

print(response.status_code)
print(response.text)

```

```javascript
const url = "https://service.alavan.ai/api/v1/Model/tts_v2";

async function callTtsApi(voiceFile) {
  const formData = new FormData();

  formData.append("text", "متن تست");
  formData.append("Preset", "news");
  formData.append("Exaggeration", "0.5");
  formData.append("CfgWeight", "1.2");
  formData.append("Temperature", "0.8");
  formData.append("RepetitionPenalty", "1.1");
  formData.append("MinP", "0.05");
  formData.append("TopP", "0.9");

  if (voiceFile) {
    formData.append("VoiceReference", voiceFile);
  }

  const response = await fetch(url, {
    method: "POST",
    headers: {
      "Authorization": "Bearer <TOKEN_FROM_ALAVAN_PORTAL>"
      // Content-Type را اضافه نکنید، مرورگر خودش تنظیم می‌کند
    },
    body: formData
  });

  const data = await response.json();
  console.log("TTS Response:", data);

  if (data.url) {
    new Audio(data.url).play();
  }
}
```
