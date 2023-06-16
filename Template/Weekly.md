---
tag: 🔧
---
# <% tp.date.weekday("[Tydzień] ww", 0, tp.file.title, "YYYY-[-W]ww") %>: <% tp.date.weekday("YYYY-MM-DD", 0, tp.file.title, "YYYY-[-W]ww") %> - <% tp.date.weekday("YYYY-MM-DD", 6, tp.file.title, "YYYY-[-W]ww") %>
[[<% tp.date.weekday("YYYY[-W]ww", -7, tp.file.title, "YYYY-[-W]ww" ) %>| ⇦ Tydzień <% tp.date.weekday("ww", -7, tp.file.title, "YYYY-[-W]ww" ) %> ]] || [[<% tp.date.weekday("YYYY[-W]ww", 7, tp.file.title, "YYYY-[-W]ww" ) %>| Tydzień <% tp.date.weekday("ww", 7, tp.file.title, "YYYY-[-W]ww" ) %> ⇨]] 
[[<% tp.date.now("YYYY", 0, tp.file.title, "YYYY-[-W]ww") %> |<% tp.date.now("YYYY", 0, tp.file.title, "YYYY-[-W]ww") %>]] » [[<% tp.date.now("YYYY-MM", 0, tp.file.title, "YYYY-[-W]ww") %>|<% monthPL(tp.file.title,0) %>]]
[[<% tp.date.weekday("YYYY-MM-DD", 0, tp.file.title, "YYYY-[-W]ww" ) %>|<% dayPL(tp.file.title,0) %> <% tp.date.weekday("DD", 0, tp.file.title, "YYYY-[-W]ww" ) %>]] · [[<% tp.date.weekday("YYYY-MM-DD", 1, tp.file.title, "YYYY-[-W]ww" ) %>|<% dayPL(tp.file.title,1) %> <% tp.date.weekday("DD", 1, tp.file.title, "YYYY-[-W]ww" ) %>]] · [[<% tp.date.weekday("YYYY-MM-DD", 2, tp.file.title, "YYYY-[-W]ww" ) %>|<% dayPL(tp.file.title,2) %> <% tp.date.weekday("DD", 2, tp.file.title, "YYYY-[-W]ww" ) %>]] · [[<% tp.date.weekday("YYYY-MM-DD", 3, tp.file.title, "YYYY-[-W]ww" ) %>|<% dayPL(tp.file.title,3) %> <% tp.date.weekday("DD", 3, tp.file.title, "YYYY-[-W]ww" ) %>]] · [[<% tp.date.weekday("YYYY-MM-DD", 4, tp.file.title, "YYYY-[-W]ww" ) %>|<% dayPL(tp.file.title,4) %> <% tp.date.weekday("DD", 4, tp.file.title, "YYYY-[-W]ww" ) %>]] · [[<% tp.date.weekday("YYYY-MM-DD", 5, tp.file.title, "YYYY-[-W]ww" ) %>|<% dayPL(tp.file.title,5) %> <% tp.date.weekday("DD", 5, tp.file.title, "YYYY-[-W]ww" ) %>]] · [[<% tp.date.weekday("YYYY-MM-DD", 6, tp.file.title, "YYYY-[-W]ww" ) %>|<% dayPL(tp.file.title,6) %> <% tp.date.weekday("DD", 6, tp.file.title, "YYYY-[-W]ww" ) %>]]^<% tp.date.weekday("[W]ww", 0, tp.file.title, "YYYY-[-W]ww" ) %>
<div class="timeline timeline--week"><% tp.file.include("[[Timeline]]") %></div>

## Intencje

## Zadania na tydzień

- 

## Habbits

Czynność             | <% tp.date.weekday("DD", 0, tp.file.title, "YYYY-[-W]ww" ) %>| <% tp.date.weekday("DD", 1, tp.file.title, "YYYY-[-W]ww" ) %>| <% tp.date.weekday("DD", 2, tp.file.title, "YYYY-[-W]ww" ) %>| <% tp.date.weekday("DD", 3, tp.file.title, "YYYY-[-W]ww" ) %>| <% tp.date.weekday("DD", 4, tp.file.title, "YYYY-[-W]ww" ) %>| <% tp.date.weekday("DD", 5, tp.file.title, "YYYY-[-W]ww" ) %>| <% tp.date.weekday("DD", 6, tp.file.title, "YYYY-[-W]ww" ) %>| <% tp.date.weekday("DD", 7, tp.file.title, "YYYY-[-W]ww" ) %>
---------------------|---|---|---|---|---|---|---|---
Migany               | _ | _ | _ | _ | _ | _ | _ | _ 
Zadania dla dzieci   | _ | _ | _ | _ | _ | _ | _ | _ 
Granie na pianinie   | _ | _ | _ | _ | _ | _ | _ | _ 
Logic Blocks         | _ | _ | _ | _ | _ | _ | _ | _ 
Czytanie z Maksiem   | _ | _ | _ | _ | _ | _ | _ | _ 

## Podsumowanie

<%*
function monthPL(title, offset) {
const month = tp.date.now("MM", offset, title, "YYYY-[-W]ww");
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
const day = tp.date.now("ddd", offset, title, "YYYY-[-W]ww");
dayName = "Dzień";
if(day==="Mon") dayName = "Pon.";
if(day==="Tue") dayName = "Wt.";
if(day==="Wed") dayName = "Śr.";
if(day==="Thu") dayName = "Czw.";
if(day==="Fri") dayName = "Pt.";
if(day==="Sat") dayName = "Sob.";
if(day==="Sun") dayName = "Niedz.";
return dayName;
}
%>