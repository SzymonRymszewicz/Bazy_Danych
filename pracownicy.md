![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/eeb35279-1462-43a7-8b4d-97a519a7551d)

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



```

