![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/7a5e8309-4fd4-497b-81b6-b70d33c55bc5)

**Rozwiązanie:**

```sql

select * from postac where rodzaj = "wiking" order by wiek desc;
delete from postac where id_postaci in (15, 18);

set foreign_key_checks = 0;
alter table postac modify id_postaci int;
alter table walizka drop foreign key walizka_ibfk_1;
alter table przetwory drop foreign key przetwory_ibfk_1;
alter table przetwory drop foreign key przetwory_ibfk_2;
alter table postac drop primary key;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/f2b8bee9-ba89-41de-80d9-7e85c7b67c46)

**Rozwiązanie:**

```sql

alter table postac add pesel char(11) first;
update postac set pesel='12345678912' + id_postaci;
alter table postac modify pesel char(11) primary key;

alter table postac modify rodzaj enum("wiking", "ptak", "kobieta", "syrena");
insert into postac VALUES ('98745612378', 115, "Gertruda Nieszczera", "syrena", "432-04-13", 542, null, null);

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/8f560807-4437-40ce-bab8-0c6aefa511c8)

**Rozwiązanie:**

```sql

update postac set statek="Piorun"
where nazwa like '%a%';

update statek set max_ladownosc = max_ladownosc * 0.7
where data_wodowania between "1901-01-01"
and "2000-12-31";

alter table postac modify wiek int unsigned check(wiek <= 1000);

```



**Rozwiązanie:**

```sql

alter table postac modify rodzaj enum("wiking", "kobieta", "ptak", "syrena", "waz");
insert into postac values ('82345678918', 666, "Loko", "waz", "0003-12-23", 1032, default, default);

```

