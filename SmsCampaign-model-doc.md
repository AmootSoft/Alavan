# نحوه استفاده از API مدل مدیر کمپین

این مدل برای **ساخت کمپین پیامکی برای کاربران تمام حوزه ها** طراحی شده است.

---


این سرویس به صورت **Post** می باشد.

در قسمت **Authorization**، مقدار **توکن دریافتی از پرتال آلاوان** را وارد نمایید.

در قسمت **business_area**، **زمینه فعالیت** خود را وارد نمایید.

در قسمت **campaign_goal**، **هدف کمپین** خود را وارد نمایید.

در قسمت **total_budget_toman**، **بودجه** خود را به **تومان** وارد نمایید.


```bash
curl --location 'https://service.alavan.co.ir/api/v1/Model/SmsCampaign' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer توکن دریافتی از پرتال آلاوان' \
--data '{
  "business_area": "زمینه فعالیت",
  "campaign_goal": "هدف کمپین",
  "total_budget_toman": 0
}'
```

```python
import requests

url = "https://service.alavan.co.ir/api/v1/Model/SmsCampaign"
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
}
data = {
    "business_area": "زمینه فعالیت",
    "campaign_goal": "هدف کمپین",
    "total_budget_toman": 0
}

response = requests.post(url, headers=headers, json=data)

print(response.status_code)
print(response.text)
```

```javascript
const url = "https://service.alavan.co.ir/api/v1/Model/SmsCampaign";

const headers = {
  "Content-Type": "application/json",
  "Authorization": "Bearer توکن دریافتی از پرتال آلاوان"
};

const body = JSON.stringify({
  business_area: "زمینه فعالیت",
  campaign_goal: "هدف کمپین",
  total_budget_toman: 0
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
