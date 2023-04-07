# Spotkanie z [[@JanKowalski| Janem Kowalskim]]


## Zadania
Wszystkie zadanie oznaczone [[1on1JK]]
```dataviewjs
const tasksFromOtherNotes = dv.pages().file.tasks
  .where(t => !t.completed)
  .where(t => t.text.includes("1on1HW"));
if(tasksFromOtherNotes.length==0) dv.paragraph("*Nie ma żadnych  zadań*")
else dv.taskList(tasksFromOtherNotes)
```

## Notki

Notatki na następne spotkanie