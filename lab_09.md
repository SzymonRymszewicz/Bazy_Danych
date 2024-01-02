![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/c64cbc08-b32e-43e9-95c3-6fe863960010)

**Rozwiązanie:**

```sql

DELIMITER //
CREATE TRIGGER kreatura_before_insert
BEFORE INSERT ON kreatura
FOR EACH ROW
BEGIN
	IF NEW.waga <= 0 THEN
		SET NEW.waga = 1; 
	END IF;
END
// 

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/bc02c8fe-a38a-406b-9dca-1892f9ff24a8)

```sql

DELIMITER //
CREATE TRIGGER kreatura_after_delete
BEFORE DELETE ON wyprawa
FOR EACH ROW
BEGIN
	INSERT INTO archiwum_wypraw values(old.id_wyprawy, old.nazwa, old.data_rozpoczecia, old.data_zakonczenia, old.kierownik);
END
// 

```

![image](https://github.com/SzymonRymszewicz/Bazy_Danych/assets/147385726/21c4f012-99ed-4c1d-81e3-7fcb8d0d31e9)

```sql



```

