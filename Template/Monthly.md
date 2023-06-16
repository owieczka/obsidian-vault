---
tag: 🔧
---
# <% monthPL(tp.file.title,0) %> <% tp.date.weekday("YYYY", 0, tp.file.title, "YYYY-MM") %>
[[<% tp.date.now("YYYY-MM", "P-1M", tp.file.title, "YYYY-MM" ) %>| ⇦ <% monthPL(tp.file.title,"P-1M")%> <% tp.date.now("YYYY", "P-1M", tp.file.title, "YYYY-MM" ) %>]] || [[<% tp.date.now("YYYY-MM", "P+1M", tp.file.title, "YYYY-MM" ) %>|<% monthPL(tp.file.title,"P+1M")%> <% tp.date.now("YYYY", "P+1M", tp.file.title, "YYYY-MM" ) %> ⇨]] 

<% tp.file.include("[[Calendar]]") %>
## Intencje
---
- 

## Zadania na miesiąć 🗓️
---
- 

## Podsumowanie
---
- 


<%*
//P1Y
function monthPL(title, offset) {
	const month = tp.date.now("MM", offset, title, "YYYY-MM");
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
%>