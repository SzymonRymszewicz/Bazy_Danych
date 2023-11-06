# Zadania z lab_04

1. Zadanie z Bjornem

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/b0bf9750-484f-4634-8b36-2447e1571679)


```sql

CREATE TABLE postac (id_postaci INT PRIMARY KEY AUTO_INCREMENT, nazwa VARCHAR(40), rodzaj ENUM('wiking', 'ptak', 'kobieta'), data_ur DATE, wiek INT);
INSERT INTO postac VALUES (1, "Bjorn", "wiking", "966-07-16", 34);
INSERT INTO postac VALUES (2, "Drozd", "ptak", "966-04-16", 2);
INSERT INTO postac VALUES (3, "Tesciowa", "kobieta", "932-04-16", 74);
UPDATE postac SET wiek = 88 WHERE id_postaci = 3;

```
