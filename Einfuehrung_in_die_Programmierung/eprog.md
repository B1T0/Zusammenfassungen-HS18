---
bibliography:
- 'bib/mybib.bib'
---

\@p@

\

 Zusammenfassung \

ETH Zürich\
Bachelorstudiengang Informatik\
Erstes Semester

Organisatorisches
=================

Team
----

Professor

:   Thomas R. Gross

Hauptassistent

:   Felix Wolf

Meine Übungsgruppe

:   Marco Zeller (mzeller\@ethz.ch), Yannick Rosskopf
    (yannicro\@ethz.ch) -\> Mittwochs, HG G 26.5

Webseite
--------

<http://www.lst.inf.ethz.ch/education/einfuehrung-in-die-programmierung-i--252-0027-.html>

-   Unbeschriebene Folien (häufig vor der Vorlesung online, keine
    Garantie)

-   Beschriebene Folien (24-48h nach der Vorlesung)

-   Videoaufzeichnung

-   Übungsblätter

-   Aktuelle Nachrichten

Übungen
-------

-   Aufgabenblätter

-   Besprechung in Übungsgruppen

-   Diskussion mit anderen

-   Pausen zwischen Besprechung und Bearbeitung für echtes Lernen

-   Bonuspunkte ab 4. oder 5. Übung

-   Slides auf <https://n.ethz.ch/~yannicro/download>

-   Abgabe der Übungen und Veröffentlichung der Musterlösung via Git

-   Feedback via Mail

Sonstiges
---------

-   Java

-   Eclipse

-   als Nutzung (Nicht prüfungsrelevantes Buch:
    <https://git-scm.com/book/en/v2>)

-   <https://vis.ethz.ch>

Beschreibung von Programmiersprachen - EBNF
===========================================

Allgemeines zur Extended Backus Normal Form
-------------------------------------------

-   Beschreibt die Syntax einer Sprache

-   Programmieren im ganz kleinen

-   Vier Elemente ("control forms")

    -   Aufreihung ('sequence')

    -   Entscheidung ('decision') - Auswahl oder Option

    -   Wiederholung ('repitition')

    -   Rekursion ('recursion')

Regeln und Beschreibungen
-------------------------

-   EBNF Beschreibung: eine Menge EBNF Regeln

-   EBNF Regel: drei Bestandteile

    1.  Linke Seite (LHS): Ein Wort - der Name der Regel, kursiv oder in
        spitzen Klammern

    2.  $\Leftarrow$: Trennt LHS von RHS, gesprochen 'ist definiert als'

    3.  Rechte Seite (RHS): Beschreibung für den Namen - besteht aus
        Namen, Buchstaben (characters) und Kombinationen der control
        forms

Control forms
-------------

### Aufreihung

-   von links nach rechts gelesen

-   Reihenfolge ist wichtig

*raum2* $\Leftarrow$ E 1 2\
*buchstabe\_d* $\Leftarrow$ D\
*buchstabe\_2* $\Leftarrow$ 2\
*buchstabe\_8* $\Leftarrow$ 8\
*raum1* $\Leftarrow$ *buchstabe\_d* *buchstabe\_2* *buchstabe\_8*

### Auswahl

-   Menge von Alternativen

-   mit $\mid$ (gesprochen senkrechter Strich) ("stroke") getrennt

-   Alternativen folgen den EBNF-Regeln

*raum* $\Leftarrow$ *raum1* $\mid$ *raum2*\
*digit* $\Leftarrow$
1$\mid$2$\mid$3$\mid$4$\mid$5$\mid$6$\mid$7$\mid$8$\mid$9$\mid$0

### Option

-   Element in eckigen Klammern

-   Kann gewählt werden, muss aber nicht

*initials* $\Leftarrow$ T\[R\]G\
*vorzeichen* $\Leftarrow$ \[+$\mid$-\]

### Wiederholung

-   Der zu wiederholende Ausdruck steht zwischen geschweiften Klammern

-   kann beliebig oft wiederholt werden (auch 0 mal, also gar nicht)

*integer* $\Leftarrow$ \[+$\mid$-\] *digit* {*digit*}

### Rekursion

-   Nötig für bestimmte komplexe Symbole, da Wiederholungen nicht für
    alles ausreichend sind. Jede Wiederholung kann allerdings durch
    Rekursion dargestellt werden.

-   "Selbstaufruf"

-   Kann direkt (eine Zeile) oder indirekt (mit mehreren Namen)
    beschrieben werden.

*balance* $\Leftarrow$ A \| *balance* \| B\
Diese Beschreibung sorgt für ein gleichmäßiges Auftreten von As und Bs
(immer gleich viele As wie Bs)

Interpretation von EBNF Beschreibungen
--------------------------------------

Die Legalität eines Symbols ist immer nur für eine EBNF-Beschreibung.
Ein Symbol ist hier eine Folge von Buchstaben (character). Ein Symbol
ist dann legal gemäss einer Regel, wenn alle Buchstaben des Symbols mit
den Elementen der Regel übereinstimmen.

Umgangssprachlich lässt sich Legalität informell beweisen. Kompakter und
formaler geht es mit Tabellen und Ableitungsbäumen.

### Tabellen

-   Jede Zeile wird aus der Vorgängerzeile durch eine der folgenden
    Regeln abgeleitet:

    1.  Ersetze einen Namen (LHS) durch die entsprechende Definition
        (RHS)

    2.  Wahl einer Alternative

    3.  Entscheidung ob ein optionales Element dabei ist oder nicht

    4.  Bestimmung der Zahl der Wiederholungen

-   Manchmal werden 1 und 2 in einem Schritt gemacht

  Status                       Reason (rule \#)
  ---------------------------- ------------------------------------------------------
  *integer*                    Given
  \[+$\mid$-\]*digit*{digit}   Replace *integer* by its RHS (1)
  \[+\]*digit*{digit}          Choose + alternative (2)
  +*digit*{*digit*}            Include option (3)
  +1{*digit*}                  Replace the first *digit* by 1 alternative (1 and 2)
  +1*digit* *digit*            Use two repititions (4)
  +14*digit*                   Replace the first *digit* by 4 alternative (1 and 2)
  +142                         Replace the first *digit* by 2 alternative (1 and 2)

EBNF-Regeln lassen sich auch als Graphen darstellen. Hierfür werden alle
Entscheidungen durch unterschiedliche Wege aufgezeichnet. Dies ist
häufig übersichtlicher als Tabellen.

Zwei EBNF Beschreibungen werden als *Äquivalent* oder auch gleichwertig
bezeichnet, wenn sie dieselben legalen und illegalen Symbole erkennen.

Syntax und Semantik
-------------------

Mit EBNF wird nur die Syntax beschrieben, also nur die Form. Dies lässt
keine Aussagen über den Inhalt zu.

EBNF für Mengen
---------------

Mengen werden als kommagetrennte Aufzählung von Zahlen zwischen zwei
geschweiften Klammern notiert.

*integer\_list* $\Leftarrow$ *integer* { , *integer* }\
*integer\_set* $\Leftarrow$ {*integer\_list*}\

Ist also eine valide Beschreibung hierfür.

Programmiereinführung
=====================

Absolute Basics (hier nicht weiter ausgeführt)
----------------------------------------------

-   Nutzen von Compiler, IDE

-   Grundgerüst von Java-Programmen

-   Bezeichner (reserviert Symbole)

-   Kommentare

-   Strings (inkl. Sonderzeichen)

-   Methoden

Typen und Variablen
-------------------

### Typen

-   Beschreiben Eigenschaften von Daten

-   In Java Angabe nötig, in anderen Sprachen manchmal nicht

-   Interne Darstellung in Binärcode

-   Sorgen für richtige Interpretation

-   Verwendbare Typen:

    -   Eingebaute Typen ("primitive types"): int, double, char, boolean

-   Sollen Fehler verhindern (Kombination verschiedener Typen)

Ausdrücke
---------

> Ein Wert oder Operanden und Operator(en) die einen Wert berechnen.

### Arithmetische Operatoren

-   Addition: $+$

-   Subtraktion: $-$

-   Multiplikation: $*$

-   Division: $/$

-   Modulus: $\%$

Bei allen Operatoren sind immer die Typen der Operanden wichtig. So
ergibt eine Division zweier ganzer Zahlen in Java immer eine neue ganze
Zahl und funktioniert daher anders als erwartet. ($43 / 3 = 14$)

### Assoziativität, Rangordnung

Bei einer Kombination mehrerer Operatoren in einem Ausdruck muss die
Reihenfolge der Ausführung festgelegt werden. Dies geschieht durch die
Assoziativität (Reihenfolge bei mehreren gleichen Operatoren) und die
Rangordnung (Reihenfolge bei unterschiedlichen Operatoren).
