### Zadanie 1.

-

### Zadanie 2.

## a)
```sql
SELECT rodzaj, group_concat(nazwa separator ' ') FROM kreatura GROUP BY rodzaj;
```

## b)
```sql
SELECT s.id_sektora, count(ew.sektor) FROM etapy_wyprawy ew RIGHT JOIN sektor s ON ew.sektor=s.id_sektora GROUP BY s.id_sektora;
```

## a)
```sql
SELECT k.nazwa, IF(count(u.id_wyprawy)=0, 'nie brał udziału w wyprawie', 'brał udział w wyprawie') AS czy_wyprawa FROM kreatura k LEFT JOIN uczestnicy u ON u.id_uczestnika=k.idKreatury;
```

## b)
```sql
```

### Zadanie 4.

## a)
```sql
```

## b)
```sql
```














