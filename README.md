Kodpress Api
===================
Dünya'nın en büyük açık kaynak kodlu platformu olan wordpress her geçen gün artış gösteren grafiği ile kullanıcılarda mobil platforma kayma isteğini de ortaya çıkartıyor. Bu durum göz önüne alındığında Kodpit Yazılım olarak bu wordpress platformlarını mobil platformlarla birleştiriyoruz. Bizim geliştirdiğimiz mobil teknolojilerle,  webmasterların geliştirdiği api desteği birleşince karşınıza harika bir sistem çıkıyor. **KODPRESS...** 

##Version
1.0.0

##Authorization
Herhangi authorization işlemine ihtiyaç yok. Wordpress kadar açık.. 


##Dökumantasyon


####**Wordpress arayüzündeki güncellemeyi dinler.**

**Request:**
```
URL: {www.domain.com}/kodpress-api/status
HTTP Request Type: GET
Parameters: none
```
**Response:**
```
{ 
	"status" : "1" ## Wordpress paneldeki değişiklik var mı?
}
```
------
####**Uygulama hazırlama için çeşitli veriler içerir.**

**Request:**
```
URL: {www.domain.com}/kodpress-api/initialize
HTTP Request Type: GET
Parameters: none
	
```
**Response:**
```
{
  "success": "1",
  "message": "All done",
  "related_post_text": "", ## İlgili postlar başlığı
  "categories": [
    {
      "category_id": "1",
      "category_name": "Healt",
      "category_count": "6", ##kategorideki post sayısı
      "category_bacgroundcolor": "#55555",
      "category_color": "#444444",
      "category_fontsize": "14",
      "category_fontfamily": "Inconsolata"
    }
  ],
  "link": [
    {
      "sm_icon": "http://",
      "sm_url": "https://twitter.com/okancancosar"
    }
  ],
  "theme_settings":{   ## Her tema için farklılaşabilir ancak ana hatlarıyla böyle
    "app_name/icon": "", ## Uygulamalar için marka ikonu(navbar için)
    "navigationbar_styles": {
      "navbar_bacgroundcolor": "#55555",
      "navbar_color": "#444444",
      "navbar_fontsize": "14",
      "navbar_fontfamily": "Inconsolata",
      "navbar_backicon_color": "#22144",
      "navbar_backicon_fontsize": "15"
    },
    "breakingNews_styles": {    ##son dakika haberleri için
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
        "post_id": "1",     ## sliderda bulunacak post'un id'si
        "post_image": ""    ## post'un önemli görseli
      }
    ],
    "indexPosts": [  ## Her kategoriden kullanıcının belirlediği sayıda postlar
      {
        "category_id": "1",
        "category_name": "Healt",
        "category_count": "6",
        "category_bacgroundcolor": "#55555",
        "category_color": "#444444",
        "category_fontsize": "14",
        "category_fontfamily": "Inconsolata",
        "category_allposts_text": "Tüm yazılar",
        "category_allposts_color": "#23223",
        "category_allposts_bacgroundcolor": "#23223",
        "category_allposts_fontsize": "14",
        "category_allposts_fontfamily": "Ariel",
        "post_bacgroundcolor": "#343443",
        "posts": [
          {
            "post_id": "5",
            "post_image": "http://kodpress.com/images/fontspace.png",
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
          }
        ]
      }
    ],
    "indexAdvertisement": [  ## Ekran için reklam yerleri
      {
        "advertisement_spot": "5",  ##Belirlenen yerler için verilen idler(spotlar)
        "advertisement_code": "<html></html>" ## Reklam kodu
      }
    ]
  }
}
```
---
####**Tüm Post'ları Getir**

**Request:**
```
URL: {www.domain.com}/kodpress-api/all-posts
HTTP Request Type: GET
Parameters: none
	
```
**Response:**
```
{
  "success": 1, 
  "message": "ok",
  "category_name": "Healt",
  "posts": [
    {
      "post_id": "5",
      "post_image": "http://kodpress.com/images/white.png",
      "post_name": "Hello world is best code ever",
      "post_category": "",
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
  "allPostAdvertisement": [   ## Ekran için reklam yerleri
    {
      "advertisement_spot": "5", ##Belirlenen yerler için verilen idler(spotlar)
      "advertisement_code": "<html></html>"  ## Reklam kodu
    }...
  ]
}
```
---

####**Post detaylarını getirir.**

**Request:**
```
URL: {www.domain.com}/kodpress-api/detail/{post_id}
HTTP Request Type: GET
Parameters: none
```
**Response:**
```
{
  "success": 1,
  "message": "",
  "post_image": "",
  "post_name": "",
  "post_detail": "",
  "post_date": "15.07.2015 15:12", ## yada today yada yesterday
  "post_author": "okancancosar",
  "command_count": "5", ## post'un yorum sayısı 
  "shared_text": "'post_name' + 'post_link'", ## sosyal medyalarda veya whatsappda paylaşma metni
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
      "post_category": "Programming"
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
####**Post'un yorumlarını getirir.**

**Request:**
```
URL: {www.domain.com}/kodpress-api/comments/{post_id}
HTTP Request Type: GET
Parameters: none
```
**Response:**
```
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
      "reply_comments": [  ## yorumun cevapları
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
####**Post'a yeni yorum ekler.**

**Request:**
```
URL: {www.domain.com}/kodpress-api/comments
HTTP Request Type: POST
Parameters:	
 "person_name"
 "person_comments"
 "post_id"
	
```
**Response:**
```
{"status":"1", "message":"ok"}
```

-----------

####**Post'un yorumuna cevap ekler.**

**Request:**
```
URL: {www.domain.com}/kodpress-api/comments
HTTP Request Type: POST
Parameters:
 "person_name"
 "person_comments"
 "post_id"
 "comment_id"	
```
**Response:**
```
{"status":"1", "message":"ok"}
```
---
