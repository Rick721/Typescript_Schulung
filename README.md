# Typescript Schulung

# 1. Was ist Typescript und wieso sollten wir es nutzen? 

## 1.1 Was ist Typescript? 
* Typescript ist eine Open Source Programmiersprache für die Webentwicklung von Microsoft 
* Typescript ist typsicher, objektorientiert und wird compiliert 
* Datentypen sind vorhanden, aber optional  
* Es wurde von Anders Hejlsberg entwickelt 

## 1.2 Warum Typescript? 
* Typsicherheit bietet im Vergleich zu Javascript mehr Sicherheit beim Programmieren und vermeidet Fehler 
* Durch die Compilierung wird die Fehlersuche vereinfacht 
* Typscript unterstützt objektorientierte Konzepte wie `Klassen, Interfaces  und <b>Vererbung` 

# 2. Aufsetzen der Entwicklungsumgebung 

## 2.1 Installieren von Node, NPM und Typescript 
* installieren Sie Node.js [hier](https://nodejs.org/en/)
* öffnen Sie ihre Windows-Konsole und überprüfen Sie die erfolgreiche Installation über den folgenden Befehl: `node -v`  
* installieren Sie Typscript über den Befehl: `npm install -g typescript`
* falls noch nicht vorhanden, installieren Sie sich eine Entwicklungsumgebung ([VSCode](https://code.visualstudio.com/download), [Notepad++](https://notepad-plus-plus.org/downloads/), etc.). Die Wahl liegt hierbei bei ihnen 

## 2.2 Ihr erstes Programm 
* erstellen Sie einen neuen Ordner mit dem Namen "Typescript Schulung"
* erstellen Sie in dem Ordner "Typescript Schulung" eine .ts Datei mit dem Namen "ErstesProgramm"
* geben Sie nun in der Konsole den Befehl tsc --build ein
* Syntax & Beispiel Code:
```typescript
// by default typescript consider all files in a folder as a module, so variables defined in one file will be checked on the fly and throws an error: Cannot redeclare block-scoped variable - to solve issue use export {}

export {};

// write valid javascript, basic javascript/typescript
console.log('Welcome to typescript');
// ------------------------------

//type annotation to eliminate any data variable type error
let name:string = 'Dinanath';
//name=123; // error
console.log('My Name is: ' + name);
```

# 3.0 Typescript features und Konzepte

## 3.1 Typescript - Die Syntax

Die Syntax einer Programmiersprachen, sind nichts anderes als eine Reihe an Regeln, welche man beim schreiben von Code beachten muss. In Typescript bestehen diese Regeln aus: 

* Variablen
* Funktionen
* Kommentaren
* Modulen 
* Anweisungen 

Diese werden wir uns nun im Detail genauer ansehen

## 3.2 Variablen

### 3.2.1 Die Grundlagen 

* Variablen sind ein Speicher oder Platzhalter für Daten wie Zahlen, Zeichenketten und vieles mehr
* Einen Übersicht aller vorhandenen Datentypen in Typescript können Sie [hier](https://ichi.pro/de/datentypen-in-typescript-188494705320680) erhalten 
* Variablen können Sie wie folgt deklarieren: 
```typescript
export {};

var name: string = 'Dinanath';
var age: number = 35;
var isDeveloper: boolean = true;
console.log('My details are : ' + name + ' ' + age + ' ' + isDeveloper);

var name = 'Dino';
console.log('My name is : ' + name); 
```

### 3.2.2 Var vs Let

* Beim deklarieren von Datentypen können wir var oder let verwenden
* Variablen welche mit let deklariert wurden, haben einen Gültigkeitsbereich, welcher auf den Block, den Befehl oder den Ausdruck in dem sie deklariert wurden, beschränkt ist
* Variablen welche mit var deklariert wurden, haben einen Gültigkeitsbereich, welcher auf die Funktion, in welcher sie deklariert wurde, beschränkt ist. 
* das folgende Beispiel veranschaulicht den Unterschied: 
* //TODO: Code Beispiel einfügen 

### 3.2.3 const Variablen Deklaration 

* const ist eine Abkürzung und steht für constant 
* Eine Variable vom Typ constant muss bereits bei der deklaration/initialisierung einen Wert erhalten
* Eine Variable vom Typ constant kann nach der deklaration/initialisierung nicht mehr verändert werden
* der Gültigkeitsbereich einer Variable vom Typ const, ist auf den Block-Scope beschränkt
* TODO: Code beispiel einfügen 






