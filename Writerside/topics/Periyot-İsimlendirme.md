# Periyot İsimlendirme

“Periyot Yönetimi” sayfasında yeni bir periyod oluşturulacağı zaman periyot üzerinde bir isimlendirme yapılabilmelidir.

## API REFERENCE

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/period/read/period.xsjs</code-block>
    </tab>
</tabs>

## Açıklama
Period tablosuna, "PERIOD_NAME" adında String türünde field eklenmiştir.

## Request Body
```json

{
  "ID": "2024",
  "START_DATE": "2023-05-31T21:00:00.000Z",
  "END_DATE": "2023-06-29T21:00:00.000Z",
  "CHECK_UP_BUDGET": 0,
  "CHECK_UP_GRADE_TO": 16,
  "CHECK_UP_BUDGET_SECOND": 5000,
  "CHECK_UP_GRADE_FROM": 17,
  "FIXED_BUDGET": 7000,
  "FIXED_BUDGET_GRADE_TO": 16,
  "FIXED_BUDGET_SECOND": 4000,
  "FIXED_BUDGET_GRADE_FROM": 17,
  "PERIOD_NAME" : "2024 PERİODU"
}

```

### RESPONSE

```json
{
  "ID": "String",
  "START_DATE": "String",
  "END_DATE": "String",
  "CREATED_BY": "String",
  "CREATED_AT": "String",
  "CHECK_UP_BUDGET": "String",
  "CHECK_UP_GRADE_TO": "String",
  "CHECK_UP_BUDGET_SECOND": "String",
  "CHECK_UP_GRADE_FROM": "String",
  "FIXED_BUDGET": "String",
  "FIXED_BUDGET_GRADE_TO": "String",
  "FIXED_BUDGET_SECOND": "String",
  "PERIOD_NAME": "String",
  "FIXED_BUDGET_GRADE_FROM": "String",
  "IS_ACTIVE": "String"
}
```

### ÖRNEK RESPONSE
```json
{
  "ID": "2020",
  "START_DATE": "2020-08-03T21:00:00.000Z",
  "END_DATE": "2020-08-24T21:00:00.000Z",
  "CREATED_BY": "00022917",
  "CREATED_AT": "2020-07-03T16:03:51.064Z",
  "CHECK_UP_BUDGET": "0",
  "CHECK_UP_GRADE_TO": "7",
  "CHECK_UP_BUDGET_SECOND": "1794",
  "CHECK_UP_GRADE_FROM": "8",
  "FIXED_BUDGET": "950",
  "FIXED_BUDGET_GRADE_TO": "7",
  "FIXED_BUDGET_SECOND": "450",
  "PERIOD_NAME": "2020 PERİODU",
  "FIXED_BUDGET_GRADE_FROM": "8",
  "IS_ACTIVE": null
}
```