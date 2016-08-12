Kodpress Api
===================

Türkiye'deki yaklaşık 74 milyon (2014 istatistiklerine göre) wordpress tabanlı web uygulama var. Halihazırda bu uygulamaların yarısına yakını sahipleri tarafından kendi sunucularında tutuluyor. Bu veriler ışığında kullanıcılar mobil platforma da kayma isteğinde bulunabiliyor. Tüm bu durumlar göz önüne alındığında Kodpit Yazılım olarak bu wordpress platformlarını mobil platformlarla birleştiriyor. Bizim geliştirdiğimiz mobil teknolojilerle,  web masterların geliştirdiği api desteği birleşince karşınıza harika bir sistem çıkıyor. **KODPRESS...** 

----------
##Authorization
Herhangi authorization işlemine ihtiyaç yok. Wordpress kadar açık.. 

----------

##Desteklenen veri formatı

```json
application/json
```

----------

##Dökumantasyon

GET /KODPRESS/status -> Wordpress arayüzündeki güncellemeyi dinler.
Parameters:
: none

**Response:**
```json
{ "datachange" = "1" } yada { "datachange" = "0" }
```
---

GET /KODPRESS/initialize -> Uygulama hazırlama için çeşitli veriler.(Postlar,  kategoriler, reklamlar, son dakika haberleri, slider ayarlamaları...)
Parameters:
: none

**Response:**
```json
{
  "success": "1",
  "errorcode": "200",
  "message": "All done",
  "app_name/icon": "",
  "related_post_text": "",
  "categories": [
    {
      "categori_id": "1",
      "categori_name": "Healt",
      "categori_count": "6",
      "categori_bacgroundcolor": "#55555",
      "categori_color": "#444444",
      "categori_fontsize": "14",
      "categori_fontfamily": "Inconsolata"
    }...
  ],
  "socialMedia": [
    {
      "sm_icon": "http://",
      "sm_url": "https://twitter.com/okancancosar"
    }...
  ],
  "navigationbar_styles": {
    "navbar_bacgroundcolor": "#55555",
    "navbar_color": "#444444",
    "navbar_fontsize": "14",
    "navbar_fontfamily": "Inconsolata",
    "navbar_backicon_color": "#22144",
    "navbar_backicon_fontsize": "15"
  },
  "breakingNews_styles": {
    "news_text": "Breaking News is here",
    "news_color": "#876532",
    "news_bacgroundcolor": "#e45e5",
    "news_fontsize": "15",
    "news_fontfamily": "Ariel",
    "news_icon_fontsize": "14",
    "news_icon_color": "#344343"
  },
  "sliderImages": [
    {
      "post_id": "1",
      "post_image": ""
    }...
  ],
  "indexPosts": [
    {
      "categori_id": "1",
      "categori_name": "Healt",
      "categori_count": "6",
      "categori_bacgroundcolor": "#55555",
      "categori_color": "#444444",
      "categori_fontsize": "14",
      "categori_fontfamily": "Inconsolata",
      "categori_allposts_text": "TÃ¼m yazÄ±lar",
      "categori_allposts_color": "#23223",
      "categori_allposts_bacgroundcolor": "#23223",
      "categori_allposts_fontsize": "14",
      "categori_allposts_fontfamily": "Ariel",
      "post_bacgroundcolor": "#343443",
      "posts": [
        {
          "post_id": "5",
          "post_image": "http://img.fontspace.com/images/fontspace-logo-small-white.png",
          "post_name": "Hello world is best code ever",
          "post_name_bacgroundcolor": "",
          "post_name_color": "",
          "post_name_fontsize": "",
          "post_name_fontfamily": "",
          "post_detail": "Lorem ipsum dolor sit amet...",
          "post_detail_bacgroundcolor": "#23223",
          "post_detail_color": "#23223",
          "post_detail_fontsize": "15",
          "post_detail_fontfamily": "Sans"
        }...
      ]
    }...
  ],
  "indexAdvertisement": [
    {
      "advertisement_spot": "5",
      "advertisement_code": "<html></html>"
    }...
  ]
}
```
---

GET /KODPRESS/allposts -> Tüm postları getirir.
Parameters:
: none

**Response:**
```json
{
  "success": 1,
  "errorcode": "200",
  "message": "ok",
  "categori_name": "Healt",
  "posts": [
    {
      "post_id": "5",
      "post_image": "http://img.fontspace.com/images/fontspace-logo-small-white.png",
      "post_name": "Hello world is best code ever",
      "post_categori": "",
      "post_name_bacgroundcolor": "",
      "post_name_color": "",
      "post_name_fontsize": "",
      "post_name_fontfamily": "",
      "post_detail": "Lorem ipsum dolor sit amet...",
      "post_detail_bacgroundcolor": "#23223",
      "post_detail_color": "#23223",
      "post_detail_fontsize": "15",
      "post_detail_fontfamily": "Sans"
    }...
  ],
  "allPostAdvertisement": [
    {
      "advertisement_spot": "5",
      "advertisement_code": "<html></html>"
    }...
  ]
}
```
---

GET /KODPRESS/detail/{post_id} -> Post'un detayını getirir. 
Parameters:
: none

**Response:**
```json
{
  "success": 1,
  "errorcode": "200",
  "message": "",
  "post_image": "",
  "post_name": "",
  "post_detail": "",
  "post_date": "15.07.2015 15:12   or today or yesterday",
  "post_author": "okancancosar",
  "command_count": "5",
  "shared_text": "'post_name' + 'post_link'",
  "relatedPosts": [
    {
      "post_id": "5",
      "post_image": "http://img.fontspace.com/images/fontspace-logo-small-white.png",
      "post_name": "Hello world is best code ever",
      "post_name_bacgroundcolor": "",
      "post_name_color": "",
      "post_name_fontsize": "",
      "post_name_fontfamily": "",
      "post_detail": "Lorem ipsum dolor sit amet...",
      "post_detail_bacgroundcolor": "#23223",
      "post_detail_color": "#23223",
      "post_detail_fontsize": "15",
      "post_detail_fontfamily": "Sans",
      "post_categori": "Programming"
    }...
  ],
  "detailsAdvertisement": [
    {
      "advertisement_spot": "5",
      "advertisement_code": "<html></html>"
    }...
  ]
}
```
---

GET /KODPRESS/comments/{post_id} -> Post'un yorumlarını getirir. 
Parameters:
: none

**Response:**
```json
{
  "success": 1,
  "errorcode": "200",
  "message": "ok",
  "comments": [
    {
      "person_name": "",
      "person_image": "",
      "comment_time_date": "10.08.2016 14:36:48",
      "comment_text": "",
      "reply_comments": [
        {
          "person_name": "",
          "person_image": "",
          "comment_time_date": "10.08.2016 14:36:48",
          "comment_text": ""
        }...
      ]
    }...
  ]
}
```
---

POST /KODPRESS/comments/ -> Post'a yeni yorum ekler.
Parameters:	
: "person_name"
: "person_comments"
: "post_id"

**Response:**
```json
{"status":"1", "message":"ok"}
```
------------------------------------------------------
POST /KODPRESS/comments/ -> Post'un yorumuna cevap ekler.
Parameters:
: "person_name"
: "person_comments"
: "post_id"
: "yorum_id"

**Response:**
```json
{"status":"1", "message":"ok"}
```
---
