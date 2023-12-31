# Zadania z lab_04

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/b0bf9750-484f-4634-8b36-2447e1571679)

**Rozwiązanie:**

```sql

CREATE TABLE postac (id_postaci INT PRIMARY KEY AUTO_INCREMENT, nazwa VARCHAR(40), rodzaj ENUM('wiking', 'ptak', 'kobieta'), data_ur DATE, wiek INT UNSIGNED);
INSERT INTO postac VALUES (1, "Bjorn", "wiking", "966-07-16", 34);
INSERT INTO postac VALUES (2, "Drozd", "ptak", "966-04-16", 2);
INSERT INTO postac VALUES (3, "Tesciowa", "kobieta", "932-04-16", 74);
UPDATE postac SET wiek = 88 WHERE id_postaci = 3;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/5ce35921-1386-4685-a449-c52846c0f036)

**Rozwiązanie:**

```sql

CREATE TABLE walizka (id_walizki INT AUTO_INCREMENT PRIMARY KEY, pojemnosc FLOAT UNSIGNED, kolor ENUM("rozowy", "czerwony", "teczowy", "zolty"), id_wlasciciela INT, FOREIGN KEY (id_wlasciciela) REFERENCES postac(id_postaci) ON DELETE CASCADE);
ALTER TABLE walizka ALTER kolor SET DEFAULT "rozowy";
INSERT INTO walizka VALUES (1, 20, "teczowy", 1);
INSERT INTO walizka VALUES (2, 10, "rozowy", 3);

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/67a4c987-d55a-4a16-ae72-eb387011560b)

**Rozwiązanie:**

```sql

CREATE TABLE izba (adres_budynku VARCHAR(50), nazwa_izby VARCHAR(50), metraz FLOAT UNSIGNED, wlasciciel INT, PRIMARY KEY (adres_budynku, nazwa_izby), FOREIGN KEY (wlasciciel) REFERENCES postac(id_postaci) ON DELETE SET NULL);
ALTER TABLE izba ADD kolor_izby VARCHAR(50) DEFAULT "czarny" AFTER metraz;
INSERT INTO izba VALUES ("Bjornowa 4", "spizarnia", 45, "czarny", 1);

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/54b3e104-35cb-47ea-85c1-602259d0e221)

**Rozwiązanie:**

```sql

CREATE TABLE przetwory (id_przetworu INT, rok_produkcji SMALLINT DEFAULT "1654", id_wykonawcy INT, zawartosc VARCHAR(100), dodatek VARCHAR(100) DEFAULT "papryczka chilli", id_konsumenta INT, PRIMARY KEY(id_przetworu), FOREIGN KEY(id_wykonawcy) REFERENCES postac(id_postaci), FOREIGN KEY(id_konsumenta) REFERENCES postac(id_postaci));
INSERT INTO przetwory VALUES (1, 1352, 1, "rzeczy", "czosnek", 3);


```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/5dfe7174-b8f5-48f6-a706-4187a7f5dbd7)

```sql

insert into postac VALUES 
(default, "Martar", "wiking", "0923-02-15", 55),
(default, "Thor", "wiking", "0003-02-15", 1032), 
(default, "Hjalmar", "wiking", "0943-01-25", 25), 
(default, "Loki", "wiking", "0973-02-15", 15),
(default, "Urak", "wiking", "0913-02-15", 91);

create table statek (
nazwa_statku varchar(200),
rodzaj_statku ENUM("szybki", "mocny"),
data_wodowania date,
max_ladownosc int unsigned, primary key (nazwa_statku));

insert into statek values 
("Piorun", "szybki", "966-12-01", 20),
("Twardy", "mocny", "936-02-11", 50);

alter table postac add funkcja varchar(200);

update postac set funkcja = "kapitan" where id_postaci = 1;

alter table postac add statek varchar(200), add foreign key(statek) references statek(nazwa_statku);

update postac inner join statek set postac.statek = statek.nazwa_statku where postac.rodzaj = "wiking" or postac.rodzaj = "ptak" and statek.nazwa_statku = "Piorun";

delete from izba where nazwa_izby = "spizarnia";

drop table izba;

```

