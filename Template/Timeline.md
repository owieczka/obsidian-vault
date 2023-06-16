<%* 
function monthPL(month) {
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

let title = tp.file.title; 
let startDate = ""; 
if (title.match(/^[12][019]\d{2}[01]\d[0123]\d$/)) { 
	startDate = tp.date.now("MM-DD-YYYY", 0, title); 
} else if (title.match(/^[12][019]\d{2}-W[01]\d$/)) {
	startDate = tp.date.now("MM-DD-YYYY", 0, title, "YYYY-[W]ww"); 
} else { 
	startDate = moment().format("MM-DD-YYYY"); 
} 
var year = moment(startDate).format("YYYY");
var monthStart = 0;
var monthBlocks = "";
var monthLabels = "";
var marker = "";
for(let i = 1; i <= 12; i++) { 
	let daysInMonth = moment(year + "-" + i).daysInMonth();
	let monthName = moment(year + "-" + i).format("MMMM");
	let monthNamePL = monthPL(moment(year + "-" + i).format("MM"));
	monthBlocks += `<rect class="month-block month-block--${monthName}" x="${monthStart * 10}" width="${daysInMonth * 10}" height="25"></rect>`; monthLabels += `<text class="month-label month-label--${monthName}" fill="#747474" x="${monthStart * 10}" y="120">${monthNamePL}</text>`;
	if (moment(startDate).format("M") == i) { 
		marker = monthStart + parseInt(moment(startDate).format("D")); 
	}
	monthStart += daysInMonth + 1; } 
%>
<svg class="year-timeline year-timeline--<%year%>" viewBox="0 -20 3760 150"> <title>Timeline <%year%></title> <g class='bars'> <% monthBlocks %> </g> <g class='labels' style="font-size:50px;" text-anchor="start"> <% monthLabels %> </g> <g class='markers'> <circle class="day-marker" cx="<%`${marker * 10}`%>" cy="14" r="15" stroke="black" fill="white" /> <rect class="week-marker" x="<%`${marker * 10}`%>" width="70" height="25" /> </g> </svg>