# Jan Maciej Kowalski

## Dane osobowe
**Imie**::Jan
Nazwisko::Kowalski
e-mail::jankowalski@gmail.com

## Wykształcenie
mgr inż. Telekomunikacji z Politechniki Warszawskiej

## Praca Zawodowa

## Spotkania
```dataviewjs
const link = dv.current().file.link
//dv.paragraph(link)
const meetings = dv.pages()
  .where(t => t.file.outlinks.includes(link));

if(meetings.length==0) dv.paragraph("*Nie ma żadnych wzmianek o tej osobie*")
else dv.list(meetings.map(t=> t.file.link));
```