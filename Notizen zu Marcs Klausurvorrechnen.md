# Link zum Vorrechnen
https://www.youtube.com/watch?v=x-YhKx23TtE
# Notizen
## Aufgabe 1
- `package`/`import`-Anweisungen waren noch nie mötig
- Functional Interfaces haben eine nicht implementierte Methode
- `default`-Methoden kommen gerne dran
- Grundlagen von Generics kommen auf jeden Fall dran
- Eigentlich kommt bei Beschränkungen nur `extends` vor
- Die Tatsache, dass Stream Typparameter hat, zählt nicht zu den Anforderungen der Klausur
- jede Methode im Interface ist automatisch public, sollte man dazuschreiben um es nicht zu vergessen
- BiFunction o.ä. wird in den Hinweisen beschrieben
- BiFunction, Supplier,... anschauen schadet nicht
- `default`-Methoden sind in Interfaces immer implementiert
- Neu deklarierter Typparameter wird vor return, nach den Modifiern angegeben
- Methode/Klasse nur generisch machenm, wenn es verlangt wird
- "nicht Subtypen!"-Hinweis auf ist nicht immer da
- Wenn man mit Generics und `super` arbeitet, muss es immer Wildcard sein
- Solange nicht explizit angemerkt, korrelieren Dinge nicht, z.B. kann 2 mal selbe Beschränkung vorkommen, sind immer noch separat zu handhaben
- Wenn nicht angegeben, darf man keine weiteren Typparameter hinzufügen
- Code muss nicht effizient sein
- Wir wissen nicht, was get zurückgibt, wir dürfen aber kontextbasiert ableiten, dass Supplier etwas vom Typ `? extends String` zurückgibt
- `? extends String` -> zum Zwischenspeichern String verwenden, Object würde zu Probleme führen
- Information, dass man davon ausgehen darf, dass irgendwann nicht mehr null zurückgeliefert wird ist gut zu wissen
- Würde nichts am Code ändern, wenn man obige Angabe nicht hat
- Bewertungsschema ist Schwachsinn
- public sollte man auch hinschreiben, wenn es nicht benötigt wird
- Erste Aufgabe ist eigentlich immer abstraktes Interface
- Früher waren Klausuren in 6 Aufgaben aufgeteilt, diese Aufteilung kann man immer noch machen
## Aufgabe 2
- Beim Implementieren einer Methode aus Interface muss Methode immer public sein
- Methodenkopf bleibt gleich
- Bei Implementation selbe Einschränkungen vornehmen
- Von vorherigen Aufgaben i.d.R. Typparameter übernehmen, nicht abändern
- Es ist besser, solche returns in eine Zeile zu packen (`return fct.apply(null, y );`)
- Hinweis, dass Methode nicht implementiert wird ist nicht immer gegeben
- Wenn etwas nicht implementiert ist -> `abstract`!
- `abstract`-Stolperstein kommt höchstwahrscheinlich
## Aufgabe 3
- Es kann vorkommen, dass Informationen zu spät gegeben werden (Informationen für Aufgabe 2 in Aufgabe 3 gegeben)
- Man darf sowas aus Kontext herleiten
- Frühere Aufagabenstruktur: 1a, b, c, ... -> Heutige Struktur: 1, 2, 3,..
- In der Klausur zur Not nachfragen
- Folgefehler geben i.d.R. nur einmal Abzug
- implements bei Interfaces, extends bei Klassen
- Typparameter kopieren ist oft nicht falsch wenn etwas aus vorheriger Aufgabe verwendet wird
- Wenn Consumer-Methode nicht implementiert wird, müsste Klasse wieder `abstract` sein
- accept von Interface Consumer -> `public`
- Klausurstruktur bleibt wahrscheinlich gleich
- Wenn Rückgabetyp nicht gegeben, fragen, zur Not `void` (nur letzte Bastion!)
- Manchmal muss man Parameter selber ausdenken, dann Name egal
- Wenn eine Methode als funktionale Methode bezeichnet wird ist Interface funktional
- Wrapper-Klasse: Eingekapselten Wert kann man per `System.out.println(d)` bekommen
- Autoboxing/Autounboxing (Kommt wahrscheinlich dran): double <-> Double
```
public static void test(Double a){...}  // Beispiel für Autoboxing
test(5.0);

public static void test(double a){...}  // Beispiel für Autounboxing
Double d = (Double) 5.0;                // Alternativ aber depreceated: new Double(5.0);
test(d);

Integer a = 5;                          // Integer -> Double geht nicht direkt
Double d = (double) (int) a;            // casten ist nötig
```
## Aufgabe 4
- Aufgabe 2 (4,5,6) üblicherweise Exceptions, typischer Aufbau:
- 2 Exceptions die voneinander erben
- Danach werfen/fangen
- Konstruktor von selbst aufrufen: `this(...)`
- `instanceof` ist einzige Möglichkeit, um auf dynamischen Typen zuzugreifen
- `super` darf nur einmal und als 1. Zeile (1. Anweisung) aufgerufen werden
- Klammern sind subjektiv wenn syntaxmäßig äquivalent
- Man darf annehmen, dass intValue() in der Tat einen Integer zurückgibt
- wenn es einen parameterlosen Konstruktor in der Basisklasse gibt, wird dieser automatisch aufgerufen
## Aufgabe 5
- Im Hinweis-Block könnten auch neue Dinge eingeführt werden
- Gedanken-Notizen kann man auskommentiert in Klausur lassen, Code sollte noch lesbar sein
- Eigentlich für Notizen Schmierblatt/Whiteboard nutzen
- Wer lesen kann ist klar im Vorteil, lieber nochmal genauer nachlesen
- Klassenmethode -> `static`
- Objektmethoden sind Standard, sollte aber immer dabeistehen
- Wenn da steht, dass man Klasse nicht schreiben muss, muss man Klasse nicht schreiben
- lieber nochmal prüfen ob Parameter, z.B. 5,6 mit den Datentypen passen
- Wenn Exception geworfen wird, direkt `throws`-Klausel mit genau dem Typen hinzufügen
- `throws Exception` war nie verlangt, immer genauer
- was generell gut/Konvention ist, wird auch verlangt, z.B. ist `throws Exception` schlecht
- `6L`/`6l`/`(long) 6`/`6 // Alles long`
- isEmpty() gibt tatsächlich zurück, ob etwas leer ist, davon darf man ausgehen
- Wenn Parameter a von Typ A ist und nicht null, wird a instanceof A immer true sein
- cast int -> byte ist lossy, daher muss immer explizit gecastet werden
- Lösung über Methoden ist better, sowas wie `isLowerCase()`
- `&&` bricht ab, wenn erste Sache `false` ist
- wenn Rückgabe eines Aufrufs abgeprüft werden soll, lieber in Varibale zwischenspeichern
- Rückgabetyp einer Methode ist Character, dann lieber in Variable von Typ `Character` speichern, nicht `char`
- auf Nummer sicher gehen: casts
- Wenn `Exc1` in throws-Klausel ist, Exc3 ist von Exc1 abgeleitet, dann muss Exc3 nicht in Klausel hinzugefügt werden
- `Double.valueOf()` ist nützlich
## Aufgabe 6
- Wenn Methode Klassenmethode ist und diese verwendet wird: `Y.m();`
- `catch (Exc2 | Exc3 e){...}` kommt zu 80%
- Auf Scope achten, insbeseondere beim Zwischenspeichern von Werten bei try-catch und so
- Zuerst spezifische catches, danach die Superklassen davon
- Normalerweise nur 3 Exception-Klassen
## Aufgabe 7
- man muss kein Racket schreiben können
- Aufgabe 3 wahrscheinlich Racket -> Java rekursiv, Java iterativ, Java mit ListItem
- `(cons "a" (list 1 2 3))` -> `(list "a" 1 2 3)`
- ListItem kommt zu 100% dran
- korrekt gebildete Liste: key ist nie null
- `cond /* racket */ -> if(...){...}else if(...){...} ... else{...} // java`
- Wenn gefordert, kopieren von Methodeninhalt wichtig, man darf auch auslagern
- Bisher immer Beschreibung und Beispiel beim Racket-Code
- Hilfsmethode fürs Kopieren: private (static bei Objektmethode nicht nötig)
## Aufgabe 8
- lieber `while` als `for`-Schleife
## Aufgabe 9
- wurde übersprungen
## Aufgabe 10
- kommt so wahrscheinlich in der Klausur, Lambda-Ausdrücke sind wichtig
- eigenes Interface schreiben
- Lambdas in Java und Racket relevant
- Beispielaufruf umsetzen
- In Racket sind `=` und `<` nur für Zahlen definiert
- man bekommt nicht immer Informationen zu Parametern und muss sich diese erschließen
- Dinge in Lambdas und Parametern gleich nennen um es leicht zu machen bei der Übersetzung
- Da im Aufgabentext nichts von Beschränkungen steht, sollte man keine Einschränkungen vornehmen
## Aufgabe 11
- Auf generisch/nichtgenerisch achten!
- Köpfe kann man einfach kopieren
- @Override ist nicht benötigt
## Aufgabe 12
- in Erinnerungen stehen gerne auch neue Informationen
- 1-zu-1-Benennung
- Klammern bei Lambdas notwendig, wenn es mehr als einen Eingabewert gibt
- Nicht vergessen, dass Foo/foo und Bar/bar Objekte sind
- Beispielaufruf: `Y.foobar(...).apply(...);`
- Informationen aus vorherigen Aufgaben darf man verwenden
## Aufgabe 13
- Array-Aufgabe einmal iterativ, einmal rekursiv; sehr wahrscheinlich dass dieser Aufgabentyp kommt
- Rekursive Aufgabe ist eventuell Zeit nicht wert
- Iterativ ist i.d.R. besser als rekursiv
- Meistens Zahlenbeispiel
- Bearbeitungsstrategie:
	- Erst Größe des finalen Arrays feststellen
	- Dann resultierendes Array über vorher verwendeten Indexzähler anlegen
	- Zählcode kopieren und abändern
- Bei Integer-Division wird Rest ignoriert
- Nicht List o.ä. verwenden, wenn es nicht direkt verboten ist, lieber nachfragen
## Aufgabe 14
- Rekursiver Ansatz:
	- Man kann Code zu großen Teilen vom iterativem Teil kopieren
	- Schleifenabbruchsbedingung wird Rekursionsanker
## Aufgabe 15
- War früher 1. Aufgabe, ist nun letzte
- Aufgaben können frech sein
- Vererbung/Typisierung wird bei Kompilierzeit überprüft
## Aufgabe 16
- `final`-Attribute müssen direkt oder im Konstruktor zugewiesen/initialisiert werden
- Auf `final`-Attribute kann nur lesend zugegriffen werden
## Aufgabe 17
- wenn kein access-Modifier: `package-private`, auch als "default" bezeichnet
- nested classes kommen nur kurz dran
- nested classes können `public`/`protected`/`private`/"default" sein (alle Optionen), man kann sie als Attribute verstehen
## Aufgabe 18
- Darstellungsinvariante: Dies gilt zu jedem Zeitpunk für ein Objekt der Klasse, egal was man mit dem Objekt macht, jede Subklasse hat selbe Darstellungsinvariante
- Arrays brauchen weniger Speicherplatz als Listen, weil man immer die Einkapselung mit ListItem braucht
- Liste hat intern mehr Elemente die schon reserviert sind, implementationsabhängig
- Jede Liste hat immer mindestens ein Attribut mehr
## Generelle Tipps
- Quizfragen als letztes bearbeiten
- Aufgabe 1 zuerst (generics)
- Aufgabe 2: Exceptions
- Wenn nicht so sicher mit Racket, die 2. ist meist leichter (lambdas Übersetzen)
- 1. Racket Aufgabe versuchen, weil sie viele Punkte gibt
- Array-Aufgabe: rekursiven Teil lieber erstmal weglassen
