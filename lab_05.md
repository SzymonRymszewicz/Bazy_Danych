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

