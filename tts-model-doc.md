# نحوه استفاده از API مدل تبدیل نوشتار به گفتار

این مدل برای تبدیل متن فارسی یا انگلیسی  به صدای طبیعی و روان طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در ورودی **text**، یک متن پیام وارد نمایید.

در قسمت **model type**، گوینده را وارد کنید.


گوینده ها:
---
piper_ahmad

piper_farid

piper_hanieh

piper_mozhgan

piper_hani


```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/TTS' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "text": "متن",
  "modelType": "گوینده"
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/Model/TTS"
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}
data = {
    "text": "متن",
    "modelType": "گوینده"
}

response = requests.post(url, headers=headers, json=data)

print(response.status_code)
print(response.text)


```

```javascript
const url = "https://service.alavan.co.ir/api/v1/Model/TTS";

const headers = {
  "Content-Type": "application/json",
  "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
};

const body = JSON.stringify({
  text: "متن",
  modelType: "گوینده"
});

fetch(url, {
  method: "POST",
  headers: headers,
  body: body
})
  .then(response => response.json())
  .then(data => {
    console.log("✅ TTS Response:", data);

    // If response contains a URL to audio, play it
    if (data.url) {
      const audio = new Audio(data.url);
      audio.play();
    } else {
      console.warn("⚠️ No audio URL in response.");
    }
  })
  .catch(error => {
    console.error("❌ Error:", error);
  });

```
