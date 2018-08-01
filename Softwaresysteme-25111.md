# Inhalt
* 01671 Datenbanken 1
* 01801 Betriebssysteme und Rechnernetze

### Prüfer: 
Dr. Wilkes, Dr. Behr (Beisitzer)

### Datum, Ort
13.Juli 2018, On-Campus Pruefung (Haus 3, Etage 2, Abschnitt H, Raum 5)

# 1671

<dl>
<dt>Was meint Datenunabhängigkeit?</dt>
<dd>Es ging um die 4 verschiedenen im Kurs erwähnten: logisch, physisch, statisch, dynamisch mit kurzer Erklärung.</dd>
<dt>Warum überhaupt physische und logische Datenunabhängigkeit? Was nützt das?</dt>
<dd>z.B. Wenn Datenfelder hinzu genommen werden, soll die Anwendung nichts davon mitkriegen.</dd>
<dt>Wann nutzt man dynamische, wann statische Bindung?</dt>
<dd>Wenn das SQL zur Laufzeit erst erstellt wird, muss dynamisch gebunden werden.</dd>
<dt>Warum physische Datenunabhängigkeit?</dt>
<dd>Wenn der Speicherort, die Speicherart oder die Organisation der Daten im Filesystem sich ändert, dann interessiert das die Anwendung nicht.</dd>
<dt>Was garantiert, dass die logische und physische Datenunabhängigkeit existiert?</dt>
<dd>Transformationsregeln.</dd>
<dt>Was ist ein Cursor?</dt>
<dd>Hilfsmittel für tupel orientierten Zugriff auf die Ergebnisse einer SQL Query. Ein Cursor zeigt mit seiner Methode FOUND an ob noch mehr ergebnisse vorhanden sind. Z.B. WHILE Cursor_Name%FOUND … LOOP</dd>
<dt>Was ist funktionale Abhängigkeit?</dt>
<dd>Definition aus dem Kurstext.</dd>
<dt>Mithilfe der funktionalen Abhängigkeiten sind die Normalformen Definiert. Was heisst das z.B. für die 2. Normalform?</dt>
<dd>Muss in der 1. NF sein und alle Nicht-Schlüssel-Attribute voll funktional abhängig. Es sollte der Unterschied zwischen funktional Abhängig und voll funktional Abhängig erklärt werden.</dd>
<dt>Beispiel vom Prüfer: A->B, AC->D; mit der Frage "Liegt 2. NF vor?"</dt>
<dd>Nein, da B nur von A, und somit nur einem Teil vom Schlüssel AC abhängt.</dd>
<dt>Wie kann man hier genanntes Beispiel in die 2. NF bringen?</dt>
<dd>(Hab ich vergessen, hab ich aber auch nicht hingekriegt)</dd>
<dt>Erstelle ein beliebiges ER Modell und führe es in ein Relationenschema über.</dt>
<dd>Ich hab folgenden aufgemalt (ohne Attribute, aber erwähnt):
[Kunde] -n-- <kauft> --m- [Produkte]
RKunde(ID,NAME), RProdukte(ID,NAME), RKundeProdukte(IDKunde, IDProdukte)</dd>
<dt>Nachfrage: Wenn statt n:m, da nun 1:m steht, wie sieht das Schema dann aus?</dt>
<dd>Der Schlüssel der “1”-Seite wird in die m-Relation aufgenommen und keine KundenProdukte() wird benötigt.</dd>
<dt>Formulieren Sie ein SQL basierend dem Relationsschema mit n:m. “Suche alle Produkte eines Kunden”</dt>
<dd>SELECT Produkt.Name FROM Kunde, Produkte, KundeProdukte WHERE Produkt.ID=ProduktKunde.ProduktID AND Produkt.Kunde.KundeId = Kunde.ID AND Kunde.Name = ‘Mueller’</dd>
<dt>Das SQL war ok, und er hat gleich die Gelegenheit genutzt über Optimierung zu sprechen.</dt>
<dd>Statt die JOINS in der WHERE Bedingung zu machen, macht man besser Joins in der FROM Sektion. per FROM Produkte JOIN Kunden ON … hier hat das Erwähnen gereicht, ich musste das nicht ausformulieren.</dd>
<dt>Was sind Outer Joins?</dt>
<dd>Kurz LEFT, RIGHT und FULL OUTER JOIN erklärt.</dd>
</dl>

# 1801

### Betriebssysteme
<dl>
<dt>Was ist virtueller Speicher, wie ist der organisiert?</dt>
<dd>Hier fiel mir ausser ein paar unsortierten Stichworten nichts gescheites ein. Er hat’s aber kurz und knapp erklärt. Und mir in der Nachbesprechung bescheinigt, dass ich den Kurstext hier nur unzureichend zitiert habe. Wie sagte er? “Hier haben Sie sich ja voll verweigert!” :) </dd>
<dt>Was ist ein kritischer Abschnitt?</dt>
<dd>Programmstück, dass zusammenhängend ausgeführt werden muss</dd>
<dt>Um Prozesse zu synchronisieren brauchts Semaphoren. Was ist das?</dt>
<dd>Abstrakte Datenstruktur mit Processqueue, up(), down() Methoden. Genau (!!!) erklaeren wie die implementiert sind. </dd>
<dt>Semaphoren haben also auch einen kritischen Abschnitt, wie geht man damit um?</dt>
<dd>Semaphoren sind so dicht am Kernel, dass das OS dafür sorgt.</dd>
<dt>Aber wie sorgt das OS dafuer?</dt>
<dd>Es<dd> lässt keine Unterbrechungen zu.</dd>
<dt>Wenn eine Seite im Speicher fehlt, was passiert dann?</dt>
<dd>Seitenfehler, und die Daten werden vom Sekundärspeicher (Platte) geladen. Hier habe ich das was auf Seite 34 im Kurstext beschrieben ist erklärt. Und zwar mit allen Details.</dd>
</dl>

### Rechnernetze
<dl>
<dt>Router. Welche Schichten implementiert der und warum nur die?</dt>
<dd>Bitübertragung, Sicherung und Vermittlung. Der Router muss sich nicht um die weiteren kümmern. Komplexität soll an den Rändern des Netzwerks sein.</dd>
<dt>Weiss der Router was von Ports?</dt>
<dd>Nein, Ports sind erst Thema in der Transportschicht und die implementiert ein Router nicht. Router kennen nur IP Adressen und schickt alles da hin.</dd>
<dt>Transportschicht - hier werden üblicherweise TCP und UDP genutzt. Was ist der Unterschied?</dt>
<dd>TCP ist verbindungsorientiert und alle Daten die verschickt werden, kommen auch an. UDP ist verbindungslos und Daten können verloren gehen.</dd>
<dt>Warum ist UDP besser für Streaming?</dt>
<dd>UDP hat mehr Nutzlast an Bord, da weniger Metadaten vorhanden sind.</dd>
<dt>Was noch macht TCP langsamer?</dt>
<dd>Der 3 Wege Handshake.</dd>
<dt>Was nutzt SMTP?</dt>
<dd>TCP</dd>


Die gesamte Prüfung hat +/- 30 Minuten gedauert und Herr Wilkes ist ein sehr guter Prüfer. Er erkennt an was man weiss und hilft einem wenn man etwas nicht weiss. Eine ruhige, angenehme Atmosphäre während des Gesprächs und er strengt sich wirklich an, dass der Prüfling die Prüfung auch bestmöglich besteht. Wenn man mit Unwissenheit glänzt, kann er da allerdings auch nix dran machen. Es wird im Endeffekt mit einer schlechteren Note honoriert hat aber keinen Einfluss auf das weitere Prüfungsgespräch - es wird nicht in Unwissenheit gebohrt sondern mit etwas anderem weiter gemacht.
