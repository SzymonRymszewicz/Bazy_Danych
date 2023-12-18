![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/098e5672-d900-4cfa-8447-40d2eb75d33d)

**Rozwiązanie:**

```sql

insert into kreatura select * from wikingowie.kreatura;
create table uczestnicy like wikingowie.uczestnicy;
insert into uczestnicy select * from wikingowie.uczestnicy;
create table etapy_wyprawy like wikingowie.etapy_wyprawy;
insert into etapy_wyprawy select * from wikingowie.etapy_wyprawy;
create table sektor like wikingowie.sektor;
insert into sektor select * from wikingowie.sektor;
create table wyprawa like wikingowie.wyprawa;
insert into wyprawa select * from wikingowie.wyprawa;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/fc4aeaf7-3435-4d0c-ae90-806ba9dcc78a)

**Rozwiązanie:**

```sql

select wyprawa.nazwa, count(uczestnicy.id_uczestnika), group_concat(kreatura.nazwa) from wyprawa 
inner join uczestnicy on wyprawa.id_wyprawy = uczestnicy.id_wyprawy
inner join kreatura on kreatura.idKreatury = uczestnicy.id_uczestnika group by wyprawa.nazwa;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/c2ce839c-5d8a-4258-814a-0ab874e3dcb9)

```sql

select s.id_sektora, ifnull(ew.sektor, 0)
from etapy_wyprawy ew
right join sektor s on ew.sektor = s.id_sektora group by s.id_sektora;

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/bb61afaf-22d7-42dd-b1f3-cb9a73ddbe47)

```sql

select idWyprawy, sum(length(dziennik)) from etapy_wyprawy group by idWyprawy;

```

