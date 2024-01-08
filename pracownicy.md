![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/91916141-0025-45b6-b7c6-eb7dc923808f)

**Rozwiązanie:**

```sql

select imie, year(data_urodzenia) from pracownik;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/61aac44f-fbc6-49b3-93df-fba68bb6fad9)

**Rozwiązanie:**

```sql

select imie, nazwisko, year(curdate()) - year(data_urodzenia) from pracownik;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/38a07199-ac13-4242-8262-69e3a7f91e32)

**Rozwiązanie:**

```sql

select d.nazwa, count(p.dzial) from dzial d inner join pracownik p on p.dzial = d.id_dzialu group by d.nazwa;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/503f0cc6-e08a-45ba-923e-5ea34eadc051)

**Rozwiązanie:**

```sql

select k.nazwa_kategori, count(t.kategoria) from kategoria k inner join towar t on k.id_kategori = t.kategoria group by k.nazwa_kategori;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/69d2dc9e-4901-4a14-90d3-7d0eca4ae513)

**Rozwiązanie:**

```sql

select k.nazwa_kategori, group_concat(t.nazwa_towaru) from kategoria k inner join towar t on k.id_kategori = t.kategoria group by k.nazwa_kategori;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/f21940a6-f9c1-4577-8ac7-676d198530a2)

**Rozwiązanie:**

```sql

select round(avg(pensja), 2) from pracownik;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/c8606bee-cc9d-4461-b3b2-2f1f9279315d)

**Rozwiązanie:**

```sql

select round(avg(pensja), 2) from pracownik where year(curdate()) - year(data_zatrudnienia) >= 5;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/8bf4a379-a09a-4232-ab74-b114aa01c786)

**Rozwiązanie:**

```sql

select towar, count(zamowienie) from pozycja_zamowienia group by towar order by count(zamowienie) desc limit 10;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/b0435ede-3dec-43b8-9089-b09cb4961b1d)

**Rozwiązanie:**

```sql

select z.numer_zamowienia, sum(pz.ilosc * pz.cena) from zamowienie z 
inner join pozycja_zamowienia pz on z.id_zamowienia = pz.zamowienie 
where year(z.data_zamowienia)=2017 and quarter(z.data_zamowienia) = 1 group by z.id_zamowienia;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/99286e7b-6bcd-4aa6-a479-9e0ac50e10e8)

**Rozwiązanie:**

```sql

select p.imie, p.nazwisko, sum(pz.ilosc * pz.cena) as wartosc from zamowienie z 
inner join pozycja_zamowienia pz on z.id_zamowienia = pz.zamowienie 
inner join pracownik p on p.id_pracownika = z.pracownik_id_pracownika
group by p.id_pracownika
order by wartosc desc;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/514dda15-71ae-4d5a-833a-187c1902bae6)

**Rozwiązanie:**

```sql

select d.nazwa, min(p.pensja), max(p.pensja), avg(p.pensja) from pracownik p
inner join dzial d on p.dzial = d.id_dzialu
group by d.id_dzialu;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/e9eae21c-f1a8-405c-91de-3fa51756da1f)

**Rozwiązanie:**

```sql

select k.pelna_nazwa, z.numer_zamowienia, sum(pz.ilosc * pz.cena) as wartosc
from zamowienie z
inner join pozycja_zamowienia pz on z.id_zamowienia = pz.zamowienie
inner join klient k on k.id_klienta = z.klient
group by k.id_klienta, z.id_zamowienia
order by wartosc desc limit 10;

```

