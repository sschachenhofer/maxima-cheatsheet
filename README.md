Erstellt von Simon Schachenhofer  
Version: 1.0 (4.5.2020)  
Keine Garantie für Vollständigkeit und Richtigkeit



## Allgemein

### Verwendung von Maxima

#### `kill()` – Löschen von Variablen

Entfernt die Wertzuweisungen von Variablen („löscht die Variablen“).

##### Parameter

`kill(a)`

- *a*: Die Variable die gelöscht werden soll

`kill(all)`

- Löscht alle vergebenen Variablen (das sollte bei jedem neuen Beispiel am Anfang einmal aufgerufen werden).

##### Beispiel

![image-20200504111635643](img\kill.png)



#### `load()` – Laden von Maxima-Packages

Lädt ein Maxima-Package nach, das nicht standardmäßig geladen wird. Das Package bleibt nur so lange geladen, bis `kill(all)` aufgerufen wird. Danach muss es erneut geladen werden.

##### Parameter

`load(package)`

- *package*: Das Package, das geladen werden soll

##### Beispiel

![image-20200504111728441](img\load.png)



#### `float()` – Ausgabe als Dezimalzahl

Gibt eine Zahl als Dezimalzahl aus.

Maxima zeigt einige Ausdrücke (zum Beispiel Terme mit &pi;, Brüche, Potenzen oder Wurzeln) einfach an, anstatt sie auszurechnen. Mit `float()` kann man das Ergebnis aber als Dezimalzahl ausgeben lassen.

Alternativ kann man an einen Befehl auch einfach `, numer` anhängen.

##### Parameter

`float(ausdruck)`

- *ausdruck*: Der Ausdruck, der als Dezimalzahl ausgegeben werden soll

##### Beispiel

![image-20200504110645452](img\float.png)



### Rechenoperationen

#### `sqrt()` – Quadratwurzel

Berechnet die Quadratwurzel ²&radic; einer Zahl oder einer Variablen.

Für alle anderen Wurzeln gibt es **keine** eigene Maxima-Funktion. Hier muss man stattdessen über die Potenzschreibweise rechnen. Die dritte Wurzel (³&radic;) von 8 kann man zum Beispiel mit `8^(1/3)` berechnen.

##### Parameter

`sqrt(a)`

- *a*: Die Zahl oder Variable, von der die Quadratwurzel berechnet werden soll

##### Beispiel

![sqrt](img\sqrt.png)



#### `exp()` – Potenzen mit der Basis *e*

Berechnet eine Potenz mit der Basis *e*, der Eulerschen Zahl.

Alternativ kann man statt `exp(...)` auch einfach `%e^(...)` schreiben.

##### Parameter

`exp(a)`

- *a*: Die Zahl oder Variable, von der die Potenz e^a^ berechnet werden soll.

##### Beispiel

![image-20200504112203530](img\exp.png)



#### `log()` – Natürlicher Logarithmus

Berechnet den natürlichen Logarithmus (den Logarithmus mit der Basis *e*, der Eulerschen Zahl).

Für alle anderen Logarithmen gibt es **keine** eigene Maxima-Funktion. Um einen Logarithmus log~a~ mit der Basis a zu berechnen, kann man sich aushelfen, indem man eine eigene Funktion definiert:  
`log_a(x) := log(x)/log(a)`

##### Parameter

`log(x)`

- *x*: Die Zahl oder Variable, von der der natürliche Logarithmus berechnet werden soll.

##### Beispiel

![image-20200504112242089](img\log.png)



#### `abs()` – Betrag einer Zahl

Berechnet den Betrag einer Zahl (*|a|*).

Zum Berechnen des Betrags eines Vektors (also der Länge eines Vektors) kann diese Funktion **nicht** verwendet werden!

##### Parameter

`abs(a)`

- *a*: Die Zahl, deren Betrag berechnet werden soll.

##### Beispiel

![image-20200504112455032](img\abs.png)



#### `mod()` – Modulo

Berechnet den ganzzahligen Rest (in Programmiersprachen wie Java geschrieben als *a % b*).

##### Parameter

`mod(a, b)`

- *a*: Die Zahl deren Rest berechnet werden soll.
- *b*: Die Zahl, durch die dividiert werden soll.

##### Beispiel

![image-20200504112637974](img\mod.png)



#### `sum()` – Berechnen einer Summe

Geht wie eine Schleife einen Wertebereich durch, setzt die Werte in einen Term ein und berechnet die Summe der Ergebnisse.

Wenn man ein `'` davorsetzt, werden keine Zahlenwerte berechnet, sondern es wird ein Ausdruck mit &Sigma; angezeigt.

##### Parameter

`sum(term, variable, untergrenze, obergrenze)`

- *term*: Der Term, in den eingesetzt werden soll.
- *variable*: Die Variable im Term, für die ein Wert eingesetzt werden soll.
- *untergrenze* und *obergrenze*: Die *variable* durchläuft die Werte von *untergrenze* bis *obergrenze* (beides inklusive).

##### Beispiel

Hier soll die Summe aller Zweierpotenzen mit den Exponenten von 0 bis 10 berechnet werden – also  
2^0^ + 2^1^ + 2^2^ + 2^3^ + 2^4^ + 2^5^ + 2^6^ + 2^7^ + 2^8^ + 2^9^ + 2^10^

![image-20200504113807002](img\sum.png)



### Trigonometrie

**Achtung**: Alle trigonometrischen Funktionen in Maxima erwarten sich Winkel in der Einheit **Radiant** bzw. geben Winkel in Radiant zurück.

Zur Umrechnung zwischen Radiant und Grad kann man sich zwei kleine Funktionen definieren:  
`rad_to_deg(x) := (x / %pi) * 180;`	für die Umrechnung von Radiant in Grad  
`deg_to_rad(x) := (x / 180) * %pi;`	für die Umrechnung von Grad in Radiant



#### `sin()` – Sinus

Berechnet den Sinus eines Winkels.

##### Parameter

`sin(winkel)`

- *winkel*: Der Winkel, dessen Sinus berechnet werden soll, in Radiant.

##### Beispiel

![image-20200504114410846](img\sin.png)



#### `cos()` – Cosinus

Berechnet den Cosinus eines Winkels.

##### Parameter

`cos(winkel)`

- *winkel*: Der Winkel, dessen Cosinus berechnet werden soll, in Radiant.

##### Beispiel

![image-20200504114523021](img\cos.png)



#### `tan()` – Tangens

Berechnet den Tangens eines Winkels.

##### Parameter

`tan(winkel)`

- *winkel*: Der Winkel, dessen Tangens berechnet werden soll, in Radiant.

##### Beispiel

![image-20200504114629262](img\tan.png)



#### `asin()` – Arcus Sinus

Berechnet aus einem Sinuswert den dazugehörigen Winkel in Radiant.

##### Parameter

`asin(x)`

- *x*: Eine Zahl im Intervall [-1; 1] (ein Ergebnis der Sinusfunktion), deren zugehöriger Winkel berechnet werden soll.

##### Beispiel

![image-20200504114848208](img\asin.png)



#### `acos()` – Arcus Cosinus

Berechnet aus einem Cosinuswert den dazugehörigen Winkel in Radiant.

##### Parameter

`acos(x)`

- *x*: Eine Zahl im Intervall [-1; 1] (ein Ergebnis der Cosinusfunktion), deren zugehöriger Winkel berechnet werden soll.

##### Beispiel

![image-20200504114959309](img\acos.png)



#### `atan()` – Arcus Tangens

Berechnet aus einem Tangenswert den dazugehörigen Winkel in Radiant.

##### Parameter

`atan(x)`

- *x*: Eine Zahl (ein Ergebnis der Tangensfunktion), deren zugehöriger Winkel berechnet werden soll.

##### Beispiel

![image-20200504115100187](img\atan.png)





## Terme und Gleichungen

### Allgemein

#### `subst()` – Einsetzen eines Wertes in einen Term oder eine Gleichung

Setzt einen oder mehrere Werte in einen Term ein und berechnet das Ergebnis. Wenn noch kein Ergebnis berechnet werden kann, wird einfach der Term mit den eingesetzten Werten wieder ausgegeben.

Wenn man für mathematische Funktionen in Maxima Terme verwendet, dann entspricht `subst()` dem Berechnen des Funktionswerts für eine bestimmte Zahl.

##### Parameter

`subst(werte, term)` (es gibt aber auch andere mögliche Formen)

- *werte*: Der Wert oder die Werte, die in den Term eingesetzt werden sollen. Das kann entweder eine Gleichung (zum Einsetzen von einem Wert) oder eine Liste (zum Einsetzen von mehreren Werten) sein. Auf jeden Fall wird im Term die linke Seite der Gleichung gesucht und durch die rechte Seite der Gleichung ersetzt.
- *term*: Der Term, in den eingesetzt werden soll.

##### Beispiel

Hier sieht man das Einsetzen von einem einzelnen Wert in *f* und das Einsetzen von mehreren Werten in *g*.

![image-20200504115538131](img\subst.png)



#### `solve()` – Lösen von Gleichungen oder Gleichungssystemen

`solve()` hat hauptsächlich zwei Aufgaben

- Umformen einer Gleichung auf eine bestimmte Variable
- Berechnen der Werte für eine oder mehrere Variablen (aus einer Gleichung oder einem Gleichungssystem)

##### Umformen einer Gleichung auf eine bestimmte Variable

`solve(gleichung, variable)`

- *gleichung*: Die Gleichung, die umgeformt werden soll.
- *variable*: Die Variable, auf die umgeformt werden soll.

Beispiel:

![image-20200504142938805](img\solve1.png)

##### Lösen eines Gleichungssystems

Um ein Gleichungssystem zu lösen und die Werte für die Variablen herauszufinden, braucht man mindestens so viele Gleichungen wie Variablen.

`solve(gleichungssystem, variablen)`

- *gleichungssystem*: Eine Liste mit Gleichungen, die die Variablen enthalten.
- *variablen*: Eine Liste mit Variablen, die in den Gleichungen enthalten sind. Es werden dann die Werte für diese Variablen berechnet.

Beispiel

![image-20200504143408388](img\solve2.png)



#### `newton()` – Numerisches Lösen von Gleichungen, Nullstellensuche

Das Newton-Verfahren ist ein numerisches Verfahren zur Nullstellensuche. Man kann es aber auch zum Lösen von Gleichungen verwenden.

Es macht Sinn, `newton()` zu verwenden, wenn `solve()` kein (oder kein sinnvolles) Ergebnis liefert. Bevor man die Funktion verwenden kann, muss man das Package *newton1* (**nicht** *newton*) mit `load(newton1)` laden.

##### Parameter

`newton(term, variable, startwert, epsilon)`

- *term*: Der Term, dessen Nullstelle gefunden werden soll.
- *variable*: Die Variable, deren Wert gesucht wird.
- *startwert*: Hier gibt man am besten eine grobe Schätzung an, die in der Nähe der Nullstelle liegt (zum Beispiel, indem man die Nullstelle aus einem Graphen ausliest).
- *epsilon*: Die Genauigkeit. Je kleiner dieser Wert ist, desto genauer ist das Ergebnis. `newton()` nähert sich der Nullstelle so lange an, bis der Betrag des Funktionswertes kleiner als *epsilon* ist.

##### Beispiel: Finden von Nullstellen

![image-20200504145001598](img\newton1.png)

##### Beispiel: Lösen einer Gleichung

Hier wurde die Gleichung *m = 7257* nach *d* gelöst.

![image-20200504151403756](img\newton2.png)



#### (`ratsimp()`)



### Nullstellensuche

siehe auch: `newton()`

#### `allroots()` und `realroots()` – Finden von allen Nullstellen

Mit diesen Funktionen lassen sich die Nullstellen einer Polynomfunktion berechnen (also alle Werte der Variable, für die der Term 0 ergibt). Nach dem *Fundamentalsatz der Algebra* hat ein Polynom n-ten Grades immer genau n Nullstellen. Nullstellen können aber gleich sein oder in den komplexen Zahlen liegen.

- `allroots()` gibt alle Nullstellen zurück
- `realroots()` gibt nur die reellen Nullstellen zurück

##### Parameter

`allroots(term)`  
`realroots(term)`

- *term*: Der Term, dessen Nullstellen gesucht werden sollen.

##### Beispiel

![image-20200504153549669](img\allroots_realroots.png)



### Umformen

#### `factor()` – Faktorisieren eines Terms (Herausheben)

Zerlegt einen Term in mehrere Faktoren (zum Beispiel durch Herausheben).

##### Parameter

`factor(term)`

- *term*: Der Term, der faktorisiert werden soll.

##### Beispiel

![image-20200504143542699](img\factor.png)



#### `expand()` – Ausmultiplizieren eines Terms

Multipliziert einen Term aus mehreren Faktoren aus. Das ist die Umkehrfunktion zu `factor()`.

##### Parameter

`expand(term)`

- *term*: Der Term, der ausmultipliziert werden soll.

##### Beispiel

![image-20200504153922124](img\expand.png)



#### `rhs()` und `lhs()` – Zugriff auf eine Seite einer Gleichung

Mit diesen beiden Funktionen kann man auf die einzelnen Terme auf den beiden Seiten einer Gleichung zugreifen. Das ist besonders praktisch, wenn man sich das Ergebnis von einem anderen Funktionsaufruf (zum Beispiel von `solve()` oder `realroots`) in einer Variable speichern möchte.

- `rhs()` greift auf die rechte Seite zu (*right hand side*)
- `lhs()` greift auf die linke Seite zu (*left hand side*)

##### Parameter

`rhs(gleichung)`  
`lhs(gleichung)`

- *gleichung*: Die Gleichung, auf deren rechte oder linke Seite zugegriffen werden soll.

##### Beispiel

![image-20200504154539439](img\rhs.png)



## Differenzieren und Integrieren

#### `diff()` – Differenzieren (Ableiten) eines Terms

Leitet einen Term nach einer Variable ab.

Um beim Aufstellen einer Differenzialgleichung die angeschriebene Ableitung zu bekommen (anstatt dem Ergebnis der Ableitung), einfach ein `'` davorsetzen: `'diff(...)`

##### Parameter

Standardform: `diff(term, variable, n)`

- *term*: Der Term, der abgeleitet werden soll
- *variable*: Die Variable, die abgeleitet werden soll
- *n*: Gibt an, die wievielte Ableitung gebildet werden soll (optional)

Es gibt aber auch noch andere Möglichkeiten, die Funktion aufzurufen.

##### Beispiel

Ableiten eines Terms:

![image-20200505171018514](img\diff.png)

`'diff(...)` für das Bilden einer Differenzialgleichung:

![image-20200505172146348](img\diff2.png)



#### `integrate()` – Bestimmtes oder unbestimmtes Integral

Integriert einen Term – bestimmt oder unbestimmt.

##### Unbestimmtes Integral

**Achtung**: Beim unbestimmten Integral gibt Maxima die Integrationskonstante **nicht** aus – sie gehört aber trotzdem zum Ergebnis dazu!

Parameter:

`integrate(term, variable)`

- *term*: Der Term, der integriert werden soll
- *variable*: Die Variable, nach der integriert werden soll

Hier gibt es im Gegensatz zu `diff()` **kein** Parameter, um mehrere Stufen auf einmal zu integrieren!

Beispiel:

![image-20200505173007040](img\integrate.png)

##### Bestimmtes Integral

Beim bestimmten Integral kann es sein, dass `integrate()` kein sinnvolles Ergebnis liefert. Dann muss man stattdessen eine numerische Integrationsmethode wie `romberg()` verwenden.

Parameter:

`integrate(term, variable, a, b)`

- *term*: Der Term, der integriert werden soll
- *variable*: Die Variable, nach der integriert werden soll
- *a* und *b*: Die beiden Grenzen des Integrationsintervalls

Beispiel:

![image-20200505172906143](img\integrate2.png)



#### `romberg()` – Numerisches bestimmtes Integral

Ein numerisches Integrationsverfahren für bestimmte Integrale. In Fällen, in denen `integrate()` kein sinnvolles Ergebnis liefert, kann man auf `romberg()` zurückgreifen.

Eventuell muss die Funktion zuerst mit `load(romberg);` geladen werden.

##### Parameter

Die Parameter sind gleich wie bei `integrate`:

`romberg(term, variable, a, b)`

- *term*: Der Term, der integriert werden soll
- *variable*: Die Variable, nach der integriert werden soll
- *a* und *b*: Die beiden Grenzen des Integrationsintervalls

##### Beispiel

Hier wurde versucht, eine Bogenlänge zu berechnen. `integrate()` hatte kein numerisches Ergebnis, deshalb wurde `romberg()` verwendet.

![image-20200505173457904](img\romberg.png)



#### `ode2()` – Allgemeine Lösung einer Differenzialgleichung

Berechnet die allgemeine Lösung einer Differenzialgleichung erster oder zweiter Ordnung. Zum Aufstellen einer Differenzialgleichung muss man `'diff()` mit dem Apostroph verwenden – siehe oben.

Das Ergebnis von `ode2()` kann eventuell noch vereinfacht werden.

Um die Integrationskonstante zu berechnen (und damit von der allgemeinen Lösung zu einer partikulären Lösung zu kommen), kann man das Ergebnis von `ode2()` an die Funktion `ic1()` übergeben.

##### Parameter

`ode2(dgl, avar, uvar)`

- *dgl*: Die Differenzialgleichung, deren Ergebnis berechnet werden soll.
- *avar*: Die *abhängige Variable* (also der Name der Funktion, die man erhalten möchte) – zum Beispiel y
- *uvar*: Die *unabhängige Variable* (also das Argument der Funktion) – zum Beispiel x

##### Beispiel

![image-20200505174532434](img\ode2.png)



#### `ic1()` – Berechnen der Integrationskonstante aus der allgemeinen Lösung einer Differenzialgleichung

Berechnet die Integrationskonstante (`%c`), um von der allgemeinen Lösung einer Differenzialgleichung auf eine partikuläre Lösung zu kommen.

##### Parameter

`ic1(loesung, uwert, awert)`

- *loesung*: Die allgemeine Lösung (hier kann einfach das genommen werden, was bei `ode2` herauskommt)
- *uwert*: Wert der unabhängigen Variablen in der Anfangs-/Randbedingung, in Form einer Gleichung (z.B. `x = 0`)
- *awert*: Wert der abhängigen Variablen in der Anfangs-/Randbedingung, in Form einer Gleichung (z.B. `y = 23.5`)

##### Beispiel

![image-20200505180510146](img\ic1.png)



## Stochastik

### Allgemein

#### `binomial()` – Berechnen des Binomialkoeffizienten

Berechnet den Wert des Binomialkoeffizienten („n über k“).

##### Parameter

`binomial(n, k)`

- *n*: n – die Größe der Grundmenge
- *k*: k – Die Anzahl an Elementen, die ausgewählt werden sollen

##### Beispiel

![image-20200505181151608](img\binomial.png)



### Verteilungen

In Maxima gibt es Funktionen für viele verschiedene Verteilungen, die nach einem gemeinsamen Schema benannt sind (z.B. `pdf_<Name der Verteilung>()`).

Die für uns wichtigsten Verteilungen sind:

- `..._binomial`: Die Binomialverteilung
- `..._hypergeometric`: Die hypergeometrische Verteilung
- `..._normal`: Die Normalverteilung
- `..._poisson`: Die Poisson-Verteilung

Die Parameter der Funktionen sind von der Verteilung abhängig!

Alle Maxima-Funktionen, die mit Verteilungen zu tun haben, gehören zum Package `distrib`. Dieses muss zuerst mit `load(distrib)` geladen werden.

Im folgenden werden die Parameter für die verschiedenen Verteilungen erklärt. Dabei wird als Beispiel immer die Wahrscheinlichkeitsfunktion (der Name beginnt mit `pdf_...`) genommen.



#### `..._binomial` – Binomialverteilung

##### Parameter

`pdf_binomial(x, n, p)`

- *x*: (auch *k*): Anzahl, wie oft der gewünschte Fall eintreten soll
- *n*: Anzahl, wie oft das Zufallsexperiment durchgeführt wird
- *p*: Wahrscheinlichkeit für ein Experiment, dass der gewünschte Fall eintritt (muss als Dezimalzahl angegeben werden: 32 % = 0.32)



#### `..._hypergeometric` – Hypergeometrische Verteilung

##### Parameter

`pdf_hypergeometric(x, D, )`

- *x*: Anzahl an Merkmalsträgern, die in der Stichprobe enthalten sein sollen
- *n1*: Anzahl an Merkmalsträgern in der Grundgesamtheit
- *n2*: Anzahl an Nicht-Merkmalsträgern in der Grundgesamtheit
- *n*: Größe der Stichprobe (Anzahl an Elementen, die aus der Grundgesamtheit gezogen werden)

**Achtung**: Die Parameter sind hier **anders** als bei der hypergeometrischen Verteilung üblich! Normalerweise benutzt man die folgenden vier Parameter:

- *N*: Größe der Grundgesamtheit (Anzahl an Elementen insgesamt)
- *n*: Größe der Stichprobe (Anzahl an Elementen, die aus der Grundgesamtheit gezogen werden)
- *D*: Anzahl der Merkmalsträger in der Grundgesamtheit
- *x*: Anzahl der Merkmalsträger, die in der Stichprobe enthalten sein sollen

So kommt man davon auf die Parameter für die Maxima-Funktion:

- *x* und *n* können übernommen werden
- *n1* entspricht *D*
- *n2* ist *N* - *D*



#### `pdf_...()` – Wahrscheinlichkeits- bzw. Dichtefunktion





#### `cdf()_...()` – Verteilungsfunktion



#### `quantile_...()` – Berechnen eines Quantils



## Statistik

#### `mean()` – Arithmetischer Mittelwert



#### `median()` – Median



#### `std()` – Standardabweichung &sigma;



#### `var()` – Varianz &sigma;²



## Matrizen und Vektoren

#### `matrix()` – Erstellen einer Matrix



#### `columnvector()` – Erstellen eines Spaltenvektors



### Rechnen mit Matrizen

#### `determinant()` – Berechnen der Determinante einer Matrix



#### `invert()` – Invertieren einer Matrix



#### `transpose()` – Transponieren einer Matrix



## Grafische Darstellungen

### `wxplot2d()` – Einfaches Zeichnen von Funktionsgraphen und Punkten



### `wxdraw2d()` – Komplexeres Zeichnen von Funktionsgraphen, Punkten, Formen und mehr