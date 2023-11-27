![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/bef1f6b0-6bd1-4486-bb37-a555e701f8e5)

**Rozwiązanie:**

```sql

create table kreatura as select * from wikingowie.kreatura;
create table zasob as select * from wikingowie.zasob;
create table ekwipunek as select * from wikingowie.ekwipunek;

select * from zasob;

select * from zasob where rodzaj="jedzenie";

select idZasobu, ilosc from zasob inner join kreatura where kreatura.idKreatury = 1 or kreatura.idKreatury = 3 or kreatura.idKreatury = 5;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/5fbf0f0f-2ac2-4aaa-9ab4-5c6a366aefe9)

**Rozwiązanie:**

```sql

select * from kreatura where rodzaj!="wiedzma" and udzwig>=50;

select * from zasob where waga between 2 and 5;

select * from kreatura where nazwa like "%or%" and udzwig between 30 and 70;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/c574ad8d-3131-460f-a1d3-f75d4e822328)

**Rozwiązanie:**

```sql

select * from zasob where month(dataPozyskania) between 7 and 8;

select * from zasob where rodzaj != "null" order by waga;

select * from kreatura order by dataUr limit 5;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/4a130407-e40b-4678-919e-48c797473876)

**Rozwiązanie:**

```sql

select distinct rodzaj from zasob;

select concat(idKreatury, nazwa) from kreatura where rodzaj like "wi%";

select (ilosc * waga), nazwa, dataPozyskania from zasob where year(dataPozyskania) between 2000 and 2007;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/dc7ca55f-787b-4b97-964c-0f479435eee9)

**Rozwiązanie:**

```sql

select nazwa, waga, (waga * 0.7), (waga * 0.3) from zasob where rodzaj = "jedzenie";

select * from zasob where rodzaj is null;

select distinct nazwa from zasob where nazwa like "Ba%" or nazwa like "%os" order by nazwa;

```
