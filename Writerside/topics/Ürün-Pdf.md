# Ürün Detaylari Düzenlemesi (PDF + IMAGE)

Kategori sayfası üzerinden ürüne gidilip üzerine tıklanıldığında açılan ürün detay sayfasında “Ürün Bulunamadı!” uyarısı alınmakta. Ürün eklenirken yazılan açıklama yazısı ve ürüne ait pdf bu alanda gösterilebilir.


## Açıklama
PDF ve IMAGE artik FTP üzerinden çekilmiyor. Binary olarak HANA üzerinde tutuyoruz. Bunun için bazı düzenlemeler yaptık.
* Son güncelleme de, PDF yüksek boyutlu olduğu için ve tüm ürünleri çekerken performans kaybı yaşandığı için bazı revizeler yaptık.
* Artık, tüm ürünleri çekerken PDF alanını çekmiyoruz. Kullanıcı eğer PDF'i görmek isterse o zaman sadece görmek istediği ürünün PDF alanını dönüyoruz.


# GET

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/read/product.xsjs</code-block>
    </tab>
</tabs>

### All Products Response
```json
{
  "ID": "1007",
  "SUBCATEGORY_ID": "1040",
  "CREATED_AT": "2021-04-19T11:27:25.621Z",
  "CREATED_BY": "00022917",
  "GRADE_FROM": "1",
  "GRADE_TO": "20",
  "PICTURE": "acibadem.png",
  "PRICE": "550",
  "IS_ACTIVE": 1,
  "IS_DIGITAL": null,
  "IS_INNOVATION": 0,
  "PICTURE_NAME": null,
  "TEXT": "Örnek 1",
  "DESCRIPTION": "Örnek"
}
```

### Get Products By Id Response
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/read/product.xsjs?productId='1010'</code-block>
    </tab>
</tabs>


```json
{
  "ID": "1010",
  "SUBCATEGORY_ID": "1040",
  "CREATED_AT": "2021-04-19T11:28:59.436Z",
  "CREATED_BY": "00022917",
  "GRADE_FROM": "1",
  "GRADE_TO": "20",
  "PICTURE": "anadolu.png",
  "PDF": "ASMCheckup40UstuErkek.pdf",
  "PRICE": "1790",
  "IS_ACTIVE": 1,
  "IS_DIGITAL": null,
  "IS_INNOVATION": 0,
  "PICTURE_NAME": null,
  "PDF_NAME": null,
  "TEXT": "Örnek",
  "DESCRIPTION": "Örnek"
}
```