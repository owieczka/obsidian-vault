| w | Pon | Wt | Śr | Czw | Pt | Sob | Niedz |
|---|---|---|---|---|---|---|---|
<% calendar(tp.file.title,0) %>
<%*
function calendar(title,offset) {
	let day = 01;
	let month = tp.date.now("MM", offset, title, "YYYY-MM");
	let year = tp.date.now("YYYY", offset, title, "YYYY-MM");
	let off = 0;
	for(off=0;off>-7;off--) {
		const dayName = tp.date.now("ddd", off, `${year}-${month}-${day}`, "YYYY-MM-DD");
		if(dayName=="Mon") break;
	}
	let output = [];
	for(let jdx=0;jdx<5;jdx++) {
		let weak = tp.date.now("ww", off, `${year}-${month}-${day}`, "YYYY-MM-DD");
		let link = tp.date.now("YYYY[-W]ww", off, `${year}-${month}-${day}`, "YYYY-MM-DD");
		output.push(`| [${weak}](${link}) `);
		for(let idx=0;idx<7;idx++) { //look over 7 day week
			let day_local = tp.date.now("DD", off+idx, `${year}-${month}-${day}`, "YYYY-MM-DD");
			let link_local = tp.date.now("YYYY-MM-DD", off+idx, `${year}-${month}-${day}`, "YYYY-MM-DD");
			let month_local = tp.date.now("MM", off+idx, `${year}-${month}-${day}`, "YYYY-MM-DD");
			if(month_local==month) {
				output.push(`| [${day_local}](${link_local}) `);
			} else {
			  output.push(`| -- `);
			}
		}
		output.push(`|\n`);
		off=off+7;
	}
	
	return output.join("");
}
%>