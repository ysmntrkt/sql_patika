# sql_patika
ödev
soru 1 
SELECT title,description FROM film
soru 2
SELECT title,description FROM film WHERE length > 60 AND length < 75;  
soru 3
SELECT title,description FROM film WHERE rental_rate =0.99 AND  replacement_cost = 12.99 OR  replacement_cost = 28.99;
soru 4
SELECT first_name,last_name FROM customer WHERE first_name = 'Mary'
soru 5
SELECT * FROM film WHERE NOT length > 50 AND  rental_rate = 2.99 OR  rental_rate = 4.99; 



Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)
SELECT * FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99; 
.actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)
SELECT first_name, last_name FROM actor WHERE first_name IN('Penelope','Nick','Ed'); 
film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)
SELECT * FROM film WHERE rental_rate IN (0.99, 2.99, 4.99);

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.
SELECT * FROM country WHERE country LIKE 'A%a';
country tablosunda bulunan country sütunundaki ülke isimlerinden  6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.
SELECT * FROM country WHERE country LIKE '_____%n';
film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.
SELECT title FROM film WHERE title ILIKE '%T%T%T%T';
film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.
SELECT * FROM film WHERE title ILIKE 'C%' AND (length > 90 AND rental_rate = 2.99);

Kolay Gelsin.

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.
SELECT  DISTINCT replacement_cost  FROM film ;
film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?
SELECT COUNT (DISTINCT replacement_cost)  FROM film ;
film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?
SELECT COUNT (title)  FROM film WHERE title  LIKE 'T%' AND rating= 'G';
country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?
SELECT COUNT(*) FROM country WHERE country LIKE '_____'; 
city tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?
SELECT COUNT(*) FROM city WHERE city ILIKE '%r'; 


Kolay Gelsin.


Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.



film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.
SELECT title FROM film WHERE title ILIKE '%n'  ORDER BY title LIMIT 5;
film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci 5 filmi sıralayınız.
SELECT title FROM film WHERE title ILIKE '%n'  ORDER BY title DESC LIMIT 5;
customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.
SELECT last_name FROM customer  ORDER BY last_name DESC OFFSET 1 LIMIT 5;

Kolay Gelsin.

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.



film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?
SELECT ROUND (AVG(rental_rate)) FROM film;
film tablosunda bulunan filmlerden kaçtanesi 'C' karekteri ile başlar?
SELECT count(title) FROM film WHERE title LIKE 'C%';
film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?
SELECT MAX(length) FROM film WHERE rental_rate = 0.99 ;
film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?
SELECT SUM(replacement_cost) FROM film WHERE length > 150;


Kolay Gelsin.

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.



film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.
SELECT max( rating)
FROM film
GROUP BY rating ;

film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.
SELECT COUNT (replacement_cost)
FROM film
GROUP BY replacement_cost
ORDER BY replacement_cost > 50;
3. customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?
4. city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıra country_id bilgisini ve şehir sayısını paylaşınız.



Kolay Gelsin.


Merhabalar,



test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
CREATE TABLE employee (id INTEGER, name VARCHAR(50), birthday DATE, email VARCHAR(100));
Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
insert into employe (id, name, email, birthday) values (1, 'Caria', 'ceick0@taobao.com', '04-May-2021');
insert into employe (id, name, email, birthday) values (2, 'Mureil', 'mescot1@mayoclinic.com', '25-Aug-2020');
insert into employe (id, name, email, birthday) values (null, null, null, null);
insert into employe (id, name, email, birthday) values (4, 'Andrus', 'amarre3@census.gov', '14-Jan-2021');
insert into employe (id, name, email, birthday) values (5, 'Jeannette', 'jslatcher4@china.com.cn', '22-Jun-2021');
insert into employe (id, name, email, birthday) values (6, 'Gladi', 'gsoden5@samsung.com', '30-Jul-2021');
insert into employe (id, name, email, birthday) values (7, 'Filmer', 'fseagood6@issuu.com', '12-Mar-2021');
insert into employe (id, name, email, birthday) values (8, 'Cornela', 'cwaddup7@bandcamp.com', '01-Oct-2020');
insert into employe (id, name, email, birthday) values (9, 'Pippy', 'pmarshfield8@list-manage.com', '04-Mar-2021');
insert into employe (id, name, email, birthday) values (10, 'Tessie', 'tdomenge9@moonfruit.com', '06-Oct-2020');
insert into employe (id, name, email, birthday) values (11, 'Dareen', 'drraundla@netscape.com', '26-Oct-2020');
insert into employe (id, name, email, birthday) values (null, null, null, null);
insert into employe (id, name, email, birthday) values (13, 'Farr', 'fgroombridgec@parallels.com', '08-Mar-2021');
insert into employe (id, name, email, birthday) values (14, 'Annalise', 'abikkerd@exblog.jp', '05-Jul-2021');
insert into employe (id, name, email, birthday) values (15, 'Abbey', 'abavridgee@printfriendly.com', '11-Jul-2021');
insert into employe (id, name, email, birthday) values (16, 'Torrie', 'tthomssonf@patch.com', '17-Sep-2020');
insert into employe (id, name, email, birthday) values (17, 'Ode', 'oedmettg@oracle.com', '21-May-2021');
insert into employe (id, name, email, birthday) values (18, 'Gibbie', 'gmeritth@wikia.com', '04-Mar-2021');
insert into employe (id, name, email, birthday) values (19, 'Arlee', 'aduddyi@vimeo.com', '26-Jan-2021');
insert into employe (id, name, email, birthday) values (20, 'Arlen', 'ajorryj@gizmodo.com', '03-May-2021');
insert into employe (id, name, email, birthday) values (null, null, null, null);
insert into employe (id, name, email, birthday) values (22, 'Amil', 'ahuguenetl@reuters.com', '24-Jan-2021');
insert into employe (id, name, email, birthday) values (23, 'Torr', 'tmucklestonem@mozilla.com', '03-Feb-2021');
insert into employe (id, name, email, birthday) values (null, null, null, null);
insert into employe (id, name, email, birthday) values (25, 'Eugenio', 'evallentino@businessweek.com', '29-Sep-2020');
insert into employe (id, name, email, birthday) values (26, 'Lezley', 'ldowneyp@meetup.com', '27-Apr-2021');
insert into employe (id, name, email, birthday) values (27, 'Diana', 'dmcgrearyq@cisco.com', '15-Dec-2020');
insert into employe (id, name, email, birthday) values (28, 'Daphne', 'delwoodr@twitter.com', '22-Oct-2020');
insert into employe (id, name, email, birthday) values (29, 'Ardelle', 'avitterys@examiner.com', '17-Nov-2020');
insert into employe (id, name, email, birthday) values (30, 'Kendrick', 'kcristofolinit@nba.com', '03-May-2021');
insert into employe (id, name, email, birthday) values (31, 'Steve', 'skingscoteu@paypal.com', '26-Jun-2021');
insert into employe (id, name, email, birthday) values (32, 'Vally', 'vhavikv@bluehost.com', '28-Mar-2021');
insert into employe (id, name, email, birthday) values (null, null, null, null);
insert into employe (id, name, email, birthday) values (34, 'Pietra', 'pcastanosx@spiegel.de', '15-Mar-2021');
insert into employe (id, name, email, birthday) values (35, 'Kippie', 'kbroadwoody@skyrock.com', '10-Jan-2021');
insert into employe (id, name, email, birthday) values (36, 'Jedd', 'jcallwayz@imgur.com', '05-Jan-2021');
insert into employe (id, name, email, birthday) values (37, 'Patton', 'pgland10@nifty.com', '01-Jan-2021');
insert into employe (id, name, email, birthday) values (38, 'Devlen', 'dpirot11@mtv.com', '17-Jun-2021');
insert into employe (id, name, email, birthday) values (39, 'Archaimbaud', 'amarlin12@google.it', '08-Mar-2021');
insert into employe (id, name, email, birthday) values (null, null, null, null);
insert into employe (id, name, email, birthday) values (41, 'Humfrey', 'hmacmoyer14@icio.us', '21-Jan-2021');
insert into employe (id, name, email, birthday) values (42, 'Vail', 'vdracey15@de.vu', '02-Dec-2020');
insert into employe (id, name, email, birthday) values (43, 'Darcie', 'dkirrage16@illinois.edu', '09-May-2021');
insert into employe (id, name, email, birthday) values (44, 'Larry', 'llightwing17@ed.gov', '03-Dec-2020');
insert into employe (id, name, email, birthday) values (45, 'Dicky', 'dpreon18@unicef.org', '31-Dec-2020');
insert into employe (id, name, email, birthday) values (46, 'Antoine', 'aevensden19@merriam-webster.com', '12-Aug-2020');
insert into employe (id, name, email, birthday) values (null, null, null, null);
insert into employe (id, name, email, birthday) values (48, 'Minor', 'mpowderham1b@eventbrite.com', '01-Nov-2020');
insert into employe (id, name, email, birthday) values (49, 'Devi', 'drivaland1c@berkeley.edu', '19-Sep-2020');
insert into employe (id, name, email, birthday) values (null, null, null, null);

Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
UPDATE employe SET name ='elmas yaesmin' where name= 'Ode' RETURNING *;
Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
DELETE FROM employe WHERE id < 6 RETURNING *;

Kolay Gelsin.


Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.


Kolay Gelsin.


Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.



city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.
customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.
customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.


Kolay Gelsin.


Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.



actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.
actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.
actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.
İlk 3 sorguyu tekrar eden veriler için de yapalım.


Kolay Gelsin.

Merhabalar,

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.



film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.
payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.




Kolay Gelsin.

Bu çalışmamamızda şimdiye kadar üzerine konuştuğumuz tüm konuları 5 farklı senaryo üzerinden tekrar etmeye çalıştık. Aşağıda ilgili senaryoları bulabilirsiniz.



film tablosundan 'K' karakteri ile başlayan en uzun ve replacenet_cost u en düşük 4 filmi sıralayınız.
film tablosunda içerisinden en fazla sayıda film bulunduran rating kategorisi hangisidir?
cutomer tablosunda en çok alışveriş yapan müşterinin adı nedir?
category tablosundan kategori isimlerini ve kategori başına düşen film sayılarını sıralayınız.
film tablosunda isminde en az 4 adet 'e' veya 'E' karakteri bulunan kç tane film vardır?


Kolay Gelsin
