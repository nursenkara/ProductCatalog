# Product Catalog Project (Ürün Katalog Projesi)
LC Waikiki .Net Bootcamp bitirme projesidir.

- [Product Catalog Project (Ürün Katalog Projesi)](#product-catalog-project-ürün-katalog-projesi)
  - [Production (Projenin Kurulmadan Görüntülenmesi)](#production-projenin-kurulmadan-görüntülenmesi)
  - [Presentation (Sunum)](#presentation-sunum)
  - [Setup (Proje Kurulumu & Ayağa Kaldırılması)](#setup-proje-kurulumu--ayağa-kaldırılması)
  - [Features (Özellikler)](#features-özellikler)
  - [Front-end (Ön yüz projesinde Kullanılan Teknolojiler)](#front-end-ön-yüz-projesinde-kullanılan-teknolojiler)
  - [Back-end (Arka yüz projesinde Kullanılan Teknolojiler)](#back-end-arka-yüz-projesinde-kullanılan-teknolojiler)
  - [ProductCatalogApi](#productcatalogapi)
    - [Endpoints](#endpoints)

## Production (Projenin Kurulmadan Görüntülenmesi)
[https://productcatalog1app.herokuapp.com](https://productcatalog1app.herokuapp.com) adresine gidilerek hiç bir geliştirme ortamına ihtiyaç duyulmadan proje canlı ortamdan görüntülenebilir.

## Presentation (Sunum)
|API|App|
|---|---|
| https://productcatalog1api.herokuapp.com/swagger | https://productcatalog1app.herokuapp.com |
| https://productcatalog2api.herokuapp.com/swagger | https://productcatalog2app.herokuapp.com |
| https://productcatalog3api.herokuapp.com/swagger | https://productcatalog3app.herokuapp.com |
| https://productcatalog4api.herokuapp.com/swagger | https://productcatalog4app.herokuapp.com |
| https://productcatalog5api.herokuapp.com/swagger | https://productcatalog5app.herokuapp.com |

## Setup (Proje Kurulumu & Ayağa Kaldırılması)
- "ProductCatalogApi" projesi "Visual Studio" ile açılıp, "Presentation" klasörü içindeki, "Api" projesi içerisindeki "appsettings.json" içindeki, "ConnectionStrings" altındaki, "MicrosoftSqlServer" connectin string tanımı yapılmalıdır. Tanımlama yapıldıktan sonra, "Package Manager Console"a "Update-Database" komutu yazılarak çalıştırılmalıdır.
- "ProductCatalogApp" klasöründeki, "src" klasöründeki, "config.js" dosyası içindeki, "base" değişkenine, "ProductCatalogApi" projesi başlatıldıktan sonraki tarayıcıda açılan "localhost:xxxx" adresi yazılmalıdır. Yine bu "ProductCatalogApp" klasöründe açılan bir terminalde "npm i" ve "npm start" komutları çalıştırılarak, proje Web Application'ı başlatılabilir.

## Features (Özellikler)
- Front-end projesi TypeScript React ile hazırlandı.
- Dil dosyasındaki  "priceSign" değiştirildiğinde para birimi tüm ui projede değiştirilebilir.
- Veri tabanı, freeasphosting.net adresinden açıldı. Development aşamasında kullanıldığı gibi, gerekirse docker üzerinden MSSQL2019 up edilerek test edilebilir.
- Dil desteği, projenin web arayüzündeki, footer bölümünde, İngilizce ve Türkçe olarak iki adet dil seçimi bulunmaktadır. Sitenin sağ alt kısmından değiştirilebilir.
- Herhangi bir geliştirme ortamı olmadan, production adresinden projeyi görüntüleyip test edebilme özelliği bulunmaktadır.
- Bootswatch sitesinden on tane tema eklendi. Sitenin sağ alt kısmından değiştirilebilir.
- Font Awesome simgeler eklendi.
- JWT Token yapıldı.

Not: Bu repo'da sadece proje dosyaları bulunmaktadır. İki projenin de commit geçmişleri front-end için ayrı, back-end için ayrı gizli repo'larımda bulunmaktadır.

## Front-end (Ön yüz projesinde Kullanılan Teknolojiler)
- TypeScript
- React
- Axios
- Redux
- FortAwesome
- Bootstrap + Bootswatch

## Back-end (Arka yüz projesinde Kullanılan Teknolojiler)
- .Net 6
- Onion Architecture
- CQRS Pattern
- MediatR
- AutoMapper
- Generic Repository
- Entity Framework Core
- Dependency Injection
- Swagger
- Veritabanı MSSQL
- JWT Authentication

## ProductCatalogApi
### Endpoints
Deploy'unun yapıldığı host'ta aşağıdaki yollardan istek gönderildiğinde API projesi cevap vermektedir.

Örnek: https://localhost:7170/api/Brands
Örnek: https://productcatalog1api.herokuapp.com/api/Brands

__Brands__
|Method|Path|
|---|---|
|GET|/api/Brands|
|GET|/api/Brands/{id}|

__Categories__
|Method|Path|
|---|---|
|GET|/api/Categories|
|GET|/api/Categories/{id}|

__Colors__
|Method|Path|
|---|---|
|GET|/api/Colors|
|GET|/api/Colors/{id}|

__Orders__
|Method|Path|
|---|---|
|GET|/api/Orders|
|POST|/api/Orders|
|PUT|/api/Orders|
|GET|/api/Orders/{id}|
|DELETE|/api/Orders/{id}|
|GET|/api/Orders/GetByUserIdOrder/{userId}|
|GET|/api/Orders/GetByProductIdOrder/{productId}|

__Products__
|Method|Path|
|---|---|
|GET|/api/Products|
|POST|/api/Products|
|PUT|/api/Products|
|GET|/api/Products/{id}|
|POST|/api/Products/PictureUpload|

__UseCases__
|Method|Path|
|---|---|
|GET|/api/UseCases|
|GET|/api/UseCases/{id}|

__Users__
|Method|Path|
|---|---|
|GET|/api/Users|
|POST|/api/Users|
|GET|/api/Users/{id}|
|DELETE|/api/Users/{id}|
|POST|/api/Users/Login|
