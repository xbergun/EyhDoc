# Ürün Yenilikler Düzenlemesi

Ürün eklenirken ve ya düzenlenirken ürünü “Yenilikler“ alanına ekleyebilmek için bir buton koyabilirz. Bu sayede “Yenilikler“ alanı düzenlenebilir hale gelecektir.

## Açıklama
Product tablosuna, "IS_INNOVATION" adında Boolean bir field eklenmiştir.
- IS_INNOVATION: 1 => Ürün Yenilikler kısmı true
- IS_INNOVATION: 0 => Ürün Yenilikler kısmı false


## GET

### 1.YOL
Tüm ürünleri çekip, IS_INNOVATION alanı 1 olanları filtreleyebilirsiniz.
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/read/product.xsjs</code-block>
    </tab>
</tabs>

### 2.YOL
Parametre olarak sadece yenilik ürünlerini çekebilirsiniz..
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/read/product.xsjs?isInnovation=true</code-block>
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
  "IS_DIGITAL": null,
  "IS_INNOVATION": 0,
  "TEXT": "A101",
  "DESCRIPTION": "* Parçalı kullanım yapılabilir.\n* Online alışverişlerde geçerli değildir.\n* Kullanım süresi 1 yıldır.\n\nDaha fazla detay için butona tıkla!"
}
```

## POST

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/create/product.xsjs</code-block>
    </tab>
</tabs>

### POST REQUEST

IS_INNOVATION değeri yollanmazsa, otomatik olarak 0 atanır.

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
  "IS_INNOVATION": true
}
```
### POST RESPONSE

```json
{
 "Response" : "31100 - Successfully created"
}
```

## UPDATE

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/update/product.xsjs</code-block>
    </tab>
</tabs>


### UPDATE REQUEST

IS_INNOVATION değeri yollanmazsa, otomatik olarak 0 atanır.

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
  "IS_INNOVATION": true
}
```
### UPDATE RESPONSE

```json
{
 "Response" : "31100 - Successfully Updated"
}
```