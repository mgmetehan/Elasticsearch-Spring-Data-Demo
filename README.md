# Elasticsearch-Spring-Data-Demo

## Icerik
- [Elasticsearch'un avantajlari](#elasticsearchun-avantajlari)
- [Tech Stack](#tech-stack)
- [Requirements](#requirements)
- [Build & Run](#build--run)
- [Elasticsearch'u Kimler Kullaniyor?](#elasticsearchu-kimler-kullaniyor)

##  Elasticsearch'un avantajlari

<p align="center">
    <img src="png/benefits-elastic.png" alt="benefits-elastic" width="%100" height="600" style="border-radius: 20px">
</p>

- `High Performance(Yuksek Performans):`

  Elasticsearch, guclu tam metin arama yetenekleriyle bilinir. Apache Lucene altyapisi kullanarak ters indeksleme ve gelismis arama algoritmalari kullanarak hizli ve dogru arama sonuclari saglar. Tipik bir SQL veritabanindan daha hizlidir.


- `Near Real-Time Operations(Neredeyse Gercek Zamanli Islemler):`

  Veri okuma veya yazma gibi Elasticsearch islemleri genellikle bir saniyeden daha kisa surede tamamlanir. Bu nedenle Elasticsearch'ten uygulama izleme ve anormallik algilama gibi neredeyse gercek zamanli kullanim amaclari dogrultusunda faydalanabilirsiniz.


- `Lots of Search Options(Cok Sayida Arama Secenegi):`

  Elasticsearch, arama konusunda bircok ozellik sunar. Full-text search(tam metin arama),auto-complete(otomatik tamamlama), instant search(anlik arama) ve daha fazlasini alabilirsiniz.

  Autocompletion(Otomatik tamamlama) ve instant search(anlik arama), yazarken oneriler sunar. Oneriler, arama gecmisi veya ilgilige dayali olarak tahmin edilir. Ayrica yazim hatasi varsa bile kullanicilar ilgili aramalar alir.


- `Distributed Approach(Dagitik mimari):`

  Elasticsearch, dagitik bir mimaride calisir. Sonuc olarak, buyuk miktarda veriyi hizli bir sekilde isleyebilir. Diziler parcalara ayrilir. Parcalar tam islevli bir dizin gibi calisir. Her parcada cok sayida kopya olabilir. Bu parcalari Elasticsearch kumesinin herhangi bir yerine barindirabilirsiniz.


- `Cluster and Backup Support (Cluster ve Yedekleme Destegi):`

  Elasticsearch, coklu dugumlerden (nodes) olusan bir kume (cluster) icinde calisabilir. Bu, yuksek kullanilabilirlik saglamak ve veri kaybini onlemek icin onemlidir. Ayrica, verilerin yedeklenmesi icin kapsamli bir sistem sunar.


- `Plugins and Integrations(Eklentiler ve Entegrasyonlar):`

  Elasticsearch, eklentiler ve entegrasyonlarla yuksek uyumludur. Eklentiler, islevselligi artirmak ve aramalari ozellestirmek icin kullanilir. Ozel eslemeler, analizciler ve kesifler eklemeye yardimci olur.


- `RESTful API:`

  Elasticsearch, sundugu basit REST tabanli API'ler sayesinde hizmeti hizla kullanmaya baslamanizi ve farkli kullanim orneklerine uygun uygulamalar tasarlamanizi saglar.


- `Security(Guvenlik):`

  Elasticsearch, kullanici kimlik dogrulama, erisim kontrolu ve veri sifreleme gibi guvenlik onlemlerini destekler.


- `Easy Application Development:`

  Kolay uygulama gelistirme Java, Python, PHP, JavaScript, Node.js, Ruby ve daha bircok dil icin destek sunar.

##  Elasticsearch'u Kimler Kullaniyor?
<p align="center">
    <img src="png/companies.png" alt="companies" width="%100" height="600" style="border-radius: 20px">
</p>

##  Elasticsearch vs SQL
<p align="center">
    <img src="png/comparison.png" alt="companies" width="%100" height="600" style="border-radius: 20px">
</p>

<details>
<summary>Summary Query Nedir?</summary>

**Summary Query:** Genel bir bakis sunar. Genellikle veri toplamalarini ve sonuclari daha yuksek duzeyde ozetlemeyi amaclar.

Ornegin, bir musterinin toplam siparis tutarini gosterir:
```sql
SELECT musteri_id,
       ad,
       soyad,
       SUM(siparis_tutari) AS toplam_siparis_tutari
FROM Musteriler
GROUP BY musteri_id, ad, soyad
```

Bu sorgu, her musterinin adini, soyadini ve toplam siparis tutarini ozetler.
</details> 

<details>
<summary>Detail Query Nedir?</summary>

**Detail Query:** daha spesifik veya ayrintili verileri cekmeyi amaclar. Bu tur sorgular, genellikle belirli bir kosulu karsilayan veya belirli bir veri kesimini getiren sorgulardir. 

Ornegin, belirli bir musterinin siparislerini listeleyecektir.
```sql
SELECT musteri_id,
       siparis_id,
       siparis_tarihi,
       urun_adi,
       miktar,
       siparis_tutari
FROM Siparisler
WHERE musteri_id = 'belirli_musteri_id'
```

Bu sorgu, belirli bir musterinin (musteri kimlik numarasina gore filtrelenmis) her bir siparisini ve siparislerin ayrintilarini listeleyecektir.
</details> 

## Tech Stack
- Java 17
- Spring Boot 3.0
- Spring Elasticsearch Data
- Docker
- Lombok

## Requirements

For building and running the application you need:
- JDK 17 or newer
- [Maven](https://maven.apache.org)
- [Lombok](https://projectlombok.org/)


## Build & Run
```
  docker-compose -f docker-compose.yml up -d
```
```
  mvn clean install && mvn --projects backend spring-boot:run
```