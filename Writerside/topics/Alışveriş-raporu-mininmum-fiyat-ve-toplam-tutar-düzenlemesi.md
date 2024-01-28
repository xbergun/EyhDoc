# Alışveriş Raporu Minimum Fiyat ve Toplam Tutar Düzenlemesi

Alışveriş raporunun detay kısımları incelendiğinde “Ürün Adı”, “Miktar” ve “Tarih” alanlarının bulunduğu gözlemlenmektedir. Bu alanlara ek olarak ürünlerin fiyatları “Ürün Birim Fiyatı” şeklinde ve toplam alışveri tutarı “Toplam Fiyat” şeklinde rapora yansıtılabilir.

## API REFERENCE

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">xsrest/basket/read/shoppingHistory.xsjs?userId=10760</code-block>
    </tab>
</tabs>

### RESPONSE 

```json
{
  "PRODUCT_NAME": "string",
  "QUANTITY": "string",
  "CREATED_AT": "Datetime",
  "UNIT_PRICE": "int",
  "TOTAL_PRICE": "int"
}
```

### ÖRNEK RESPONSE
```json
{
  "PRODUCT_NAME": "Migros",
  "QUANTITY": "1726",
  "CREATED_AT": "2021-06-10T12:10:36.021Z",
  "UNIT_PRICE": 2,
  "TOTAL_PRICE": 3452
}
```