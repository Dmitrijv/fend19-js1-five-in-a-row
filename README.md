# FEND19 - JavaScript 1 - Five In a Row

Du skall med hjälp av HTML, CSS och Javascript göra ett fem-i-rad-spel.\
Du skall skapa en HTML-sida, som när den visas i webbläsaren innehåller:\
En rubrik med spelets namn (du kan välja ett eget namn om du vill)\
Ett spelbräde.\
Ett textfält (p-tagg) som berättar vems tur det är att göra ett drag, O eller X.\
Ett textfält (p-tagg) som berättar hur många drag som har gjorts totalt.\
Spelbrädet skall bestå av ett rutfält med knappar (button).\
Det skall vara åtminstone 25 knappar i höjdled och 25 knappar i sidled stort.\
Den spelare vars tur det är kan klicka på en knapp som inte redan blivit klickad på.\
När spelaren gör det skall spelaren vars tur det är få sin markering på den knappen.\
Om det är X tur att klicka, så kan denne alltså klicka på en knapp, som då får markeringen “X”.\
Då går turen över till O.\
När en knapp väl blivit klickad på så skall det inte hända något om någon av spelarna klickar på den igen.\
Du får styla spelet på vilket sätt du själv vill.

### För G-nivå

Du kan skapa spelbrädet som du vill, antingen genom att skriva HTML, eller skapa elementen med Javascript.\
Ditt program skall hålla reda på vems tur det är, och hur många drag som har gjorts sammanlagt.\
Detta skall visas i varsitt textfält (p-tagg).\
Du kan använda bokstäverna O och X som märken för kryss och cirkel.\
Du ska ha använt minst 4 CSS-klasser när du har stylat spelet. Varje klass måste innehålla minst en deklaration.

### För VG-nivå

Minst uppfyllt kraven för godkänt.\
Du måste ha skapat själva spelbrädet (alltså knapparna) med hjälp av Javascript.\
Du skall ha en eller flera variabler som gör att du kan ändra på antal rutor på spelbrädet.\
Märkena, alltså X och O, skall antingen vara stylade med en färg,\
eller använda en emoji istället för text (t.ex. ❌ ⭕️, eller annan valfri om du tycker det är roligare),\
eller använda sig av en bild av något slag.\
Varje gång en spelare gjort ett drag skall ditt program kontrollera om någon av spelarna har vunnit\
(alltså fått minst 5 symboler i rad horisontellt, vertikalt eller diagonalt).\
Om någon av spelarna har vunnit skall detta presenteras i ett eget textfält, och det skall inte gå att spela vidare.
