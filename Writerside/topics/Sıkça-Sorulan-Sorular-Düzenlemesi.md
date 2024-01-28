# Sıkça Sorulan Sorular  

Sıkça sorulan soruların düzenlenmesini biraz daha yönetilebilir hale getirebilmek için sıkça sorulan sorular kısmında soruların en üstünde yeni bir soru ekleme butonu konumlandırabiliriz. Aynı zamanda soruların düzenlenmesi için soruların içinde düzenleme ve silme işlemleri için silme butonu konumlandırabiliriz.

## Açıklama
Sıkça sorulan sorular için yeni bir servis yazılmıştır.
- Kategori yönetimi kolaylaşması adına, kategoriye göre post request atılmalıdır.

## API REFERENCE

### GET
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/com/ittr/sf/eyh/connectivity/rest/faq/read/faq.xsjs</code-block>
    </tab>
</tabs>

### RESPONSE
```json
{
  "EYH Uygulaması ve Kapsamı": [
    {
      "QUESTION": "Deneme Question 2",
      "ANSWER": "Deneme ANSWER 2"
    },
    {
      "QUESTION": "Deneme Question 3",
      "ANSWER": "Deneme ANSWER 3"
    },
    {
      "QUESTION": "Deneme Question 4",
      "ANSWER": "Deneme ANSWER 4"
    }
  ],
  "EYH Seçim ve Sistem Kullanımı": [
    {
      "QUESTION": "Deneme Question 1",
      "ANSWER": "Deneme ANSWER 1"
    },
    {
      "QUESTION": "Deneme Question 2",
      "ANSWER": "Deneme ANSWER 2"
    },
    {
      "QUESTION": "Deneme Question 3",
      "ANSWER": "Deneme ANSWER 3"
    }
  ]
}
```

## POST
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/com/ittr/sf/eyh/connectivity/rest/faq/create/faq.xsjs</code-block>
    </tab>
</tabs>

### Post Request

```json
{
  "QUESTION" : "Deneme Question 10",
  "ANSWER" : "Deneme ANSWER 10",
  "CATEGORY" : "Ürünler ve Kullanım Koşulları"
}
```
> **ÖNEMLİ**
>
> KATEGORİ İSMİ TAM OLARAK DOĞRU ŞEKİLDE GİRİLMELİDİR. EĞER STRİNG UYUŞMAZSA BAŞKA KATEGORİ AÇAR.
>
{style="note"}

### POST RESPONSE


```json
{
  "Response": "41100 - Successfully created"
}
```
## UPDATE
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/com/ittr/sf/eyh/connectivity/rest/faq/update/faq.xsjs</code-block>
    </tab>
</tabs>

### Update Request

```json
{
  "ID": "1203",
  "QUESTION" : "Deneme Question 10",
  "ANSWER" : "Deneme ANSWER 10",
  "CATEGORY" : "Ürünler ve Kullanım Koşulları"
}
```
> **ÖNEMLİ**
>
> KATEGORİ İSMİ TAM OLARAK DOĞRU ŞEKİLDE GİRİLMELİDİR. EĞER STRİNG UYUŞMAZSA BAŞKA KATEGORİ AÇAR.
>
{style="note"}

### UPDATE RESPONSE


```json
{
 "Response": "41100 - Successfully Updated"
}
```
## DELETE
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/com/ittr/sf/eyh/connectivity/rest/faq/delete/faq.xsjs?ID=1234</code-block>
    </tab>
</tabs>

### DELETE RESPONSE

```json
{
 "Response": "41100 - Successfully Deleted"
}
```



