# Diskrete Mathematik

[TOC]

## Organisatorisches

### Team
* Professor: Ueli Maurer
* Hauptassistent: Martha ...
* Meine Übungsgruppe: Anton Schäfer -\> Dienstags 15-17 Uhr, ETZ E 6

###Webseite
<https://www.crypto.ethz.ch/teaching/lectures/DM18/>
-   Übungsblätter
-   Aktuelle Nachrichten

### Wichtig
-   Skript für 10 CHF kaufen. Wichtig zum Vor- und Nachbereiten der
    Vorlesungen
-   Zeitaufwand mind. 2x so viel wie Vorlesungen + Übungsstunden
-   Drei Ziele: Inhalte, Informatikmäßiges Denken, Mathematisches
    Denken)

## Math, Reasoning, Proofs & a First Approach to Logic

### Allgemeines
Das Verständnis der zu beweisenden Behauptung ist existenziell. Nur wenn
die Behauptung eindeutig und klar formuliert ist, lässt sie sich
beweisen. Es gilt hierbei zu beachten, dass sich abstrakte Aussagen
häufig leichter beweisen lassen als einzelne Beispiele. Beweise sind
dann akzeptabel, wenn sie nachvollziehbar (und abgeschlossen) sind.
Aussage, die zu beweisen sind, werde häufig auch als Propositionen
bezeichnet. Sie müssen eindeutig formuliert sein und dadurch beweis-
oder widerlegbar.

### Aussagenlogik


#### Logische Konstanten, Operatoren und Formeln

##### Definition Konstanten {#definition-konstanten .unnumbered}
Die logischen Konstanten "Wahr" und "Falsch" werden auch mit 1 bzw. 0
bezeichnet.

##### Definition Operationen {#definition-operationen .unnumbered}
-   Die **Negation** (logisches NOT) einer Proposition $A$ wird $\neg A$
    geschrieben und ist dann und nur dann wahr, wenn $A$ falsch ist.
-   Die **Konjunktion** (logisches AND) zweier Propositionen $A$ und $B$
    wird $A \land B$ geschrieben und ist dann und nur dann wahr, wenn
    $A$ und $B$ wahr sind.
-   Die **Disjunktion** (logisches OR) zweier Propositionen $A$ und $B$
    wird $A \lor B$ geschrieben und ist dann und nur dann wahr, wenn $A$
    oder $B$ (oder beide) wahr sind.
-   Die **Implikation** zweier Propositionen $A$ und $B$ wird
    $A \rightarrow B$ geschrieben und ist dann und nur dann wahr, wenn
    $B$ aus $A$ folgt.
-   Die **zweiseitige Implikation** zweier Propositionen $A$ und $B$
    wird $A \leftrightarrow B$ geschrieben und ist dann und nur dann
    wahr, wenn $B$ aus $A$ und $A$ aus $B$ folgt.
Die logischen Operatoren lassen sich nicht nur mit Worten definieren,
sondern auch mit Wahrheitswerttabellen (function table):

| $A$|$B$|$\neg A$ |  $A \land B$ |  $A \lor B$  | $A \rightarrow B$  | $A \leftrightarrow B$|
|-----| -----| ----------| -------------| ------------| -------------------| -----------------------|
|0 |    0 |      1|            0            |0                |1                     |1|
|    0|     1|       1|            0|            1|                1|                     0|
|1     |0       |0            |0            |1                |0                     |0|
|    1|     1|       0|            1|            1|                1|                     1|

##### Definition Äquivalenz

Zwei logische Formeln $F$ und $G$ werden **äquivalent** genannt
($F \equiv G$), wenn sie dieselbe Funktion haben, also in jedem Fall
eine Übereinstimmung der Wahrheitswerte vorliegt.

##### Definition Logische Konsequenz

Eine Formel $F$ wird **logische Konsequenz** von $G$ genannt
($G \vDash F$), wenn $F$ immer dann wahr ist, wenn auch $G$ wahr ist.
Wenn $F$ eine Tautologie ist, schreibt man auch $\vDash F$.

##### Definition Tautologie und Erfüllbarkeit

Eine Formel $F$ wird als **Tautologie** bezeichnet, wenn sie in jedem
Fall wahr ist. Sie wird **erfüllbar** genannt, wenn sie in mindestens
einem Fall wahr ist und **unerfüllbar**, wenn sie in keinem Fall wahr
ist.

#### Verhältnis von Formeln und Aussagen

-   Formeln sind nicht Aussagen
-   Formeln an sich sind nicht wahr oder falsch. Sie können höchstens
    eine Tautologie oder unerfüllbar sein.
-   Die Äquivalenz zweier Formeln $F \equiv G$ ist eine mathematische
    Aussage

### Prädikatenlogik
In der Prädikatenlogik werden Universen (nicht-leere Mengen) betrachtet
und in diesen Universen Schlüsse gezogen. Hierfür werden sog. Prädikate
verwendet, die jedem Element einer oder mehreren Listen von Elementen
aus dem betrachteten Universum einen Wahrheitswert zuordnen.

Beispiel: Im Universum $U=\mathbb{N}$ kann man das Prädikat $prime(x)$
betrachten, welches definiert ist als
$$prime(x)=\begin{cases}1 & \text{if $x$ is prime}\\ 
​                          0 & \text{else}\end{cases}$$.

#### Quantoren
##### Definition: Quantoren

Für ein Universum $U$ und das Prädikat $P(x)$ werden die folgenden
Aussagen definiert:\
$\forall x P(x)$ ist die Aussage: $P(x)$ ist wahr, **für alle** $x$ in
$U$\
$\exists x P(x)$ ist die Aussage: Es existiert ein $x \in U$, für das
$P(x)$ wahr ist.\
Wichtig bei der Kombination mehrerer Quantoren ist die Reihenfolge!

Beispiel Primzahlen im Universum der Natürlichen Zahlen:
$$prime(x) := x>1 \land (\forall y \forall z ((y * z=x) \rightarrow (y=1) \lor (z=1)))$$

##### Zwei Beispiele mit Quantoren

$$\exists y (xy = 1)$$ Diese Formel kann nicht wahr oder falsch sein, da
$x$ nicht definiert ist. Der Wahrheitswert hängt somit von $x$ ab.
$$\forall x (x=0 \lor \exists y (xy = 1) \text{ in } U=R$$ Diese Formel
ist eine sog. **Propositionsformel**. Sie ist eine Aussage, da alle
Variablen definiert sind (im Universum $U$). Dementsprechend kann sie
wahr oder falsch sein (in $U = \mathbb{N}$ ist sie falsch).

### Beweismuster
Im Folgenden wird das "$\Rightarrow$" Symbol als Anzeige für
Herleitungsschritte verwendet. Es kann zwischen zwei Aussagen (nicht
Formeln wie "$\rightarrow$" in der Aussagenlogik) stehen.

#### Direkter Beweis einer Implikation

Ein direkter Beweis einer Implikation $S \Rightarrow T$ wird geführt,
indem T unter der Annahme, das S gilt, bewiesen wird.

$S := \text{ a und b sind Quadratzahlen}$\
$T := \text{ a*b ist eine Quadratzahl}$\
Beweis:\
Annahme: $a=u^2, b=v^2$\
Dann gilt folgendes:\
$a*b = u*u*v*v=u*v*u*v=(u*v)*(u*v)=(u*v)^2$\
$a*b=w*w \text{ mit } w=u*v$\
Das heisst, dass $a*b$ eine Quadratzahl ist. q.e.d.

#### Indirekter Beweis einer Implikation

Ein indirekter Beweis einer Implikation $S \Rightarrow T$ wird geführt,
indem T als falsch angenommen wird und unter dieser Annahme S als falsch
bewiesen wird. Grundlage in der Aussagenlogik:
$\neg B \rightarrow \neg A \vDash A \rightarrow B$.

#### Komposition von Implikationen

Eine Implikation lässt sich durch eine Komposition von Implikationen
beweisen, indem die zu beweisende Implikationen in zwei Implikationen
aufgeteilt wird. Grundlage in der Aussagenlogik:
$(A \rightarrow B) \land (B \rightarrow C) \vDash A \rightarrow C$.

#### Modus Ponens

Um eine Aussage zu beweisen kann eine andere Aussage formuliert und
bewiesen werden. Anschließend muss nur noch gezeigt werden, dass aus der
neuen Aussage die zu beweisende folgt. Grundlage in der Aussagenlogik:
$(A \land (A \rightarrow B) \vDash B)$.

#### Fallunterscheidung

Eine Aussage kann auch dadurch bewiesen werden, dass jeder einzelne
Fall, in dem sie gelten soll bewiesen wird. Dabei ist zu beachten, dass
immer alle Fälle abgedeckt sein müssen. Grundlage in der Aussagenlogik:
$(A_1 \lor A_2 \lor ... \lor A_n) \land (A_1 \rightarrow B) \land (A_2 \rightarrow B) \land ... \land (A_n \rightarrow B) \vDash B$.

#### Widerspruchsbeweis

Soll eine Aussage bewiesen werden, kann man dies tun, indem man sie als
falsch annimmt und daraus eine weitere Aussage folgert, die als falsch
bewiesen werden muss (Widerspruch). Grundlage in der Aussagenlogik:
$(\neg A \rightarrow B) \land \neg B \vDash A$.

#### Existenzbeweis

Der Beweis einer Aussage $S_x$ nach dem Muster "$S$ ist für mindestens
ein $x$ wahr" erfolgt entweder durch Angabe eines $x$, für das $S$ wahr
ist (konstruktiver Existenzbeweis), oder durch einen Widerspruchsbeweis
(nicht-konstuktiver Existenzbeweis).

#### Schubfachprinzip für Existenzbeweise

#### Beweis durch ein Gegenbeispiel

Eine Aussage $S_x$ der Form "$S$ ist nicht für alle $x$ wahr" kann durch
ein Beispiel für $x$, bei dem $S$ nicht wahr ist, gegeben werden.

#### Induktionsbeweis

Soll eine Aussage der Form $\forall n P(n), n \in \mathbb{N}$ bewiesen
werden, kann dies durch einen Induktionsbeweis geschehen. Die Grundlage
hierfür bietet die Logik folgendermaßen:
$$P(0) \land \forall n (P(n) \rightarrow P(n+1)) \vDash \forall n P(n)$$
Ein Induktionsbeweis ist immer nach folgendem Schema aufgebaut:

1.  Basisschritt der Induktion. Hier wird gezeigt, dass die Aussage für
    den Ausgangspunkt (meistens $n=0$ oder $n=1$) gilt.

2.  Aufstellen der Induktionshypothese. Dafür wird die Aussage mit
    $A(n)$ am Anfang formuliert

3.  Beweis des Inuktionsschrittes. Der Induktionsschritt
    ($A(n) \rightarrow A(n+1)$) wird hier bewiesen.

## Mengen, Relationen und Funktionen

### Mengen
Mengen sind die einfachsten mathematischen Objekte, da sie strukturlos
(keine Reihenfolge o.ä.) sind. Heute nutzt man hauptsächlich eine
Axiomatische Mengenlehre, doch das ist für uns nicht wichtig.

#### Elemente eine Menge, Gleichheit von Mengen und Kardinalität

Mengen können unterschiedlich definiert werden. Unabhängig von der
Beschreibung kann man prüfen, ob ein bestimmtes Element $x$ in einer
Menge $M$ vorhanden ist ($x \in M$) oder nicht ($x \notin M$). Als
Elemente in Mengen kommen auch andere Mengen infrage. Werden zwei Mengen
$A$ und $B$ verglichen, so werden sie genau dann als "gleich"
bezeichnet, wenn jedes Element $x$ aus $A$ auch ein Element von $B$ ist
und jedes Element $y$ in $B$ auch in $A$ vorkommt. Es gilt also:
$A=B \Leftrightarrow \forall x (x \in A \land x \in B$). Die
Kardinalität einer Menge $A$ wird $\mid A \mid$ geschrieben und gibt die
Anzahl der Elemente von $A$ an.

#### Beschreibung von Mengen

Werden endliche Mengen beschrieben, so werden häufig alle Elemente
aufgezählt: $A = \{1,2,3\}$. Mengen können aber auch dadurch beschrieben
werden, dass bestimmte Eigenschaften für die Elemente gelten müssen. So
kann eine Menge $B$ als $B=\{x \in A \mid P(x)\}$ beschrieben werden.
Hierbei ist $A$ eine Menge von möglichen Elementen und $P$ ein Prädikat,
welches die Eigenschaften der Elemente von $B$ beschreibt. Anstelle des
senkrechten Striches "$\mid$" wird häufig auch eine Doppelpunkt "$:$"
genutzt.

#### Teilmengen

Eine wichtige Relation zweier Mengen ist die Frage, ob eine Menge $A$
eine Teilmenge einer anderen Menge $B$ ist. Die Menge $A$ ist genau dann
eine Teilmenge der Menge $B$, wenn alle Elemente in $A$ auch in $B$
sind. Es gilt hier also:
$A \subseteq B :\Rightarrow \forall x (x \in A \rightarrow x \in B)$.
Jede Menge ist folglich auch eine Teilmenge von sich selbst. Daraus
folgt dann auch:
$A=B \Leftrightarrow (A \subseteq B) \land (B \subseteq A)$.

#### Die leere Menge $\emptyset$

##### Definition

Die leere Menge, geschrieben als $\emptyset$, $\varnothing$ oder $\{\}$
ist die Menge ohne Elemente. Es gilt also:
$\forall x (x \notin \emptyset)$.

Die leere Menge ist Teilmenge jeder anderen Menge. Sie ist außerdem
einzigartig. Die leere Menge kann auch ein Element anderer Mengen sein.
So ist es Möglich eine Menge als $\{\emptyset\}$ oder gar
$\{\{\{\{\emptyset\}\}\}\}$ zu beschreiben. Im Gegensatz zur leeren
Menge selbst haben diese Mengen eine Kardinalität von 1 (anstatt von 0).

#### Potenzmenge

##### Definition

Die Potenzmenge einer Menge $A$, geschrieben $\mathcal{P}(A)$, ist die
Menge aller Teilmengen von $A$. Es gilt also:
$\mathcal{P}(A) := \{S \mid S \subseteq A\}$. Beim Arbeiten mit der
Potenzmenge ist wichtig zu beachten, dass sowohl die Leere Menge, als
auch die Menge selbst immer in der Potenzmenge enthalten sind.

#### Vereinigung, Durchschnitt, Differenz, Komplement

##### Definition

Die **Vereinigung** zweier Mengen $A$ und $B$ ist folgendermaßen
definiert: $A \cup B := \{x \mid x \in A \lor x \in B\}$.\
Der **Durchschnitt** zweier Mengen $A$ und $B$ ist definiert als:
$A \cap B := \{x \mid x \in A \land x \in B\}$.\
Die **Differenz** zweier Mengen $A$ und $B$ ist die Menge aller
Elemente, die in $A$ vorkommen, aber nicht in $B$:
$A \setminus B := \{x \in A \mid x \notin B\}$\
Das **Komplement** einer Menge $A$ in einem Universum $U$ ist die Menge
aller Elemente in $U$, die nicht in $A$ sind:
$\bar{A} := \{x \in U \land x \notin A\}$.

#### Gesetze für Mengenoperationen

Für alle Mengen $A$, $B$ und $C$ gelten die folgenden Gesetze:
$$\begin{gathered}
A \cup A = A\\
A \cap A = A\\
A \cap B = B \cap A\\
A \cup B = B \cup A\\
A \cap (B \cap C) = (A \cap B) \cap C\\
A \cup (B \cup C) = (A \cup B) \cup C\\
A \cap (A \cup B) = A\\
A \cup (A \cap B) = A\\
A \cap (B \cup C) = (A \cap B) \cup (A \cap C)\\
A \cup (B \cap C) = (A \cup B) \cap (A \cup C)\\
A \subseteq B \Leftrightarrow A \cap B = A \Leftrightarrow A \cup B = B\end{gathered}$$

#### Kartesisches Produkt

##### Definition

Das Kartesische Produkt zweier Mengen $A$ und $B$ ist die Menge aller
geordneten Paare, in denen das erste Element in $A$ und das zweite
Element in $B$ existtiert:
$A \times B := \{(a,b) | a \in A \land b \in B\}$.

Bei endlichen Mengen gilt, dass die Kardinalität des Kartesischen
Produktes der Mengen $A$ und $B$ gleich dem Produkt der Kardinalitäten
der beiden Mengen ist.

### Relationen
Relationen sind ein fundamentales Konzept in der diskreten Mathematik
und Informatik.

##### Definition

Eine Relation $\rho$ von einer Menge $A$ zu einer Menge $B$ ist eine
Teilmenge von $A \times B$. Wenn $A=B$, wird $\rho$ eine Relation auf
$A$ genannt.

Relationen sind also immer Mengen geordneter Paare $(a,b)$ mit $a \in A$
und $b \in B$. Man schreibt entweder $(a,b) \in \rho$ oder aber häufiger
$a \rho b$, bzw. $(a,b) \notin \rho$ oder $a \not\rho b$.

#### Repräsentationen von Relationen

Es gibt verschiedene Möglichkeiten Relationen darzustellen. Man kann
eine Relation von $A$ nach $B$ als $\mid A \mid \times \mid B \mid$
Matrix darstellen und mit Einsen und Nullen aller Paare markieren, die
in der Relation enthalten sind.\
Eine andere Möglichkeit der Darstellung ist ein gerichteter Graph mit
$\mid A \mid + \mid B \mid$ Knoten. Die Kanten geben dann die in der
Relation enthaltenen Paare an.

#### Mengenoperationen

Da Relationen auch Mengen sind, lassen sich die normalen
Mengenoperationen auf sie anwenden. Es gibt also Vereinigungen,
Durchschnitte und Komplemente von Relationen. Dargestellt in der Matrix
sind diese Operationen eine logische UND oder ODER Verknüpfung
entsprechender Werte bzw. eine Negation.

#### Inverse von Relationen

Das Inverse einer Relation $\rho$ von einer Menge $A$ zu einer anderen
Menge $B$ ist die Relation $\hat{\rho}$, sodass
$\forall a \in A \forall b \in B (a \rho b \leftrightarrow b \hat{\rho} a)$
gilt. Manchmal wird anstelle von $\hat{\rho}$ auch $\rho ^{-1}$
geschrieben.

#### Verbindung von Relationen

##### Definition

Sei $\rho$ eine Relation von $A$ nach $B$ und $\sigma$ eine Relation von
$B$ nach $C$, dann ist die Verbindung der beiden Relationen $\rho\sigma$
oder auch $\rho \circ \sigma$ eine Relation von $A$ nach $C$, sodass
$a \rho\sigma c :\Leftrightarrow \exists b \in B (a \rho b \land b \sigma c)$
gilt.

Es gilt hierbei $\hat{\rho\sigma} = \hat{\sigma}\hat{\rho}$.

#### Besondere Eigenschaften von Relationen

Relationen können bestimmte Eigenschaften haben. Im Folgenden werden
diese kurz erläutert:

##### Reflexivität

Eine Relation $\rho$ wird reflexiv genannt, wenn
$\forall a (a,a) \in \rho$, also wenn die Identitätsrelation eine
Teilmenge der Relation ist. In der Graphendarstellung ist das genau dann
der Fall, wenn jeder Knoten eine Schleife aufweist.

##### Symmetrie

Eine Relation $\rho$ wird symmetrisch genannt, wenn
$\forall a \forall b (a \rho b \leftrightarrow b \rho a)$gilt, also die
inverse Relation von $\rho$ gleich $\rho$ ist.

##### Antisymmetrie

Eine Relation $\rho$ wird antisymmetrisch genannt, wenn
$\forall a \forall b ((a \rho b \land b \rho a) \rightarrow a = b)$
gilt. Damit ist Antisymmetrie nicht das Gegenteil von Symmetrie.

##### Transitivität

Eine Relation $\rho$ wird transitiv genannt, wenn
$\forall a \forall b \forall c ((a \rho b \land b \rho c) \rightarrow a \rho c)$
gilt.

### Äquivalenzrelationen

Eine Relation $\rho$ ist eine Äquivalenzrelation, wenn sie reflexiv,
symmetrisch und transitiv ist. Alle Elemente der Menge, auf der $\rho$
definiert ist, die zueinander in der $\rho$ Relation sind, befinden sich
in einer sogenannten Äquivalenzklasse, was wie folgt notiert wird:
$[a]_{\rho} := \{b \in A | b \rho a\}$. Äquivalenzklassen lassen sich als
Graph darstellen. In einer Menge sind alle Elemente, die sich in einer
Äquivalenzklasse befinden mit Schleifen ausgestattet (reflexiv),
untereinander immer in beide Richtungen verbunden (symmetrisch) und es
sind jeweils alle Elemente einer Klasse miteinander verbunden
(transitiv). Es werden also Zusammenhangskomponenten dargestellt. Damit
partitionieren Äquivalenzrelationen Mengen.

### Partielle Ordnungsrelationen

Eine partielle Ordnung auf einer Menge $A$ ist eine Relation, die
reflexiv, antisymmetrisch und transitiv ist. Eine Menge mit einer
solchen Ordnungsrelation wird partiell geordnete Menge oder auch poset
genannt. Wenn alle Elemente einer Menge untereinander vergleichbar sind,
spricht man von einer totalen Ordnung, es gibt also auch Mengen, in
denen Elemente vorkommen, die nicht miteinander vergleichbar sind.
Mithilfe von Hasse-Diagrammen werden Ordnungsrelationen visualisiert.

#### Hasse-Diagramme

Wie bereits erwähnt werden Hasse-Diagramme zur Visualisierung von
Ordnungsrelationen verwendet. Es gibt hierbei ein paar wichtige
Begriffe:

##### maximale/minimale Elemente
sind die Elemente eines Hasse-Diagramms, für die gilt, dass kein anderes Element größer resp. kleiner ist.

##### kleinstes/größtes Element
ist ein Element dann, wenn es nur ein maximales/minimales Element
gibt.

Diese Begriffe lassen sich auch auf Teilmengen im Hasse Diagramm
anwenden. Dann kommen noch weitere Begriffe hinzu:

##### untere/obere Schranken
sind all diejenigen Elemente im Hasse-Diagramm, die unter/über allen Elementen der Teilmenge stehen. HIerbei muss eine Verbindung (Vergleichbarkeit) gegeben sein.

##### grösste untere/kleinste obere Schranke
ist das jeweilige Element, welches das grösste/kleinste Element der unteren/oberen Schranken einer Teilmenge ist.

##### meet
grösste untere Schranke

##### join
kleinste obere Schranke

##### Verband/lattice
Wenn es sowohl ein meet, als auch ein join gibt, wird die partielle Ordnungsrelation auch Verband oder engl. lattice genannt.

### Funktionen
Funktionen sind das wohl zweit-wichtigste Konzept der Mathematik nach
den Mengen. Sie sind spezielle Relationen, die durch zwei wichtige
Eigenschaften von anderen Relationen unterschieden werden können:

1.  Eine Funktion ist immer total definiert. D.h. für jedes Element des
    Definitionsbereiches gibt es ein Element im Wertebereich.
    $\forall a \in A (\exists b \in B (a f b))$ Wobei $f$ die Funktion
    mit Definitionsbereich $A$ und Wertebereich $B$ ist.

2.  Eine Funktion ist wohldefiniert. D.h. für jedes Element des
    Definitionsbereiches gibt es nur ein einziges Element im
    Wertebereich.
    $\forall a \in A (\forall b,b\prime \in B (a f b \land a f b\prime \rightarrow b = b\prime))$.
    Wobei $f$ die Funktion mit Definitionsbereich $A$ und Wertebereich
    $B$ ist.

Wenn die erste Bedingung nicht erfüllt ist, spricht man von partiellen
Funktionen.

#### Besondere Eigenschaften

##### injektiv
Eine Funktion ist injektiv, wenn kein Wert des Bildbereiches doppelt belegt ist

##### surjektiv
Eine Funktion ist surjektiv, wenn jeder Wert des Bildbereiches belegt ist

##### bijektiv
Eine Funktion ist bijektiv, wenn sie sowohl injektiv als auch surjektiv ist. Nur die inversen von bijektiven Funktionen sind auch Funktionen.

### Zählbarkeit von Mengen

##### Definition
-   Zwei Mengen $A$ und $B$ werden als gleichmächtig ($A \sim B$)
    bezeichnet, wenn es eine Bijektion $A \rightarrow B$ gibt.
-   $B$ dominiert $A$ ($A \preceq B$) genau dann, wenn es eine Bijektion
    $A \rightarrow C$ gibt, mit $C \subseteq B$.
-   Eine Menge $A$ wird abzählbar genannt, wenn $A \preceq \mathbb{N}$
    und überabzählbar, wenn es nicht so ist. Die Relation $\preceq$ ist
    transitiv.
-   Eine Menge ist genau dann abzählbar, wenn sie endlich ist oder von
    $\mathbb{N}$ dominiert wird.

#### Beispiele für abzählbare Mengen

##### $\{0,1\}^*$
Die Menge der endlichen Folgen aus Nullen und Einsen ist abzählbar. Die
Injektion auf $\mathbb{N}$ ist dadurch gegeben, dass jeder String durch
hinzufügen einer Eins am Anfang durch die Standardumwandlung von
Binärzahlen als natürliche Zahl zu interpretieren ist.

##### $\mathbb{N} \times \mathbb{N}$
Die Menge der Paare aus natürlichen Zahlen ist ebenfalls abzählbar. Hier
ist die Injektion ein Pfad durch den ersten Quadrantes des
Koordinatensystems der immer schräg von einem Punkt aus natürlichen
Zahlen zum nächsten geht. Jeder Schritt wird gezählt. Hieraus folgt,
dass jedes Kartesische Produkt zweier abzählbarer Mengen auch abzählbar
ist. Zusätzlich auch dass die Rationalen Zahlen, die sich als Paar
$(m,n)$ mit $m \in \mathbb{Z}, n\in \mathbb{N} \setminus\{0\}$
darstellen lassen, abzählbar sind.

##### Weitere Kombinationen abzählbarer Mengen $A, A_i, i\in \mathbb{N}$
-   Für alle $n\in \mathbb{N}$ ist $A^n$abzählbar
-   $\cup_{i\in \mathbb{N}}A_i$ der abzählbaren Liste aus $A_i$
-   $A^*$

##### $(\{0,1\}^*)^*$

Um die Abzählbarkeit der endlichen Folgen endlicher Folgen aus Einsen
und Nullen zu beweisen, lässt sich eine Kodierung für Nullen, Einsen und
Trennungen finden, mit der die Endlichen Folgen zu einer Folge
zusammengeführt werden können.

#### Überabzählbare Mengen

##### $\{0,1\}^\infty$

Die Menge der unendlichen Folgen von Einsen und Nullen ist
überabzählbar. Beweisen lässt sich dies mit "Cantors
Diagonalisierungsargument", einem Widerspruchsbeweis. Hierfür wird eine
Tabelle erstellt, in der linken Spalte steht die natürliche Zahl, die
der Folge in der rechten Spalte zugeordnet wird. Nun wird die Folge
betrachtet, die aus den invertierten Elementen der Diagonalen durch die
rechte Spalte besteht. Auch diese Folge ist eine Unendliche Folge und
hat zu jeder anderen Folge mindestens ein Element, dass sich
unterscheidet. Da diese Folge auch eine unendliche Folge ist, muss sie
in der Tabelle vorkommen und sich damit von sich selbst unterscheiden.
Daher lässt sich eine solche Tabelle und damit Injetkion nicht
erstellen.

#### Berechenbarkeit von Programmen

Da die Menge der Funktionen, die eine Natürliche Zahl auf Null oder Eins
abbilden unendlich ist, ein Computerprogramm aber nur aus endlichen
Zeichen bestehen kann, gibt es Funktionen, die ein Computer nicht
berechnen kann. Diese sind tatsächlich deutlich mehr, als die
berechenbaren. Ein fundamentales Problem der Informatik.

## Esoterik (Zahlentheorie)
Durch Anwendung in der Kryptographie aber auch sonst, ist die
Zahlentheorie von außerordentlicher Wichtigkeit. Trotzdem wird hier nur
eine kurze Einführung gegeben. Es werden Fakten als bekannt
vorausgesetzt, die normalerweise eines Beweises bedürfen. In Teilen wird
hier von der algebraischen Struktur des Rings gesprochen, der im Detail
erst im nächsten Kapitel erklärt wird.

### Teiler und die Division
##### Definitionen
Für beliebige zwei natürliche Zahlen $a$ und $b$ sagt man, dass $a$ $b$
teilt ($a \mid b$), wenn es eine andere natürliche Zahl $c$ gibt, sodass
$b = a*c$ gilt. In diesem Fall wir $a$ als Teiler bezeichnet und $b$ ist
ein Vielfaches von $a$. Für beliebige natürliche Zahlen $a$ und
$d\neq 0$ gilt, dass zwei natürliche Zahlen $q$ und $r$ existieren,
sodass $a=dq+r$ mit $0 \leq r < |d|$.Hier wird $a$ als Dividend, $d$ als
Divisor, $q$ als Quotient und $r$ als Rest bezeichnet. Dieses Theorem
geht auf Euklid zurück.

#### Größte gemeinsame Teiler (ggT/gcd)

Der grösste gemeinsame Teiler $d$ zweier Zahlen $a$ und $b$ teilt $a$
und $b$. Außerdem teilt jeder andere gemeinsame Teiler von $a$ und $b$
$d$. Dieses Konzept gibt es nicht nur für die natürlcihen und ganzen
Zahlen, sondern auch für alle Ringe. Ist der grösste gemeinsame Teiler
zweier Zahlen gleich 1, so werden diese als teilerfremd bezeichnet.

#### Ideale

Für zwei ganze Zahlen $a$ und $b$ ist das Ideal $(a,b)$definiert als die
Menge aller Zahlen, die als Linearkombination von $a$ und $b$ mit
anderen ganzen Zahlen gebildet werden können. Entsprechend ist das Ideal
einer Zahl die Menge aller Zahlen, von denen diese Zahl ein Teiler ist.
Für jedes Ideal zweier Zahlen $(a,b)$ gibt es eine andere Zahl $d$,
deren Ideal $(d)$, dem von $a$ und $b$ entspricht. Hier ist $d$ der ggT
von $a$ und $b$. Daraus folgt, dass für alle Zahlen $a$ und $b$ der ggT
als Linearkombination der beiden Zahlen mit ganzen Zahlen geschrieben
werden kann.

#### Euklids ggT-Algorithmus

### Primzahlzerlegung
Ein großer Teil des Kapitels über Primzahlzerlegung ist nicht
prüfungsrelevant. Das gilt jedoch nicht für die Irrationalität von
Wurzeln. Alle Quadratwurzeln natürlicher Zahlen sind irrational, außer
die natürliche Zahl ist eine Quadratzahl.

### Kongruenzen und modulare Arithmetik
#### Modulare Kongruenzen

##### Definition modulare Kongruenz

Für ganze Zahlen $a,b,m$ mit $m\geq 1$ sagen wir, $a$ ist kongruent zu
$b$ modulo $m$, wenn $m$ $a-b$ teilt:
$a \equiv_m b :\Leftrightarrow m \mid (a-b)$. Für jedes $m \geq 1$ ist
$\equiv_m$ eine Äquivalenzrelation.

##### Lemma 4.15

Gilt $a \equiv_m b$ und $c \equiv_m d$, dann gilt auch
$a+c \equiv_m b+d$ und $ac \equiv_m bd$.

#### Modulare Arithmetik

Die Äquivalenzrelation $\equiv_m$ hat genau $m$ Äquivalenzklassen:
$[0],[1],...,[m-1]$. Wenn man bei einer Addition oder Multiplikation nur
an dem Rest des Ergebnisses modulo $m$ interessiert ist, kann man auch
die Reste an einem beliebigen Zwischenschritt betrachten, ohne das
Ergebnis zu verändern (Lemma 4.18): $R_m(a+b) = R_m(R_m(a) + R_m(b))$und
$R_m(ab) = R_m(R_m(a)*R_m(b))$ gelten.

#### Multiplikative Inverse

Betrachtet man eine Kongruenzgleichung $ax \equiv_m b$, so ist, sofern
$x$ eine Lösung ist, $x+km$ für jedes $k \in \mathbb{Z}$ eine Lösung der
Gleichung. Besonders interessant ist der Fall, wenn $gcd(a,m)=1$ und
$b=1$:

##### Lemma 4.19

Die Kongruenzgleichung $ax\equiv_m 1$ hat genau dann eine Lösung
$x \in \mathbb{Z}_m$, wenn $gcd(a,m)=1$. Die Lösung ist dabei eindeutig.
Wenn $gcd(a,m)=1$, wird die eindeutige Lösung $x \in \mathbb{Z}_m$ der
Kongruenzgleichung $ax \equiv_m 1$ das "multiplikativ Inverse von $a$
modulo $m$" genannt. Man schreibt auch: $x\equiv_m a^{-1}$ oder
$x \equiv_m 1/a$. Das multiplikativ Inverse von $a$ modulo $m$ kann
mithilfe des euklidschen Algorithmus sehr einfach berechnet werden. Wenn
$gcd(a,m) \neq 1$, dann hat $a$ modulo $m$ kein multiplikativ Inverses.

#### Das Chinese Remainder Theorem

Seien $m_1,m_2,...,m_r$ paarweise teilerfremde natürliche Zahlen (es
gibt kein $gcd(m_i,m_j)>1$) und sei $M=\prod_{i=1}^rm_i$. Dann hat das
System von Kongruenzgleichungen $$\begin{gathered}
x \equiv_{m_1} a_1\\
x \equiv_{m_2} a_2\\
...\\
x \equiv_{m_r} a_r\\\end{gathered}$$ für jede Liste $a_1,...,a_r$ mit
$0\leq a_i < m_i$ für $1\leq i \leq r$ eine eindeutige Lösung $x$ mit
$0 \leq x < M$.

## Algebra

### Allgemeines
In der Algebra geht es um bestimmte Strukturen, die aus einer Menge und
Operationen auf dieser Menge bestehen. Hierbei ist die Operation auf
einer Menge $S$ definiert als eine Funktion $S^n \rightarrow S$, wobei
$n$ die Stelligkeit der Operation ist. Eine Algebra, auch algebraische
Struktur genannt, ist ein Paar $\langle S;\Omega \rangle$, wobei $S$ die
Menge, auch Trägermenge, und
$\Omega=(\omega_1, \omega_2, ..., \omega_n)$eine Liste von Operationen
ist.

### Monoiden und Gruppen
Eine Algebra $\langle S; * \rangle$ kann verschiedene Eigenschaften
haben. Drei wichtige davon sind die folgenden:
1.  Die Algebra kann neutrale Elemente enthalten
2.  Ein Assoziativgesetz kann gelten
3.  Es kann inverse Elemente geben

Hierbei sind auch Kombinationen möglich.

Ein **Monoid** ist eine Algebra $\langle M; *, e \rangle$, wobei $*$
assoziativ ist und $e$ ein neutrales Element.

Eine **Gruppe** $\langle G; *, \hat , e \rangle$ ist eine Algebra, für
die die folgenden Axiome gelten:
* G1: ist assoziativ
* G2: Es existiert ein neutrales Element $e \in G$, sodass $a*e=e*a=a$ für alle $a\in G$
* G3: Jedes $a \in G$ hat eine inverses Element $\hat a$, sodass $a*\hat a = \hat a * a = e$ gilt.

### Struktur von Gruppen
#### Direktes Produkt von Gruppen

Das direkte Produkt der Gruppen $\langle G_1; *_1\rangle, ...,  \langle G_n; *_n\rangle​$ ist definiert als die algebraische Struktur $\langle G_1 \times G_2 \times ... \times G_n; \star \rangle​$- also eine Menge von $n​$-Tupeln verknüpft mit $\star​$ -, wobei $\star​$ definiert ist als komponentenweise Anwendung der Operation $*_i​$:
$$
(a_1,...,a_n) \star (b_1,...,b_n) = (a_1*_1b_1, ..., a_n *_n b_n)
$$
Die algebraische Struktur
$\langle G_1 \times G_2 \times ... \times G_n; \star \rangle​$ ist eine
Gruppe, wobei das neutrale Element und die inversen Elemente jeweils
komponentenweise aus den entsprechenden Gruppen
$\langle G_1; *_1\rangle, ...,  \langle G_n; *_n\rangle​$ gewählt wird.

#### Homomorphismen in Gruppen
Ein Gruppenhomomorphismus ist eine Strukturerhaltende Funktion von einer
Gruppe in eine andere. Homomorphismen sind eigentlich für alle
algebraischen Strukturen definiert, wir betrachten jedoch nur den Fall
für Gruppen. Eine Funktion $\psi: \langle G;*,\hat{},e \rangle \longrightarrow \langle H;\star,\tilde{}, e\prime \rangle$ ist ein Gruppenhomomorphismus, wenn für alle $a,b \in G$ gilt: $$\psi(a*b) = \psi(a) \star \psi(b)$$. Ist $\psi$ eine Bijektion, so spricht man von einem Isomorphismus: \"$G$ und $H$ sind isomorph\" $G \simeq H$.

#### Untergruppe

Eine Teilmenge $H \subseteq G$ einer Gruppe
$\langle G;*,\hat{},e \rangle$ wird Untergruppe von $G$ genannt, sofern
$\langle H;*,\hat{},e \rangle$ eine Gruppe ist. Dafür muss
$\langle H;*,\hat{},e \rangle$ bezüglich aller Operationen abgeschlossen
sein: 
$$
\forall a,b \in H: a*b \in H\\
e \in H\\
\forall a \in H: \hat{a} \in H
$$
Die Menge aus dem
neutralen Element, sowie die Gruppe selbst sind stets die trivialen
Untergruppen.

#### Ordnung
Die Ordnung eines Elements $a$ ist das geringste $m$, sodass $a^m=e$ ist. Hier wird die Multiplikationsschreibweise verwendet. Es kann aber für alle Operationen so angewandt werden. Wenn es kein solches $m$ gibt, so ist die Ordnung des Elements $\infty$. Wenn jedes Element einer Gruppe eine endliche Ordnung besitzt, so ist auch die Gruppe endlich. Die Ordnung einer Gruppe ist gleich der Anzahl der Elemente in der Gruppe.

#### Zyklische Gruppen
Lässt sich eine Gruppe $G$ als $<g>=\{g^n \mid n \in \mathbb{Z} \}$ schreiben ($g \in G$), so wird $G$ zyklisch genannt. Hierbei wird $g$ als Generator bezeichnet und $<g>$ ist stets die kleinste Untergruppe von $G$, die $g$ enthält. Wenn eine Gruppe zyklisch ist, so ist die Ordnung der Gruppe $|G|=n$. Jede dieser Gruppen ist isomorph zu $\mathbb{Z}_n$.

#### Die Ordnung von Untergruppen

##### Theorem 5.8 (Lagrange)

Die Ordnung jeder Untergruppe $H$ einer endlichen Gruppe $G$ teilt deren Ordnung: $|H| \mid |G|$.

##### Korollar 5.9

Die Ordnung jedes Elements $a$ einer Gruppe $G$ teilt deren Ordnung: $\forall a \in G: ord(a) \mid |G|$.

##### Korollar 5.10

In jeder endlichen Gruppe $G$ der Ordnung $|G|$ gilt: $\forall a \in G: a^{|G|} = e$.

##### Korollar 5.11 

Jeder Gruppe $G$, deren Ordnung prim ist, ist zyklisch und jedes Element mit Ausnahme des neutralen ist ein Generator von $G$.

#### Die Gruppe $\mathbb{Z}_m^*$ und die Euler-Funktion

##### Definition 5.16

$\mathbb{Z}_m^* := \{a \in \mathbb{Z}_m \mid gcd(a,m)=1\}$

##### Definition 5.17

Die Eulerfunktion $\varphi: \mathbb{Z}^+ \longrightarrow \mathbb{Z}^+$ist definiert als die Kardinalität von $\mathbb{Z}_m^*$: $\varphi(m) = |\mathbb{Z}_m^*|$.

##### Lemma 5.12 

Sei $m=\prod_{i=1}^{r}p_i^{e_i}$ die Primfaktorzerliegung von $m$, dann gilt:
$$
\varphi(m) = \prod_{i=1}^{r}(p_i-1)p_i^{e_i-1}
$$

##### Theorem 5.13

$\langle \mathbb{Z}_m^*; \odot, ^{-1}, 1\rangle$ ist eine Gruppe.



### Anwendung: RSA Verschlüsselung

##### Theorem 5.16

Sei $G$ eine endliche Gruppe (im Folgenden als multiplikative geschrieben) und $e \in \mathbb{Z}$ teilerfremd zu $|G|$. Dann ist die (eindeutig bestimmte) $e$-te Wurzel $x = y^d \in G$ von $y \in G$, wobei $d$ das multplikativ inverse von $e$ modulo $|G|$ ist. Es gilt also: $ed \equiv_{|G|} 1$.

Sollen Nachrichten über das RSA-Verfahren ausgetauscht werden, so werden zunächst Schlüssel ausgetauscht. Dafür generiert der Empfänger der Nachricht zwei Primzahlen $p$ und $q$, aus denen er ein $n$ mit $n=p*q$, sowie ein $f$ mit $f=(p-1)(q-1)$ errechnet. Nun lässt sich ein privater Schlüssel $d$ durch $d \equiv_f e^{-1}$ errechnen. Das Paar $n,e$ kann als öffentlicher Schlüssel an den Sender weitergegeben werden, der den Klartext m \in \{1,...,n-1\}$ in den verschlüsselten Text $y=R_n(m^e)$ kodiert. und an den Empfänger verschickt. Dieser kann durch $m=R_n(y^d)$ den Klartext berechnen.

### Ringe und Körper

#### Ring

##### Definition 5.18: Ring

Ein Ring ist eine Algebra, $\langle R; +,-,0,*,1\rangle$, wobei:

1. $\langle R;+,-,0\rangle$ eine kommutative Gruppe ist
2. $\langle R;*,1\rangle$ ein Monoid ist
3. Das linke und rechte Distributivgesetz gilt: $a(b+c) = ab+ac$ und $(b+c)a = ba+ca$

Ist die Multiplikation zusätzlich noch kommutativ, so spricht man von einem kommutativen Ring.

##### Lemma 5.17

Für alle Ringe $\langle R; +,-,0,*,1\rangle$ und $a,b \in R$ gilt:

1. $0a=a0=0$
2. $(-a)b=-(ab)$
3. $(-a)(-b)=ab$
4. Wenn $R$ mehr als ein Element enthält, ist $1 \neq 0$. Daher gilt in jedem nicht-trivialen Ring, dass $0$ kein multiplikativ inverses hat, weswegen $\langle R;*,1\rangle$ keine Gruppe, sondern nur ein Monoid sein kann.

##### Definition 5.19

_The characteristic_ einer Gruppe ist die Ordnung von $1$ in der additiven Gruppe. Wenn diese nicht endlich ist, so ist es 0.

#### Teiler

##### Definition 5.20

Für alle $a,b \in R$ mit $a\neq0$ , teilt $a$ $b$  ($a \mid b$)genau dann, wenn ein $c$ existiert, sodass $b=ac$.  HIer ist $a$ der Divisor von $b$ und $b$ ist ein Vielfaches von $a$.

##### Lemma 5.18

In jedem kommutativen Ring gilt:

1. Die Teilerrelation ist transitiv: $((a \mid b) \land (b \mid c)) \rightarrow a\mid c$
2. $\forall a,b,c: a\mid b \rightarrow a \mid bc$
3. $(a\mid b \land a \mid c) \rightarrow a\mid (b+c)$

##### Definition 5.21

Für zwei Ringelemente $a,b$ (beide nicht $0$) wird ein Ringelement $c$ der grösste gemeinsame Teiler von $a$ und $b$ genant, wenn $d|a \land d|b$ und jeder andere gemeinsame Teiler von $a$ und $b$ $d$ teilt.

#### Einheit, Nullteiler und Integritätsbereiche

##### Definition 5.22: Nullteiler

Ein Element $a\neq0$ eines kommutativen Rings $R$ wird Nullteiler genannt, wenn für ein $b\in R$ gilt: $ab=0$.

##### Definition 5.23: Einheit

Ein Element $u$ eines (kommutativen) Rings $R$ wird Einheit genannt, wenn ein Inverses von $u$ in $R$ existiert: $\exists v: uv=vu=1$. Man schreibt dabei $v=u^{-1}$. Die Menge der Einheiten in $R$ wird $R^*$ geschrieben.

##### Lemma 5.19

Für jeden Ring $R$ ist $R^*$ eine multiplikative Gruppe.

##### Definition5.24 Integritätsbereich

Ein nicht-trivialer, kommutativer Ring ohne Nullteiler wird Integritätsbereich genannt: $\forall a,b: (ab=0 \rightarrow a=0 \lor b=0)$.

##### Lemma 5.20

In jedem Integritätsbereich gilt: Ist $b$ ein Vielfaches von $a$, so ist $c$ mit $ac=b$ eindeutig bestimmt. Man schreibt auch $c=\frac{b}{a}$ . $c$ wird hier auch Quotient genannt.

#### Polynomielle Ringe

##### Definition 5.25

Ein Polynom $a(x)$ über einem Ring $R$ in der Indeterminante $x$ ist ein formaler Ausdruck der Form:
$$
a(x) = a_dx^d+a_{d-1}x^{d-1}+...+a_1x^1+a_0 = \sum_{i=0}^{d}a_ix^i
$$
Hier ist $d$ eine nicht-negative ganze Zahl und $a_i \in R$. Der Grad von $a(x)$, $deg(a(x))$, ist das grösste $i$, für das $a_i\neq 0$ ist. Das Polynom, in dem jedes $a_i=0$ ist, hat den Grad $-\infty$. Die Mege aller Polynome über einem Ring $R$ wird $R[x]$ geschrieben.

##### Theorem 5.21

Für jeden Ring $R$ ist $R[x]$ ein Ring.

##### Lemma 5.22

1.  Ist $D$ ein Integritätsbereich, so ist auch $D[x]$ einer.
2. Die Einheiten von $D[x]$ sind die konstanten Polynome, die Einheiten von  $D$ sind: $D[x]^*=D*$

#### Körper

##### Definition 5.26

Ein Körper ist ein nicht-trivialer kommutativer Ring, in dem jedes Element außer $0$ eine Einheit ist: $F^*=F\setminus\{0\}$.

##### Theorem 5.23

$\mathbb{Z}_p$ ist genau dann ein Körper, wenn $p$ prim ist. Diese Körper werden nach dem Mathematiker Galois mit $GF(p)$ bezeichnet.

##### Theorem 5.24

Jeder Körper ist ein Integritätsbereich.

---

Polynome über einem Körper lassen sich faktorisieren, weswegen man bei ihnen auch von Teilern sprechen kann.

##### Definition 5.27

Ein Polynom $a(x) \in F[x]$ wird monisch genant, wenn der erste Koeffizient 1 ist.

##### Definition 5.28

Ein Polynom $a(x) \in F[x]$ mit Grad größer gleich 1 wird irreduzierbar genannt, wenn es nur durch konstante Polynome und konstante Vielfache teilbar ist. Daher ist jedes Polynom vom Grad 1 irreduzierbar. Um Irreduzierbarkeit eines Polynoms $a(x)$ zu testen, kann getestet werden, ob es durch die monischen Polynome mit Grad kleiner gleich $deg(a(x))/2$ teilbar ist.

##### Definition 5.29

Das monische Polynom $g(x)$ des größten Grades, das $a(x)$ und $b(x)$ teilt, ist der grösste gemeinsame Teiler dieser beiden Polynome und wird auch $gcd(a(x),b(x))$ geschrieben.

##### Theorem 5.25

Sei $F$ ein Körper. Für jedes $a(x)$ und $b(x) \neq 0$ in $F$ existiert genau ein $q(x)$ und $r(x)$, sodass $a(x)=b(x)*q(x)+r(x)$, wobei der Grad von $r(x)$ kleiner ist als der von $b(x)$.

### Polynome als Funktionen

Für einen Ring $R$ kann ein Polynom $a(x)$ als Funktion $R \longrightarrow R$ interpretiert werden. Hierzu wird die Auswertung von $a(x)$ bei $\alpha \in R$ wie üblich betrachtet. Dabei gilt:
$$
c(x) = a(x) + b(x) \rightarrow c(\alpha) = a(\alpha) + b(\alpha)\\
c(x) = a(x) * b(x) \rightarrow c(\alpha) = a(\alpha) * b(\alpha)\\
$$

#### Wurzeln oder Nullstellen

##### Definition 5.33

Sei $a(x) \in R[x]$. Ein Element $\alpha\in R $, für welches $a(\alpha) = 0$ gilt, wird Wurzel oder Nullstelle von $a(x)$ genannt.

##### Lemma 5.28

In einem Körper $F$ ist $\alpha \in F$ genau dann eine Wurzel oder Nullstelle von $a(x)$, wenn $(x-\alpha)|a(x)$. Dies impliziert, dass ein irreduzierbares Polynom vom Grad größer gleich 2 keine Wurzeln/Nullstellen hat.

##### Korollar 5.29

Ein Polynom $a(x)$ vom Grad 2 oder 3 über dem Körper $F$ ist genau dann irreduzierbar, wenn es keine Wurzeln/Nullstellen hat.

##### Definition 5.34

Wenn $\alpha$ eine Nullstelle von $a(\alpha)$ ist, dann ist die _multiplicity_ der höchste Exponent von $x-\alpha$, der $a(x)$ teilt.

##### Theorem 5.30

Für einen Körper $F$ hat ein Polynom $a(x)\neq0\in F[x]$ vo Grad $d$ höchstens $d$ Nullstellen, wobei _multiplicities_ mitgezählt werden.

#### Polynominterpolation

##### Lemma 5.31

Ein Polynom $a(x) \in F[x]$ vom Grad $\leq d$ ist eindeutig bestimmt durch beliebige $d+1$ Werdet für $a(x)$. Man kann also durch die Angabe von $d+1$ Werten für $\alpha$ und $a(x)$ ein Polynom eindeutig bestimmen.

### Endliche Körper

#### Der Ring $F[x]_{m(x)}$

##### Lemma 5.32

Kongruenz modulo einem Polynom $m(x)$ ist eine Äquivalenzrelation auf $F[x]$. Hier hat jede Äquivalenzklasse ein eindeutig bestimmtes Element vom Grad $\leq deg(m(x))$.

##### Definition 5.35

Sei $m(x)$ ein Polynom mit Grad $d$ über dem Körper $F$. Dann ist:
$$
F[x]_{m(x)} := \{a(x) \in F[x] \mid deg(a(x)) < d\}
$$

##### Lemma 5.33

Sei $F$ ein endlicher Körper mit $q$ Elementen und $m(x)$ ein Polynom mit Grad $d$ über $F$. Dann ist $|F[x]_{m(x)}|=q^d$.

##### Lemma 5.34

$F[x]_{m(x)}$ ist ein Ring bezüglich der Addition und Multiplikation modulo $m(x)$.

##### Lemma 5.35

Die Kongruenzgleichung $a(x)b(x) \equiv_{m(x)}1$ hat genau dann eine Lösung für ein gegebenes $a(x)$, wenn $gcd(a(x),m(x)) = 1$. Diese Lösung ist eindeuig bestimmt. Es gilt also:
$$
F[x]_{m(x)}^*=\{a(x) \in F[x]_{m(x)} \mid gcd(a(x), m(x)) = 1\}
$$

#### Körper aus Polynomen

##### Theorem 5.36

Der Ring $F[x]_{m(x)}$ ist genau dann ein Körper, wenn $m(x)$ irreduzierbar ist.

### Anwendung: Fehler-korrigierende Codes

#### Definitionen

##### Definition 5.36

Eine $(n,k)$-kodierende Funktion $E$ für ein Alphabet $\mathcal{A}$ ist eine injekive Funktion, die eine Liste $(a_0,...,a_{k-1}) \in A^k$ aus $k$ Symbolen auf eine Liste $(c_0,...,c_{n-1})\in \mathcal{A}^n$ aus $n> k $ Symbolen, auch Codewort genannt, abbildet:
$$
E: \mathcal{A}^k \longrightarrow \mathcal{A}^n: 
(a_0,...,a_{k-1}) \mapsto E((a_0,...,a_{k-1})) = (c_0,...,c_{n-1})
$$
Die Menge $\mathcal{C} = Im(E) = \{E((a_0,...,a_{k-1})) \mid a_0,...,a_{k-1} \in \mathcal{A} \}$ wird Fehler-korrigierender Code genannt.

##### Definition 5.37

Ein $(n,k)$-Fehler-korrigierender Code über einem Alphabet $\mathcal{A}$ mit $|\mathcal{A}|=q$ ist eine Teilmenge der Kardinalität $q^k$ von $\mathcal{A}^n$.

##### Definition 5.38

Die Hamming Distanz zwischen zwei Strings gleicher Länge über einem Alphabet ist die Anzahl an Positionen, an denen die Strings sich unterscheiden.

##### Definition 5.39

Die Minimaldistanz eines Fehler-korrigierenden Codes $\mathcal{C}$ ist das Minimum der Hamming Distanzen zwischen zwei beliebigen Codewörtern.

#### Dekodieren

##### Definition 5.40

Eine Dekodierfunktion $D$ für einer $(n,k)$-kodierende Funktion ist eine Funktion $D: \mathcal{A}^n \longrightarrow \mathcal{A}^k$. 

##### Definition 5.41

Eine Dekodierfunktion $D$ ist $t$-Fehler-korrigierend für eine Kodierfunktion $E$, wenn $\forall (a_0,...,a_{k-1}): D((r_0,...,r_{n-1}))=(a_0,...,a_{k-1})$ für beliebige $(r_0,...,r_{n-1})$ mit der Hamming Distanz von höchstens $t$ von $E((a_0,...,a_{k-1}))$. Ein Code $\mathcal{C}$ ist $t$-Fehler-korrigierend, wenn $E$ und $D$ für $\mathcal{C}$ existiert, wobei $D$ $t$-Fehler-korrigierend ist.

##### Theorem 5.40

Ein Code $\mathcal{C}$ mit Minimaldistanz $d$ ist genau dann $t$-Fehler-korrigierend, wenn $d \geq 2t+1$.

##### Theorem 5.41

Sei $\mathcal{A} = GF(q)$ und $\alpha_0,...,\alpha_{n-1}$ beliebige verschiedene Elemente aus $\mathcal A$. Betrachtet man die Kodierfunktion $E((a_0,...,a_{k-1})) = (a(\alpha_0),...,a(\alpha_{n-1}))$, wobei $a(x)$ das Polynom $a(x)=a_{k-1}x^{k-1}+...+a_1x+a_0$ ist, so hat dieser Code eine Minimaldistanz von $n-k+1$.

## Logik

### Beweissysteme

##### Definition 6.1

Ein Beweissystem ist ein Quadrupel $\Pi=(\mathcal{S}, \mathcal{P}, \tau, \phi)$. Hier ist $\mathcal{S}$ die Menge der (syntaktischen Repräsentationen) von mathematischen Aussagen, $\mathcal{P}$ die Menge der (syntaktischen Repräsentationen) von Beweisen. $\mathcal S$ und $\mathcal P$ sind Teilmenegen von $\Sigma^*$, wobei $\Sigma$ ein Alphabet von Symbolen ist. $\tau$ ist die Wahrheitsfunktion, die jeder Aussage einen Wahrheitswert zuordnet und $\phi$ die Verifizierungsfunktion, die jedem Paar einer Aussage und einem Beweis einen Wert $0$ oder $1$ zuordnet, wobeii $1$ für die Validität des Beweises steht. Die Funktion $\phi​$ muss effizient berechenbar sein.

##### Definition 6.2

Ein Beweissystem ist korrekt, wenn keine falsche Aussage einen Beweis hat

##### Definition 6.3

Ein Beweissystem ist vollständig, wenn jede wahre Aussage einen Beweis hat.

### Elementare Konzepte der Logik

#### Das Ziel

Das Ziel der Logik ist es, Beweissysteme zu konstruieren, die für eine möglichst große Anzahl Aussagen Beweise und deren Verifikation bieten.

### Syntax, Semantik, Interpretationen und Modelle

##### Definition 6.4

Die Syntax einer Logik definiert ein Alphabet $\Lambda$ und spezifiziert, welche Zeichenketten aus $\Lambda^*$ Formeln (also syntaktisch korrekt) sind.

##### Definition 6.5

Die Semantik einer Logik definiert unter welchen Voraussetzungen eine Formel wahr ist. Insbesondere definiert sie eine Formel, die jeder Formel eine Teilmenge der Indizes der Symbole dieser Formel zuordnet. Jedes Symbol, dessen Index in dieser Formel existiert, wird als freies Symbol in der Formel bezeichnet. Ein Symbol kann in einer Formel als freies und nicht freies Symbol an unterschiedlichen Stellen auftreten.

##### Definition 6.6.

Eine Interpretation besteht aus einer Funktion, die einer bestimmten Menge von Symbolen konkrete Werte zuordnet, wobei jedes Symbol einen bestimmten Wertebereich hat (auch Universum genannt).

##### Definition 6.7

Eine Interpretation ist passend zu einer Formel, wenn sie für alle freien Symbole der Formel einen Wert zuordnet.

##### Definiton 6.8

Die Semantik einer Logik definiert auch eine Funktion, die jeder Formel in Verbindung mit konkreten Werten für freie Symbole einen Wahrheitswert zuordnet.

##### Definition 6.9

Eine passende Interpretation $A$, für die ein Formel $F$ wahr ist, wird Modell für $F$ genannt. Man schreibt auch $A \vDash F$. Für eine Menge von Formeln $M$ wird eine passende Interpretation Modell für $M$ genannt, wenn alle Formeln für diese Interpretation wahr sind. Man schreibt auch $A \vDash M$. Ist $A$ kein Modell für $M$, schreibt man $A \not \vDash M$.

#### Erfüllbarkeit, Tautologien, Konsequenzen und Äquivalenzen

##### Definition 6.10
Eine Formel $F$ (oder eine Menge von Formeln $M$) wird erfüllbar genannt, wenn ein Modell für diese Formel oder die Menge existiert. Andernfalls ist sie unerfüllbar. Für unerfüllbare Formeln wird auch das Symbol $\bot$ (Falsum) genutzt.

##### Definition 6.11
Eine Formel $F$ wird als Tautologie oder gültig/allgemeingültig bezeichnet, wenn sie für alle passenden Interpretationen wahr ist. Man benutzt das Symbol $\top$ (Verum). Man schreibt auch $\vDash F$ (Definiton 6.14).

##### Lemma 6.1
Eine Formel $F$ ist genau dann eine Tautologie, wenn $\neg F$ unerfüllbar ist.

##### Definition 6.12
Eine Formel $G$ ist die logische Konsequenz einer Formel $F$ [einer Menge von Formeln $M$], wenn jede passende Interpretation für $F$ [$M$] und $G$, die ein Modell für $F$ [$M$] ist, auch ein Modell für $G$ ist. Man schreibt $F \vDash G$ [$M \vDash G$].

##### Definiton 6.13
Zwei Formeln $F,G$ heissen äquivalent, wenn jede für $F$ und $G$ passende Interpretation für beide Formeln den gleichen Wahrheitswert ergibt, beide Formeln also logische Konsequenzen von der jeweils anderen sind: 
$$
F \equiv G :\Longleftrightarrow F \vDash G \text{ and } G \vDash F
$$

##### Definiton 6.14
Siehe 6.11

#### Die logischen Operatoren $\land$, $\lor$ and $\neg$
In diesem Abschnitt werden die logischen Operatoren genau wie in Kapitel 2 eingeführt. Daher ist eine Zusammenfassung ausgelassen.

#### Logische Konsequenz vs. Unerfüllbarkeit
##### Lemma 6.3
Die Folgenden drei Aussagen sind äquivalent:
$$
\{F_1, F_2, ..., F_k\} \vDash G\\
(F_1, F_2, ..., F_k) \leftarrow G \text{ ist eine Tautologie}\\
\{F_1, F_2, ..., F_k, \neg G\} \text{ ist unerfüllbar}
$$

### Aussagenlogik

#### Syntax
##### Definiton 6.23
Eine atomare Formel hat die Form $A_i$ mit $i \in \mathbb N$. Eine Formel ist induktiv definiert als:
*  Eine atomare Formel ist eine Formel
*  Wenn $F$ und $G$ Formeln sind, so sind auch $\neg F$, $(F \land G)$ und $(F \lor G)$ Formeln.

#### Semantik
In der Aussagenlogik sind alle atomaren Formeln freie Symbole. Eine Interpretation wir Wahrheitsbelegung genannt.
##### Definition 6.24
Eine Interpretation (Whaheitsbelegung) für eine Menge $M$ atomarer Formeln ist eine Funktion $\alpha: M \longleftarrow \{0,1\}$. Eine Wahrheitsbelegung $\alpha$ ist passend zu einer Formel, wenn sie alle atomaren Formeln in $F$ enthält. Die Semantik ist durch $\mathcal A()A_i=\alpha(A_i)$ für alle atomaren Formeln $A_i$ definiert.

#### Normalformen
##### Definition 6.25
Ein Literal ist eine atomare Formel oder die Negation einer solchen.

##### Definition 6.26
Eine Formel $F$ ist in der _Konjunktiven Normalform_ (CNF), wenn sie eine Konjunktion von Disjunktionen von Literalen ist: $F=(L_{11}, \lor ... \lor L_{1m_1}) \land ... \land (L_{n1} \lor ... \lor L_{nm_n})$ für Literale $L_{ij}$.

##### Definition 6.7
Eine Formel $F$ ist in der _Disjunktiven Normalform_ (DNF), wenn sie eine Disjunktion von Konjunktionen von Literalen ist: $F=(L_{11}, \land ... \land L_{1m_1}) \lor ... \lor (L_{n1} \land ... \land L_{nm_n})$ für Literale $L_{ij}$.

##### Theorem 6.5
Jede Formel ist äquivalent zu einer Formel in CNF und einer anderen Formel in DNF. Als Beweis kann das Verfahren zur "Berechnung" der CNF und DNF angegeben werden.

### Prädikatenlogik
#### Syntax
##### Definition 6.31
* Variablensymbole haben die Form $x_i$ mit $i\in\mathbb N$. Wir verwenden $x,y,z,u,v,w$.
* Funktionssymbole haben die Form $f_i^{(k)}$ mit $i,k\in\mathbb N$. $k$ bezeichnet die Anzahl der Argumente der Funktion. Ist $k=0$, so spricht man von einer Konstante. Wir verwenden $f,g,h$.
* Prädikatensymbole haben die Form $P_i^{(k)}$ mit $i,k\in\mathbb N$. $k$ bezeichnet die Anzahl der Argumente des Prädikates. Wir verwenden $P,Q,R$.
* Ein Term ist induktiv definiert: Jede Variable ist ein Term, zusätzlich ist $f_i^{(k)}(t_1,...,t_k)$ ein Term, wenn $t_1,...,t_k$ Terme sind. Ist $k=0$ werden keine Klammern geschrieben.
* Eine Formelist auch induktiv definiert:
	- Für beliebige $i,k\in\mathbb N$ ist $P_i^{(k)}(t_1,...,t_k)$ eine Formel, sofern $t_1,...,t_k$ Terme sind. Diese Formeln werden auch atomare Formeln genannt.
	- Wenn $F$ und $G$ Formeln sind, so sind auch $\neg F$, $F\land G$ und $F \lor G$ Formeln
	- Wenn $F$ eine Formel ist, dann sind für beliebige $i \in \mathbb N$: $\forall x_i  F$ und $\exists x_i  F$ Formeln.

#### Freie Variablen und Variablenersetzung
##### Definition 6.32
Variablen sind in Formeln entweder frei oder gebunden. Gebunden sind Variablen $x_i$, wenn sie in (Teil-)Formeln der Form $\forall x_i F$ oder $\exists x_i F$ vorkommen. Man spricht von einer geschlossenen Formel, wenn sie keine freien Variablen enthält.
##### Definition 6.33
Für eine Formel $F$, eine Variable $x$ und einen Term $t$ beschreibt $F[x/t]$ die Formel, die durch ersetzen jeder freien Variable $x$ in $F$ entsteht.

#### Semantik
##### Definition 6.34
Eine Interpretation oder auch Struktur ist ein 4-Tupel $\mathcal A=(U,\phi,\psi,\xi)$, wobei:
* $U$ eine nicht-leere Menge, das sog. Universum ist
* $\phi$ eine Funktion ist, die jedem Funktionssymbol eine $k$-äre Funktion $U^k \longrightarrow U$ zuweist.
* $\psi$ eine Funktion ist, die jedem Prädikatensymbol eine $k$-äre Funktion $U^k \longrightarrow \{0,1\}$ zuweist.
* $\xi$ eine Funktion ist, die jeder Variable einen Wert in $U$ zuweist.

##### Definition 6.35
Eine Struktur $\mathcal A$ ist passend zu einer Formel $F$, wenn alle Funktionssymbole, Prädikatensymbole und freien Variablen defineirt werden.

##### Definition 6.36
Für eine Struktur $\mathcal A=(U,\phi,\psi,\xi)$ definieren wir den Wert von Termen und den Wahrheitswert von Formeln unter dieser Struktur wie folgt:
Der Wert $\mathcal A(t)$ ist rekursiv definiert:
- Wenn $t$ eine Variable ist, gilt $\mathcal A(t)=\xi(t)$
- Wenn $t$ ein Symbol der Form $f(t_1,...,t_k)$ für Terme $(t_1,...,t_k)$ und eine $k$-äre Funktion $f$ ist, gilt $\mathcal A(t)=\phi(f)(\mathcal A(t_1),...,\mathcal A(t_k))$
Der Wahrheitswert einer Formel $F$ ist rekursiv definiert als:
- $\mathcal A((F \land G)) = 1$ genau dann, wenn $\mathcal A(F) = 1$ and $\mathcal A(G)=1$
- $\mathcal A((F \lor G)) = 1 $ genau dann, wenn $\mathcal A(F) = 1$ or $\mathcal A(G)=1$
- $\mathcal A(\neg F) = 1 $ genau dann, wenn $\mathcal A(F) = 0$
- Wenn $F$ die Form $F=P(t_1,...,t_k)$ für Terme $(t_1,...,t_k)$ und ein $k$-äres Prädikat $P$, gilt $\mathcal A(F)=\psi(P)(\mathcal A(t_1),...,\mathcal A(t_k))$
- Wenn $F$ die Form $\forall x F$ oder $\forall x F$, dann ... siehe Skript...

#### Gleicheheit in der Prädikatenlogik
Da die Gleichheit in der bisher definierten Syntax nicht vorkommt, muss diese ergänzt werden: Deshalb definieren wir für zwei Terme $t_, t_2$ folgendes: $(t_1 = t_2)$ ist eine Formel. Ebenfalls muss jetzt noch die Semantik erweitert werden durch: $\mathcal A((t_1 = t_2)) = 1 \Leftrightarrow \mathcal A(t_1) = \mathcal A(t_2)$. Hierbei ist zu beachten, dass die beiden Gleichheitszeichen unterschiedliche sind. Während links des Doppelpfeils das neue Zeichen unserer Prädikatenlogik steht, ist rechts das allgemein verwendete Zeichen.

#### Basic Equivalences involving Quantifiers
In diesem Abschnitt werden in Lemma 6.8 10 Äquivalenzen aufgezeigt.
##### Lemma 6.9
Ersetzt man eine Teilformel $G$ einer Formel $F$ durch eine Formel $H$, wobei $G$ und $H$ äquivalent sind, so ist die resultierende Formel äquivalent zu $F$.

#### Ersetzung gebundener Variablen
##### Lemma 6.10
Für eine Formel $G$, in der $y$ nicht vorkommt, gilt:
$$
\forall x G \equiv \forall y G[x/y]
$$
und
$$
\exists x G \equiv \exists y G[x/y]
$$

##### Definition 6.37
Eine Formel in der keine Variable als gebunden und freie Variable vorkommt und alle gebundenene Variablen unterschiedlich sind, wird als bereinigt bezeichnet.

#### Universelle Instanziierung
##### Lemma 6.11 
Für eine beliebige Formel $F$ und einen beliebigen Term $t$ gilt:
$$
\forall x F \vDash F[x/t]
$$

#### Normalformen
##### Definition 6.38
Eine Formel der Form 
$$
Q_1x_1 Q_2x_2 \dots Q_nx_n G
$$
wobei $Q_i$ Quantoren ($\forall$ oder $\exists$) sind und $G$ eine Formel ohne Quantoren ist, ist in der Prenex-Form.
##### Theorem 6.12
Für jede Formel gibt es eine äquivalente Formel in Prenex-Form. Für die Umstellung können die bekannten Äquivalenzen verwendet werden. Es kann vorteilhaft sein, die Formeln als Baum darzustellen.

#### Ein Theorem und Interpretationen
Das folgende Theorem kann auf unterschiedliche Weisen interpretiert und daraus interessante Aussagen (folgende Korollare) getroffen werden:
##### Theorem 6.13
$$
\neg \exists x \forall y (P(y,x) \leftrightarrow \neg P(y,y))
$$
##### Korollar 6.14
Es gibt keine Menge, die aus allen Mengen besteht, die sich nicht selbst einthalten.
###### Dazugehörige Interpretation
$$
U^{\mathcal A} = \text{ alle Mengen}
P^{\mathcal A}(x,y) = 1 :\Leftrightarrow x \in y
$$
##### Korollar 6.15
Die Menge $\{0,1\}^\infty$ ist überabzählbar.
###### Dazugehörige Interpretation
$$
U^{\mathcal A} = \mathbb N
P^{\mathcal A}(x,y) = 1 :\Leftrightarrow \text{ das $y$-te Bit der $x$-ten Folge ist 1}
$$
Diese Interpretation entspricht dem Kantorschen Diagonalisiserungsargument.
##### Korollar 6.16
Es gibt unberechenbare Funktionen $\mathbb N \rightarrow \{0,1\}$
###### Dazugehörige Interpretation
$$
U^{\mathcal A} = \mathbb N \text{ , wobei jede natürliche Zahl einer Funktion entspricht}
P^{\mathcal A}(x,y) = 1 :\Leftrightarrow \text{ das Outputbit für das Programm $x$ mit Eingabe $y$ ist 1}
$$

### Logische Kalküle
Eine wohldefinierte Menge von Regeln zur Bearbeitung von Formeln wird Kalkül genannt. Diese werden eingesetzt, um Beweise durchzuführen. Es gibt sehr unterschiedliche Arten von Kalkülen, wir werden aber im Folgenden eine sehr "natürliche" Form von Kalkülen betrachten, die sogenannten Hilbert-Style-Kalküle.
#### Hilbert-Style Kalküle
##### Definition 6.17
Eine Schlussregel ist eine Regel um eine Formel aus einer Menge von Formeln (Preconditions) zu schließen. Man schreibt $\{F_1,...,F_k\} \vdash_R G$, wenn $G$ durch Anwendung der Regel $R$ aus der Menge der Formeln $\{F_1,...,F_k\}$ geschlossen werden kann. Häufig schreibt man auch $\frac{F_1\:F_2\:...\:F_k}{G} \; (R)$.
##### Definition 6.18 (Informell)
Eine Schlussregel $R$ auf eine Formelmenge $M$ anzuwenden bedeutet:
1. Eine Teilmenge $M'$ aus $M$ auszuwählen
2. Für die Platzhalter in $R$ die Formeln oder Teilformeln aus $M'$ auszuwählen, sodass $M' \vdash_R G$ für eine Formel $G$ gilt
3. $G$ zur Menge $M$ hinzuzufügen
##### Definition 6.19
Ein logisches Kalkül $K$ ist eine endliche Menge von Schlussregeln: $K=\{R_1,...,R_k\}$
##### Definition 6.20
Eine Herleitung einer Formel $G$ aus einer Formelmenge $M$ in einem Kalkül $K$ ist eine Sequenz der Länge $n$ von Anwendungen der Regeln in $K$, die zu $G$ führt. Genauer gesagt: $M_0=M, M_i:=M_{i-1} \cup \{G_i\}$ für $1\leq i \leq n$, wobei $N \vdash_{R_j}G_i$ für ein $N\subseteq M_{i-1}$ und ein $R_j \in K$, wobei $G_n=G$.
Man schreibt $M\vdash_KG$, wenn eine Herleitung von $G$ aus $M$ in $K$ existiert.
#### Korrektheit und Vollständigkeit
##### Definition 6.21
Eine Schlussregel $R$ ist korrekt, wenn für jede Menge von Formeln $M$ und jede Formel $F$ gilt, dass $M\vdash_RF$ impliziert $M\vDashF$.
##### Definition 6.22
Ein Kalkül $K$ wird als korrekt bezeichnet, wenn jede Formel $F$ die mithilfe der Reglen des Kalküls aus einer beliebigen Formelmenge $M$ hergeleitet werden kann auch logische Konsequenz dieser Formelmenge ist.
Ein Kalkül $K$ wird als Vollständig bezeichnet, wenn jede Formel $F$, die logische Konsequenz einer Formelmenge $M$ ist, mithilfe des Kalküls aus $M$ hergeleitet werden kann.
#### Herleitungen aus Annahmen
##### Lemma 6.4
Wenn $F\vdash_KG$ für ein korrektes Kalkül gilt, dann ist $F\rightarrow G$ eine Tautologie. Allgemeiner gilt: Wenn $\{F_1,...,F_K\} \vdash G$ gilt, dann gilt $\vDash ((F_1 \land ... \land F_k) \rightarrow G)$.
#### Das Resulotionskalkül der Aussagenlogik
Das Ziel des Resolutionskalküls ist es, zu zeigen, dass eine gegebne Formelmenge unerfüllbar ist, da so bewiesen werden kann, dass die Negation der Konjunktion aller Formeln eine Tautologie ist (Lemma 6.3).
##### Voraussetzungen
###### Definition 6.28 und 6.29
Voraussetzung für die Anwendung des Resolutionskalküls ist, dass eine Formel in der konjunktiven Normalform vorliegt. Aus dieser können aus den einzelnen Disjunktionen die Literale als Elemente einzelner Klasuseln extrahiert werden. Alle Klauseln einer konjunktiven Normalform bilden dann die Klauselmenge dieser Formel. Die Vereinigung der Klauselmengen einer Formelmenge bildet die Klauselmenge dieser Menge von Formeln.
##### Durchführung
###### Definition 6.30
Eine Klauselmenge kann verändert werden, indem zwei Klauseln $K_1,K_2$ zusammengezogen werden, sofern sich ein Literal $L\in K_1$ in einer Klausel und seine Negation $\neg L \in K_2$ in der anderen Klausel befindet. Die entstehende Klausel $K$ wird als _resolvent_ von $K_1$ und $K_2$ bezeichnet. $K=(K_1\setminus\{L\})\cup(K_2\setminus\{\neg L})$

Sei $\mathcal K$ eine gegebene Klauselmenge, so besteht ein Resolutionsschritt daraus, den _resolvent_ $K$ aus zwei Klauseln $K_1,K_2 \in \mathcal K$ zu berechnen und $K$ zu $\mathcal K$ hinzuzufügen. Diese Regel lässt sich auch schreiben als $\{K_1, K_2\} \vdash_{res} K$ und ist die einzige Regel des Resolutionskalküls $Res = \{res\}$.

###### Lemma 6.6
Das Resolutionskalkül ist korrekt.

Das Ziel des Resolutionskalküls ist es, eine leere Klausel $\emptyset$ zu erreichen. Denn:

###### Theorem 6.7
Eine Formelmenge $M$ ist genau dann unerfülbar, wenn $\mathcal K(M) \vdash_{Res} \emptyset$.