# Ürün Aktif Pasifliği

Ürün düzenlenirken ya da eklerken ürünleri aktif ve ya pasif duruma çekebilmek için bir buton yerleştirebiliriz. Bu sayede ürünleri kaldırmak zorunda kalmayız ve veri kaybını azaltmış oluruz.

## API REFERENCE

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/read/product.xsjs</code-block>
    </tab>
</tabs>

## Açıklama
Product tablosuna, "IS_ACTIVE" adında Boolean bir field eklenmiştir.
- IS_ACTIVE: 1 => Ürün Aktif
- IS_ACTIVE: 0 => Ürün Pasif

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

### DELETE REQUEST

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/delete/product.xsjs?ProductId=123123</code-block>
    </tab>
</tabs>

Ürünü hard delete olarak silmez. IS_ACTIVE alanını 0'a çeker.

### Delete Response
```json
{
"Response": "34100 - Successfully deleted"
}
```