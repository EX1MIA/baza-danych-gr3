## Zadanie 3 , b  
#### Sposób 1

```sql
SELECT * FROM statek 
WHERE data_wodowania >= '1901-01-01' 
AND data_wodowania <= '2000-12-31' 
DESC statek;
```
#### Sposób 2
```sql
SELECT * FROM statek 
WHERE data_wodowania BETWEEN '1901-01-01' AND '2000-12-31' 
DESC statek;
```
#### Sposób 3
```sql
SELECT * FROM statek 
WHERE YEAR(data_wodowania) BETWEEN '1901-01-01' AND '2000-12-31' 
# month, day, hour, minute, second
# select hour(now());
# select now(); data i czas
# select curdate(); tylko bierząca data
DESC statek;
```

```sql
SELECT * FROM statek;
UPDATE statek
SET max_ladownosc = 0.7 * max_ladownosc; 
```

## Zadanie 3 , c

```sql
ALTER TABLE postac MODIFY wiek INT UNSIGNED CHECK (wiek < 1000);
ALTER TABLE postac ADD CHECK (wiek < 1000);
#sprawdzenie czy instrukcja check jest w składzie tabel
SHOW CREATE TABLE postac;
SELECT FROM postac;
# test działania check na kolumnie wiek
UPDATE postac SET wiek=1000 WHERE nazwa='Drozd';
```

## Zadanie 4 , a
```sql
INSERT INTO postac VALUES(default, Loko)
```

## Zadanie 4 , b

#### Sposób 1
```sql
# stworzenie tabeli na wzór innej, bez danych, z kluczem glownym, bez kluczy obcych
CREATE TABLE marynarz LIKE postac;

INSERT INTO marynarz SELECT * FROM postac WHERE statek IS NOT NULL;  
```

#### Sposób 2

```sql
# Stworzenie tabeli na podstawie zapytania
# select z danymi, bez kluczy
CREATE TABLE marynarz2 AS SELECT id_postaci, nazwa, statek FROM postac;
SELECT * FROM marynarz2;
# Sposób ten nie przenosi checka i klucza
```

## Zadanie 5

#### A
```sql
DELETE ALL postac FROM statek;
```

#### B
```sql

```

#### C
```sql

```

#### D
```sql
DROP TABLE statek;
```

#### E
```sql
CREATE TABLE zwierz (zwierz_id int primary key auto_increment, nazwa varchar(50), wiek int);
```

#### F
```sql

```
