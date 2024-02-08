# Ürün Bana Özel Kısmı Düzenlemesi

Ürün düzenlerken ve eklerken ürünün ait olduğu sınıfı seçerek onu bana özel önerilenler kısmına eklenebilir. Birden
fazla sınıf aynı anda seçilebilir. Bana özel ürünler kısmındaki "ürünleri incele" butonuna tıklandıktan sonra yeni bir
sayfaya yönlendirilicek. Bu sayfanın içinde herhangi bir ürüne tıklandığında o ürünün sayfasına yönlendirilebilir.

## Açıklama

Belirli kurallara göre her ürünün bir veya birden fazla kuralı olabilir.

### Kurallar

* 30 Yaş Üstü Evli Erkek (o30mm)
* 30 Yaş Üstü Bekar Erkek (o30sm)
* 30 Yaş Üstü Evli Kadın (o30mf)
* 30 Yaş Üstü Bekar Kadın (o30sf)
* 30 Yaş Altı Evli Erkek (u30mm)
* 30 Yaş Altı Bekar Erkek (u30sm)
* 30 Yaş Altı Evli Kadın (u30mf)
* 30 Yaş Altı Bekar Kadın (u30sf)

Şeklinde 8 adettir. UI Tarafında static olarak yazılabilir. İstenirse Backend'den dönülebilir.

# GET

Başka bir endpoint çıkmamak adına, EYH ilk açıldığı anda istek atılan User API'sine gömüldü.
Giriş yapan kullanıcının segment bilgisine göre ürünleri eşleştirip User'a gömer.

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/user/read/user.xsjs</code-block>
    </tab>
</tabs>

### User Response

```json
{
  "userId": "12345",
  "userLocale": "en_US",
  "user": true,
  "admin": true,
  "superAdmin": true,
  "eMail": "dummy@sap.com",
  "firstName": "X",
  "lastName": "X",
  "segment": "o30mm",
  "specialProductsForMe": [
    {
      "ID": "10938",
      "SUBCATEGORY_ID": "1027",
      "CREATED_AT": "2024-01-30T22:30:31.084Z",
      "CREATED_BY": "00030771",
      "GRADE_FROM": "8",
      "GRADE_TO": "10",
      "PICTURE": "Screenshot 2023-03-02 15223232009.png",
      "PICTURE_NAME": "",
      "PRICE": "20",
      "IS_ACTIVE": 1,
      "IS_DIGITAL": 0,
      "IS_INNOVATION": 0,
      "TEXT": "asdasdklsak",
      "DESCRIPTION": "asdasd",
      "SEGMENT_ID": 1,
      "SEGMENT_CODE": "o30mm",
      "SEGMENT_TEXT": "30 Yaş Üstü Evli Erkek"
    },
    {
      "ID": "10904",
      "SUBCATEGORY_ID": "1027",
      "CREATED_AT": "2024-02-05T18:29:13.310Z",
      "CREATED_BY": "00030771",
      "GRADE_FROM": "8",
      "GRADE_TO": "10",
      "PICTURE": "Screenshot 2023-03-02 15223232009.png",
      "PICTURE_NAME": "",
      "PRICE": "20",
      "IS_ACTIVE": 1,
      "IS_DIGITAL": 0,
      "IS_INNOVATION": 0,
      "TEXT": "asdasdklsak",
      "DESCRIPTION": "asdasd",
      "SEGMENT_ID": 1,
      "SEGMENT_CODE": "o30mm",
      "SEGMENT_TEXT": "30 Yaş Üstü Evli Erkek"
    }
  ]
}
```

# POST

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/create/product.xsjs'</code-block>
    </tab>
</tabs>

Product ile birlikte, SPECIAL_FOR_ME adinda array ile gönderilmelidir.

```json
{
  "SPECIAL_FOR_ME": [
    {
      "PRODUCT_ID": 1012,
      "SEGMENT_ID": 1,
      "SEGMENT_CODE": "o30mm",
      "SEGMENT_TEXT": "30 Yaş Üstü Evli Erkek"
    },
    {
      "PRODUCT_ID": 1012,
      "SEGMENT_ID": 2,
      "SEGMENT_CODE": "o30sm",
      "SEGMENT_TEXT": "30 Yaş Üstü Bekar Erkek"
    },
    {
    }
  ]
}
```

# UPDATE

<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/xsrest/product/update/product.xsjs'</code-block>
    </tab>
</tabs>

* Aslında direkt olarak ürüne ait bir kuralı update edemiyoruz. Çünkü update etmeye gerek kalmayan bir kısım burası.
* Kullanıcı, varolan kuralı ürün içerisinden silebilir ya da düzenlerken başka kural ekleyebilir. Bunların hepsi update
  requesti ile yollanır.
* Varsayalım 1010 ID' li ürünün 2 adet kuralı var. Bu ürün düzenlenirken, kural setleri aynı kalacaksa eğer, kural seti
  olduğu gibi yollanır.

```json
{
  "SPECIAL_FOR_ME": [
    {
      "ID": 23232,
      "PRODUCT_ID": 1012,
      "SEGMENT_ID": 1,
      "SEGMENT_CODE": "o30mm",
      "SEGMENT_TEXT": "30 Yaş Üstü Evli Erkek"
    },
    {
      "ID": 123123,
      "PRODUCT_ID": 1012,
      "SEGMENT_ID": 2,
      "SEGMENT_CODE": "o30sm",
      "SEGMENT_TEXT": "30 Yaş Üstü Bekar Erkek"
    },
    {
    }
  ]
}
```

* Eğer 1 tane var ise ve sayısız kural eklemek istiyorsanız oluşacak body;
* var olan kural ID si ile birlikte yollanır.
```json
{
  "SPECIAL_FOR_ME": [
    {
      "ID": 23232,
      "PRODUCT_ID": 1012,
      "SEGMENT_ID": 1,
      "SEGMENT_CODE": "o30mm",
      "SEGMENT_TEXT": "30 Yaş Üstü Evli Erkek"
    },
    {
      "PRODUCT_ID": 1012,
      "SEGMENT_ID": 2,
      "SEGMENT_CODE": "o30sm",
      "SEGMENT_TEXT": "30 Yaş Üstü Bekar Erkek"
    },
    {
      "PRODUCT_ID": 1012,
      "SEGMENT_ID": 2,
      "SEGMENT_CODE": "u30sm",
      "SEGMENT_TEXT": "30 Yaş Altı Bekar Erkek"
    }
  ]
}
```

# Delete

Kural silme işlemini yapmak için body içerisinde o kuralı yollamamanız yeterli.
* Örnek olarak, bir üstte olan body de 23232 ID'li kuralı silmek istiyorsunuz.

```json
{
  "SPECIAL_FOR_ME": [
    {
      "PRODUCT_ID": 1012,
      "SEGMENT_ID": 2,
      "SEGMENT_CODE": "o30sm",
      "SEGMENT_TEXT": "30 Yaş Üstü Bekar Erkek"
    },
    {
      "PRODUCT_ID": 1012,
      "SEGMENT_ID": 2,
      "SEGMENT_CODE": "u30sm",
      "SEGMENT_TEXT": "30 Yaş Altı Bekar Erkek"
    }
  ]
}
```

