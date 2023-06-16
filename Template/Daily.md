---
tag: 🔧
---
# <% dayPL(tp.file.title,0) %>, <% tp.file.title %>
⇦ [[<% tp.date.now("YYYY-MM-DD", -1, tp.file.title, "YYYY-MM-DD") %>]] || [[<% tp.date.now("YYYY-MM-DD", 1, tp.file.title, "YYYY-MM-DD") %>]] ⇨
[[<% tp.date.now("YYYY", 0, tp.file.title, "YYYY-MM-DD") %> |<% tp.date.now("YYYY", 0, tp.file.title, "YYYY-MM-DD") %>]] » [[<% tp.date.now("YYYY-MM", 0, tp.file.title, "YYYY-MM-DD") %> |<% monthPL(tp.file.title,0) %>]] » [[<% tp.date.weekday("YYYY[-W]ww", 0, tp.file.title, "YYYY-MM-DD" ) %>|Tydzień <% tp.date.weekday("ww", 0, tp.file.title, "YYYY-MM-DD" ) %> ]]
<div class="timeline timeline--day"><% tp.file.include("[[Timeline]]") %></div>

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
---
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


## TimeLog 🗓️
---
Daily planer

## Zadania na przyszłość ☑️
---
- 

## Notes 📝
---
Inbox

<%*
function monthPL(title, offset) {
const month = tp.date.now("MM", offset, title, "YYYY-MM-DD");
monthName = "Miesiąc";
if(month==="01") monthName = "Styczeń";
if(month==="02") monthName = "Luty";
if(month==="03") monthName = "Marzec";
if(month==="04") monthName = "Kwiecień";
if(month==="05") monthName = "Maj";
if(month==="06") monthName = "Czerwiec";
if(month==="07") monthName = "Lipiec";
if(month==="08") monthName = "Sierpień";
if(month==="09") monthName = "Wrzesień";
if(month==="10") monthName = "Październik";
if(month==="11") monthName = "Listopad";
if(month==="12") monthName = "Grudzień";
return monthName;
}

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