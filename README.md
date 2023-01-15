Merhabalar,

test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.


--1.SORU--
CREATE TABLE employee(
       id SERIAL PRIMARY KEY,
       name VARCHAR(50) NOT NULL,
       birthday DATE,
       email VARCHAR(100)
);


--3.SORU--
UPDATE employee
SET email = 'Şevval Hilal Aydın'
         birthday = '2001-03-22'
WHERE id = 1;

UPDATE employee
SET email = 's.hilalaydin@outlook.com'
WHERE name = 'Şevval Hilal Aydın';

UPDATE employee
SET name = 'Zeynep Çamcı'
WHERE name LIKE 'Z%'
RETURNING *;

UPDATE employee
SET email = 'zeynepcamci@hotmail.com'
WHERE name LIKE 'Z%'
RETURNING *;


UPDATE employee
SET name = 'Yağmur Deniz'
        email = 'yagmur@hotmail.com'
        birthday = '1999-04-08'
WHERE email = 'yagmurdeniz@hotmail.com'
RETURNING *;

--4.SORU--
DELETE FROM employee
WHERE birthday = '1998-03-09'
RETURNING *;

DELETE FROM employee
WHERE id = 6
RETURNING *;


DELETE FROM employee
WHERE name ILIKE 'V%'
RETURNING *;


DELETE FROM employee
WHERE email = 'yagmur@hotmail.com
RETURNING *;

DELETE FROM employee
WHERE id BETWEEN 4 AND 7
RETURNING *;


























