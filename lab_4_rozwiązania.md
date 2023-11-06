# Tytuł
## Poziom 1
###### Poziom 6

Lista zadań do wykonania:
* todo 1
* todo 2
  * todo 2.1

1. Rozdzial 1
2. Rozdzial 2  
  2.1 Rozdzial 2.1

**Listning 1** -> pogrubienie  
_Listning 2_ -> kursywa  
**_Listning 3_** -> kursywa i pogrubienie


Poniżej to blok kodu:
```sql
SELECT * FROM osoba;
```

Kod umieszczamy liniowo. Polecenie `SELECT` oznacza wybranie danych z bazy.

show tables; -> pokazywanie tabeli
describe (nazwa tabeli); -> pokazanie danej konkretnej tabeli z tabel

🔽 **_Rozwiazania:_** 🔽

▶️ 1. Zadanie  
* Stwórz tabelę postac z następującymi polami:
```sql
CREATE TABLE postac (id_postaci int primary key auto_increment, nazwa varchar(40), rodzaj enum("wiking","ptak","kobieta"), data_ur date, wiek int unsigned);
```
* Do tabeli postać dodaj rekordy gdzie kolumna nazwa to ("Bjorn","Drozd","Tesciowa"): 
```sql
INSERT INTO postac VALUES(default,"Bjorn","wiking","1700-10-23",323);

INSERT INTO postac VALUES(default,"Drozd","ptak","1760-11-23",263);

INSERT INTO postac VALUES(default,"Tesciowa","kobieta","1730-9-23",293);
```
* Zmodyfikuj wiek tesciowej o 88 lat:
```sql
UPDATE postac SET wiek=88 WHERE nazwa="Tesciowa";
```

▶️ 2. Zadanie  
* Stwórz tabelę walizka:
```sql
CREATE TABLE walizka (id_walizki int primary key auto_increment, pojemnosc int unsigned, kolor enum("rozowy","czerwony","teczowy","zolty"), id_wlasciciela int, foreign key(id_wlasciciela) references postac(id_postaci) on delete cascade);
```
* Dodaj do pola kolor wartość domyślną - różowy:
```sql
ALTER TABLE walizka ADD [COLUMN] kolor default("rozowy");
```

▶️ 3. Zadanie
* Stwórz tabele izba:
```sql
CREATE TABLE izba (adres_budynku int primary key auto_increment, nazwa_izby int primary key auto_increment, metraz int unsigned, wlasciciel int, foreign key(wlasciciel) references postac(id_postaci) on delete set null)
```
* Dodaj pole kolor izby po polu metraz;
```sql
ALTER TABLE izba ADD [COLUMN] kolor_izby AFTER metraz;
```
