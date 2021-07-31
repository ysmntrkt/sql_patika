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
film tablosunda bulunan filmlerden kaçtanesi 'C' karekteri ile başlar?
film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?
film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?


Kolay Gelsin.


