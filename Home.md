## Osoby
[[PeopleIndex |Lista Osób]]

---
## Cele

### Kwiecień 2023
- Wgrać moj Vault na GitHuba

---
## Notki
To można umieścić różne notatki

---
## Artykuły
Miejsca na artykuły naukowe

---
## Projekty

[[Projects-Ideas]]

### Aktualnie
[[Organizacja_Obsydian]]

---
## Spotkania
### Stare spotkania
[[Meeting-2023 |2023]]

[[Meeting-202303|03 - Marzec]]

[[Spotkania_z_JanemKowalskim]]


### Aktualne
Spotkania które sie już odbyły ale trzeba przejżeć stan zadań

[[20230323_1100-Test]]

### Przyszłe

[[20230408_0900-Dom]]

---

## NextAction
```dataviewjs
const tasksFromOtherNotes = dv.pages().file.tasks
  .where(t => !t.completed)
  .where(t => t.text.includes("NextAction"));
if(tasksFromOtherNotes.length==0) dv.paragraph("*Nie ma żadnych zaplanowanych następnych działań*")
else dv.taskList(tasksFromOtherNotes)
```

## WaitingFor
```dataviewjs
const tasksFromOtherNotes = dv.pages().file.tasks
  .where(t => !t.completed)
  .where(t => t.text.includes("WaitingFor"));
if(tasksFromOtherNotes.length==0) dv.paragraph("*Nie czekam na nikog aby do mnie wrócił*")
else dv.taskList(tasksFromOtherNotes)
```

## SomeDayMaybe
```dataviewjs
const tasksFromOtherNotes = dv.pages().file.tasks
  .where(t => !t.completed)
  .where(t => t.text.includes("SomeDayMaybe"));
if(tasksFromOtherNotes.length==0) dv.paragraph("*Nie mam żadnych pomysłów na przyszłość*")
else dv.taskList(tasksFromOtherNotes)
```

---
## Types of content

`@:` People
`&:` Firmy

## Task and Markers

```
[ ] Task
[x] Task dane
[/] Partialy complited
[-] Canceled
[<] Scheduled - Planed in calendar
[>] Moved elsware

- [?] Test 
- [!] Im
- [*] 3
- ["] 4
- [l] 5
- [b] 6
- [i] 6
- [S] 7
- [I] 8
- [p] 8
- [c] 8
- [f] 0393
- [k] 4
- [w] 5
- [u] 5
- [d] dd
```

- [ ] Task
- [x] Task dane
- [/] Partialy complited
- [-] Canceled
- [<] Scheduled - Planed in calendar
- [>] Moved elsware

## Help
[[Dataview]]

## Review
Weekend
- Wszystkie wiszące karty
- Wszystkie wiszące spotkania
- Stan projektów
- Maile
- Otwarte Karty w przeglądarce

Monthly
- Nowe pomysły
- Nowe projekty

[[Tasks]]
