---
tag: 🔧
---
# <% monthEN(tp.file.title,0) %> <% tp.date.weekday("YYYY", 0, tp.file.title, "YYYY-MM") %>
[[<% tp.date.now("YYYY-MM", "P-1M", tp.file.title, "YYYY-MM" ) %>| ⇦ <% monthEN(tp.file.title,"P-1M")%> <% tp.date.now("YYYY", "P-1M", tp.file.title, "YYYY-MM" ) %>]] || [[<% tp.date.now("YYYY-MM", "P+1M", tp.file.title, "YYYY-MM" ) %>|<% monthEN(tp.file.title,"P+1M")%> <% tp.date.now("YYYY", "P+1M", tp.file.title, "YYYY-MM" ) %> ⇨]] 

<% tp.file.include("[[CalendarEN]]") %>
## Intentions
---
- 

## Tasks for Month 🗓️
---
- 

## Summary
---
- 


<%*
//P1Y
function monthEN(title, offset) {
	const month = tp.date.now("MM", offset, title, "YYYY-MM");
	monthName = "Month";
	if(month==="01") monthName = "January";
	if(month==="02") monthName = "February";
	if(month==="03") monthName = "March";
	if(month==="04") monthName = "April";
	if(month==="05") monthName = "May";
	if(month==="06") monthName = "June";
	if(month==="07") monthName = "July";
	if(month==="08") monthName = "August";
	if(month==="09") monthName = "September";
	if(month==="10") monthName = "November";
	if(month==="11") monthName = "October";
	if(month==="12") monthName = "December";
	return monthName;
}
%>