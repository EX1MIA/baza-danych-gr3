## Lab_6
Pojęcia poza zadaniami:
```sql
SELECT SUM(waga) FROM kreatura;
# SUM - suma danych wartości z "waga"
SELECT COUNT(waga) FROM kreatura;
# COUNT - ilość danych wartości z "waga"

# SELECT nazwa, rodzaj, waga, ilosc, ilosc * waga FROM zasob;
# SELECT rodzaj, SUM(ilosc * waga) FROM waga GROUP BY rodzaj;

Left Join 
```

### Zad 1.
#### a)
```sql
SELECT AVG(waga) FROM kreatura;
# AVG - średnia danych wartości z "waga"
```
#### b)
```sql
SELECT COUNT(rodzaj), AVG(waga) FROM kreatura GROUP BY rodzaj;
# Grupowanie w kolumnie rodzaj, średnia waga i ilość rodzajów dla każdego rodzaju
```
#### c)
```sql
SELECT AVG(wiek) FROM kreatura;
```

### Zad 2.
#### a)
```sql
SELECT SUM(waga) FROM zasob GROUP BY rodzaj;

SELECT nazwa, rodzaj, waga, ilosc, ilosc * waga FROM zasob;
SELECT rodzaj, SUM(ilosc * waga) FROM waga GROUP BY rodzaj;
```
#### b)
```sql
SELECT AVG(waga) FROM zasob GROUP BY nazwa HAVING COUNT(waga) >= 4 AND SUM(waga) >= 10;
```
#### c)
```sql

```

### Zad 3.
#### a)
```sql
SELECT * FROM kreatura, ekwipunek WHERE kreatura.idKreatury = ekwipunek.idKreatury;
```
#### b)
```sql

```
#### c)
```sql

```








#### a)
```sql


```
#### b)
```sql
SELECT nazwa, dataUr FROM kreatura WHERE ekwipunek IS NOT NULL LIMIT 5;
```
#### c)
```sql

```

### Zad 5.
#### a)
```sql
SELECT k.nazwa, k.rodzaj, AVG(e.ilosc * z.waga) FROM kreatura INNER JOIN ekwipunek e ON k.idKreatury=e.idKreatury INNER JOIN zasob z ON z.idZasobu=e.idZasobu WHERE k.rodzaj NOT IN ('malpa','waz') AND e.ilosc 30;
```
#### b)
```sql
SELECT a.nazwa, a.rodzaj, a.dataUr FROM kreatura a, (SELECT MIN(dataUr) min, MAX(dataUr) max FROM kreatura GROUP BY rodzaj) b WHERE b.min - a.dataUr OR b.max=a.dataUr;
```
