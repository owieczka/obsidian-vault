---
aliases: [@XX]
---
# Jan Marek Kowalski
**Gdzie poznałem:** xxx
<% await tp.file.move("/People/"+tp.file.title) %>

## Dane osobowe
Imie::Jan
Nazwisko::Marek

## Wykształcenie

## Praca zawodowa
Kiedy        | Gdzie 
------------ | ---
             |     |

## Spotkania
```dataviewjs
const link = dv.current().file.link
//dv.paragraph(link)
const meetings = dv.pages()
  .where(t => t.file.outlinks.includes(link));

if(meetings.length==0) dv.paragraph("*Nie ma żadnych wzmianek o tej osobie*")
else dv.list(meetings.map(t=> t.file.link));
```