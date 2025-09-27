# نحوه استفاده از API مدل ترجمه چند زبانه

این مدل برای **ترجمه متون فارسی به زبان‌های مختلف و بالعکس** طراحی شده است.

---

این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **sourceLanguage**، **زبان مبدا برای ترجمه** را وارد نمایید.

در قسمت **text**، **متن پیام** را وارد نمایید.

در قسمت **destinationLanguage**، **زبان مقصد برای ترجمه** را وارد نمایید.

---

زبان های معتبر:

  Persian: "fa",         English: "en",         Arabic: "ar",          French: "fr",         German: "de",
  Spanish: "es",         Russian: "ru",         Turkish: "tr",         Italian: "it",        Chinese: "zh",
  Hindi: "hi",           Japanese: "ja",        Urdu: "ur",            Portuguese: "pt",     Korean: "ko",
  Dutch: "nl",           Greek: "el",           Romanian: "ro",        Ukrainian: "uk",      Polish: "pl",
  Azerbaijani: "az",     Pashto: "ps",          Kurdish: "ku",         Swedish: "sv",        Norwegian: "no",
  Danish: "da",          Finnish: "fi",         Hungarian: "hu",       Czech: "cs",          Slovak: "sk",
  Serbian: "sr",         Croatian: "hr",        Bulgarian: "bg",       Bosnian: "bs",        Albanian: "sq",
  Hebrew: "he",          Malay: "ms",           Indonesian: "id",      Thai: "th",           Vietnamese: "vi",
  Bengali: "bn",         Armenian: "hy",        Georgian: "ka",        Kazakh: "kk",         Uzbek: "uz",
  Nepali: "ne",          Marathi: "mr",         Malayalam: "ml",       Tamil: "ta",          Telugu: "te",
  Sinhala: "si",         Macedonian: "mk",      Slovenian: "sl",       Lithuanian: "lt",     Latvian: "lv",
  Estonian: "et",        Azerbaijani: "az",     Kurdish: "ku",         Swahili: "sw",        Somali: "so",
  Amharic: "am",         Hausa: "ha",           Yoruba: "yo",          Igbo: "ig",           Zulu: "zu",
  Afrikaans: "af",       Xhosa: "xh",           Malagasy: "mg",        Icelandic: "is",      Irish: "ga",
  ScottishGaelic: "gd",  Galician: "gl",        Catalan: "ca",         Breton: "br",         Luxembourgish: "lb",
  Basque: "eu",          Cebuano: "ceb",        Javanese: "jv",        Sundanese: "su",      Tagalog: "tl",
  HaitianCreole: "ht",   Oromo: "om",           Tigrinya: "ti",        Lingala: "ln",        Wolof: "wo",
  Lao: "lo",             Khmer: "km",           Burmese: "my",         Oriya: "or",          Gujarati: "gu",
  Punjabi: "pa",         Sindhi: "sd",          Kannada: "kn",         Telugu: "te",         Ganda: "lg",
  Tswana: "tn",          NorthernSotho: "ns",   Fulah: "ff",           Iloko: "ilo",         Bashkir: "ba",
  Belarusian: "be",      Asturian: "ast",       Occitan: "oc",         WesternFrisian: "fy", Yiddish: "yi"

---
    
```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/Translation' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "sourceLanguage": "زبان مبدا",
  "text": "متن",
  "destinationLanguage": "زبان مقصد"
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/Model/Translation"
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}
data = {
  "sourceLanguage": "زبان مبدا",
  "text": "متن",
  "destinationLanguage": "زبان مقصد"
}

response = requests.post(url, headers=headers, json=data)

print(response.status_code)
print(response.text)
```

```javascript
const url = "https://service.alavan.co.ir/api/v1/Model/Translation";

const headers = {
  "Content-Type": "application/json",
  "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
};

const body = JSON.stringify({
  sourceLanguage: "زبان مبدا",
  text: "متن",
  destinationLanguage: "زبان مقصد"
});

fetch(url, {
  method: "POST",
  headers: headers,
  body: body
})
  .then(response => response.json())
  .then(data => {
    console.log("✅ Response:", data);
  })
  .catch(error => {
    console.error("❌ Error:", error);
  });

```
