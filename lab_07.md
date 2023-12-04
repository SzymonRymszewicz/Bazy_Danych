![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/ee325cb9-58e5-4a10-81fc-34aa3dc9ed3d)

**Rozwiązanie:**

```sql

select avg(waga) from kreatura where rodzaj="wiking";

select avg(waga), count(rodzaj), rodzaj from kreatura group by rodzaj;

select avg(year(dataUr)), rodzaj from kreatura group by rodzaj;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/817e21e0-6b7e-4260-a64d-69b3c211fd52)

**Rozwiązanie:**

```sql

select sum(waga), rodzaj from zasob group by rodzaj;

select nazwa, avg(waga) from zasob group by nazwa having sum(ilosc) >= 4 and sum(waga) > 10;

select count(nazwa), rodzaj, min(ilosc) from zasob group by rodzaj having min(ilosc) > 1;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/e7bb5e29-5169-4ee7-ad2f-f20e04c6b3f7)

**Rozwiązanie:**

```sql

select count(ilosc), kreatura.nazwa from ekwipunek inner join kreatura on kreatura.idKreatury = ekwipunek.idKreatury group by kreatura.nazwa;

select kreatura.nazwa, zasob.nazwa from ekwipunek inner join kreatura on kreatura.idKreatury = ekwipunek.idKreatury inner join zasob on ekwipunek.idZasobu = zasob.idZasobu order by kreatura.nazwa;

select kreatura.nazwa, ekwipunek.idEkwipunku from kreatura left join ekwipunek on kreatura.idKreatury = ekwipunek.idKreatury where ekwipunek.idKreatury is null;

```
