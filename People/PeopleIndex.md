# Lista Osób

```dataview
table Imie, Nazwisko, file.path as "Path"
where startswith(file.name,"@")=true
sort Nazwisko asc, Imie asc
```
