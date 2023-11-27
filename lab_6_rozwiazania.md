## Lab_6

### Zad 1.
#### a)
```sql
# Jeżeli wybrana baza to baza imienna:
CREATE TABLE kreatura AS SELECT * FROM wikingowie.kreatura;
CREATE TABLE ekwipunek AS SELECT * FROM wikingowie.ekwipunek;
CREATE TABLE zasob AS SELECT * FROM wikingowie.zasob;
# Tworzy tabele kreatura/zasob/ekwipunek poprzez wybranie danych z tebeli wikingowie
```
#### b)
```sql
SELECT * FROM zasob;
```
#### c)
```sql
SELECT * FROM zasob WHERE jedzenie = TRUE;
```
#### d)
```sql
SELECT nazwa FROM kreatura WHERE idKreatury in (1, 3, 5);
```

### Zad 2.
#### a)
```sql
SELECT nazwa FROM kreatura WHERE NOT rodzaj = "wiedzma" AND waga > 50;
```
#### b)
```sql
SELECT nazwa FROM zasoby WHERE waga BETWEEN 2 AND 5;
```
#### c)
```sql
SELECT nazwa FROM kreatura WHERE KEYWORD LIKE '%a%' AND KEYWORD LIKE '%b%';
```

### Zad 3.
#### a)
```sql
SELECT nazwa FROM zasob WHERE MONTH = "lipiec" AND MONTH = "sierpien";
```
#### b)
```sql

```
#### c)
```sql
SELECT nazwa FROM kreatura WHERE kreatura ORDER BY dataUr = 5;
```

### Zad 4.
#### a)
```sql
SELECT DISTINCT rodzaj FROM kreatura;
SELECT DISTINCT(rodzaj) FROM kreatura;
```
#### b)
```sql
SELECT CONCAT(idKreatury, ' ', nazwa) FROM kreatura;
# Concat łaczy ze sobą dane z idKreatury, " " (spację) i nazwa, np. "1 Bjorn, 2 Drozd"
```
#### c)
```sql
SELECT CONCAT(ilosc * waga) AS "calkowita waga" FROM zasob WHERE dataPozyskania BETWEEN "2000-01-01" AND "2006-12-30";
```

### Zad 5.
#### a)
```sql

```
#### b)
```sql

```
#### c)
```sql

```
