# Sıkça Sorulan Sorular  

Sıkça sorulan soruların düzenlenmesini biraz daha yönetilebilir hale getirebilmek için sıkça sorulan sorular kısmında soruların en üstünde yeni bir soru ekleme butonu konumlandırabiliriz. Aynı zamanda soruların düzenlenmesi için soruların içinde düzenleme ve silme işlemleri için silme butonu konumlandırabiliriz.

## Açıklama
Sıkça sorulan sorular için yeni bir servis yazılmıştır.
- Kategori yönetimi kolaylaşması adına, kategoriye göre post request atılmalıdır.

## API REFERENCE

## GET
<tabs>
    <tab title="API URL">
        <code-block lang="plain text">/com/ittr/sf/eyh/connectivity/rest/faq/read/faq.xsjs</code-block>
    </tab>
</tabs>

### RESPONSE
```json
{
  "ID": "1",
  "CATEGORY": "EYH Uygulaması ve Kapsamı",
  "CONTENT": [
    {
      "ID": "1032",
      "QUESTION": "Deneme Question 2",
      "CATEGORY_ID": "1",
      "ANSWER": "Deneme ANSWER 2",
      "CREATED_BY": "00030771",
      "CREATED_AT": "2024-01-27T00:16:52.047Z",
      "HEADER_TEXT": "EyhKapsam"
    },
    {
      "ID": "1044",
      "QUESTION": "Deneme Question 3",
      "CATEGORY_ID": "1",
      "ANSWER": "Deneme ANSWER 3",
      "CREATED_BY": "00030771",
      "CREATED_AT": "2024-01-27T00:16:57.826Z",
      "HEADER_TEXT": "EyhKapsam"
    },
    {
      "ID": "1056",
      "QUESTION": "Deneme Question 4",
      "CATEGORY_ID": "1",
      "ANSWER": "Deneme ANSWER 4",
      "CREATED_BY": "00030771",
      "CREATED_AT": "2024-01-27T00:17:04.326Z",
      "HEADER_TEXT": "EyhKapsam"
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
  "QUESTION" : "DENEME CREATE QUESTION",
  "ANSWER": "DENEME CREATE ANSWER",
  "CATEGORY_ID": "4",
  "HEADER_TEXT" : "DENEME CREATE QUESTION"
}
```

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
  "ID" : "1140",
  "QUESTION" : "sdasadsadsa",
  "ANSWER": "asdsadsds",
  "CATEGORY_ID": "4",
  "HEADER_TEXT" : "DENEME UPDATEDD QUESTION"
}
```

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



