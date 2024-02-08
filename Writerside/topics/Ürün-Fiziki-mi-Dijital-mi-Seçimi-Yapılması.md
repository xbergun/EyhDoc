# Ürün Fiziki mi Dijital mi Seçimi Yapılması

Ürün eklenirken ve ya düzenlenirken ürünün dijital kart mı yoksa fiziksel bir ürün mü olduğunun seçilebilmesi talep edildi. Yine bu ürünün dijital kart mı yoksa fiziksel kart mı olduğunu belirtebileceğimiz bir buton ekleyebiliriz.


## Açıklama
Product tablosuna, "IS_DIGITAL" adında Boolean bir field eklenmiştir.
- IS_DIGITAL: 1 => Ürün Dijital
- IS_DIGITAL: 0 => Ürün Fiziksel
Olarak temsil edilir.


# GET

### 1.YOL
Tüm ürünleri çekip, IS_DIGITAL alanı 1 yada 0 olanları filtreleyebilirsiniz.
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/read/product.xsjs</code-block>
    </tab>
</tabs>

### 2.YOL
Parametre olarak sadece yenilik ürünlerini çekebilirsiniz..
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/read/product.xsjs?isDigital=true</code-block>
    </tab>
</tabs>


### RESPONSE

```json
{
  "ID": "string",
  "SUBCATEGORY_ID": "string",
  "CREATED_AT": "Datetime",
  "CREATED_BY": "string",
  "GRADE_FROM": "string",
  "GRADE_TO": "string",
  "PICTURE": "NCLOB",
  "PDF": "NCLOB",
  "PRICE": "string",
  "IS_ACTIVE": "int",
  "IS_DIGITAL": "int",
  "IS_INNOVATION": "int",
  "TEXT": "string",
  "DESCRIPTION": "string"
}
```

### ÖRNEK RESPONSE
```json
{
  "ID": "1086",
  "SUBCATEGORY_ID": "1027",
  "CREATED_AT": "2021-06-07T13:36:50.151Z",
  "CREATED_BY": "00022917",
  "GRADE_FROM": "1",
  "GRADE_TO": "20",
  "PICTURE": "a101.png",
  "PDF": "EsnekYanHaklar_A101n.pdf",
  "PRICE": "1",
  "IS_ACTIVE": 1,
  "IS_DIGITAL": 1,
  "IS_INNOVATION": 0,
  "TEXT": "A101",
  "DESCRIPTION": "* Parçalı kullanım yapılabilir.\n* Online alışverişlerde geçerli değildir.\n* Kullanım süresi 1 yıldır.\n\nDaha fazla detay için butona tıkla!"
}
```

# POST

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/create/product.xsjs</code-block>
    </tab>
</tabs>

### POST REQUEST

IS_DIGITAL değeri yollanmazsa, otomatik olarak 0 atanır.

```json
{
  "GRADE_FROM": 1,
  "GRADE_TO": 11,
  "PICTURE": "mediamarkt10.png",
  "PDF": "intermed-goz-muayenesi-ileri-tetkik10.pdf",
  "PRICE": 20,
  "PRODUCT_NAME": "denedmee",
  "DESCRIPTION": "ksdadskads",
  "SUBCATEGORY_ID": 1027,
  "IS_DIGITAL": true
}
```
### POST RESPONSE

```json
{
 "Response" : "31100 - Successfully created"
}
```

# UPDATE

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/update/product.xsjs</code-block>
    </tab>
</tabs>


### UPDATE REQUEST

IS_DIGITAL değeri yollanmazsa, otomatik olarak 0 atanır.

```json
{
  "ID" : "213123",
  "GRADE_FROM": 1,
  "GRADE_TO": 11,
  "PICTURE": "mediamarkt10.png",
  "PDF": "intermed-goz-muayenesi-ileri-tetkik10.pdf",
  "PRICE": 20,
  "PRODUCT_NAME": "denedmee",
  "DESCRIPTION": "ksdadskads",
  "SUBCATEGORY_ID": 1027,
  "IS_DIGITAL": true
}
```
### UPDATE RESPONSE

```json
{
 "Response" : "31100 - Successfully Updated"
}
```