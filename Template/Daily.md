# <% dayPL(tp.file.title,0) %>, <% tp.file.title %> 🔧
<< [[<% tp.date.now("YYYY-MM-DD", -1, tp.file.title, "YYYY-MM-DD") %>]] || [[<% tp.date.now("YYYY-MM-DD", 1, tp.file.title, "YYYY-MM-DD") %>]]>>

## Tasks due today
Pilne zadania - automatycznie agregowane innych notatek
```dataviewjs
const tasksFromOtherNotes = dv.pages().file.tasks
  .where(t => !t.completed)
  .where(t => t.text.includes("{{date:YYYY-MM-DD}}"));
if(tasksFromOtherNotes.length==0) dv.paragraph("*Dziś nie ma żadnych pilnych zadań*")
else dv.taskList(tasksFromOtherNotes)
```

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

## Meetings
Dzisiejsze spotkania - automatyczne agregowane z innych notatek
```dataviewjs
const meetings = dv.pages()
  .where(t => t.file.name.includes("{{date:YYYYMMDD}}"))
  .map(t => {
    let link = t.file.link;
    link.display = t.file.name;
    return link
    //return t.file.lists[0].section;
    //return t.file.lists[0]
  });
if(meetings.length==0) dv.paragraph("*Dziś nie ma żadnych zaplanowanych spotkań*")
else dv.list(meetings);
```


## TimeLog
Daily planer

## Zadania na przyszłość

- 

## Notes
Inbox

<%*
function dayPL(title, offset) {
const day = tp.date.now("ddd", offset, title, "YYYY-MM-DD");
dayName = "Dzień";
if(day==="Mon") dayName = "Poniedziałek";
if(day==="Tue") dayName = "Wtorek";
if(day==="Wed") dayName = "Środa";
if(day==="Thu") dayName = "Czwartek";
if(day==="Fri") dayName = "Piątek";
if(day==="Sat") dayName = "Sobota";
if(day==="Sun") dayName = "Niedziela";
return dayName;
}
%>