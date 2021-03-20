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


## 3.3 Datentyp `Any`
* Typescript besitzt einen neuen Datentyp namens `any` 
* Eine Variable vom Typ `any` kann jeden einen Wert von jedem Datentyp beinhalten 

> **Syntax & Beispiel**: `Typescript`
```typescript
let data1:string = 'Data1'

//error - string type can not accept number or other data
// data1 = 50; 

// any data type variable can store any type of value, there are no data checking 
let data2:any = 'Data2';
data2 = 50;
data2 = true;
data2 = ['Hi','Hey','Good','Hello'];

console.log(data2);
```

## 3.4 Datentyp `Array`
* Arrays in Typescript funktionieren wie Arrays in Javascript 
* Es gibt zwei Möglichkeiten, Arrays zu deklarieren: 
  1. let meinArray: string[];
      - let arrayStädte: string [] = ['Hamburg','Berlin','München','Stuttgart'];
  2. let meinArray: Array&lt;string&gt;
      - let arraySprachen: Array&lt;string&gt; = ['C','C++','Java','Ruby','Phthon'];
      - In dem obrigen Beispiel haben wir einen Array vom Typ String erstellt (Typescript stellt nun sicher, dass der Array auch tatsächlich nur Strings beinhaltet)

> **Syntax & Beispiel**: `Typescript`
```typescript

export {};

let arrayStädte: string [] = ['Hamburg','Berlin','München','Stuttgart'];
console.log('arrayStädte:',arrayStädte);


let arraySprachen: Array<string> = ['C','C++','Java','Ruby','Phthon'];
console.log('arraySprachen',arraySprachen);
```

## 3.5 Tuples
* Typescript bietet eine neue Art von Array namens Tuples 
* Tuples ermöglichen das speichern von mehreren Datentypen in einem Array
* Wir deklarieren einen Tuple wie folgt: let personDetail: [string, number] = ['Dinanath', 35];

> **Syntax & Beispiel**: `Typescript`
```typescript
export {};

let arrayFrameworkDetails:  [string,number] = ['JavaScript',7.0];
console.log('arrayFrameworkDetails:',arrayFrameworkDetails);

console.log('arrayFrameworkDetails Name:',arrFrameworksDetails[0]);
console.log('arrayFrameworkDetails Version:',arrFrameworksDetails[1]);
```

## 3.6 Enums
* Enums sind eine Sammlung von Konstanten
* Sie dienen der Lesbarkeit und der logischen Struktur unseres Codes
* Sie bieten uns die Möglichkeit, vordefinierte Konstanten für unsere Variablen festzulegen
* Es gibt 3 Arten von Enums: 
  1. Numerischer enum (beinhaltet Zahlenwerte)
  2. String enum (beinhaltet String Werte)
  3. Heterogenes enum (beinhaltet String- und Zahlenwerte) 
 
> **Syntax & Beispiel**: `Typescript`
```typescript
export {};

enum RGBFarben { Rot, Grün, Blau };
console.log('RGBFarben:', RGBFarben);
console.log('RGBFarben.Grün:', RGBFarben.Grün);

let farbeBlau: RGBFarben = RGBFarben.Blau;
console.log('farbeBlau:', farbeBlau);

enum Städte1 { Hamburg = 10, München = 20, Berlin = 30, Köln = 40, Stuttgart = 50 }
console.log('Städte:', Städte1);
console.log('Bangalore:',Städte1.München);

enum Städte2 { Hamburg = 'M', München = 'D', Berlin = 'K', Köln = 'C', Stuttgart = 'B' }
console.log('Städte:', Städte2);
console.log('Bangalore:',Städte2.München);
```

## 3.7 Funktionen
* Funktionen sind einer der wichtigsten Grundlagen in fast jeder Programmiersprache 
* Eine Funktion ist eine Sammlung von Anweisungen, welche eine bestimmte Aufgabe erfüllen
* Funktionen machen den Code lesbarer, verwaltbarer und wiederverwendbarer
* Mithilfe von Typescript können wir die Typen von unseren Übergabeparametern festlegen, sowie von unseren Rückgabewerten
* Typescript ermöglicht es optionale Parameter zu erstellen, indem wir ein `?` nach unserem Parameternamen angeben

> **Syntax & Beispiel**: `Typescript`
```typescript
export {};

// die Parameter erhalten einen festgelegten Datentyp, in diesem Fall number
function sum(num1: number, num2: number) {
  console.log(num1 + num2);
}

sum(10, 20);

//der untere Funktionsaufruf würde einen Fehler werfen, da wir nur Werte vom Typ number übergeben dürfen
// sum('one','two');

// nicht nur der Parameter nachricht, sondern auch der Rückgabewert der Funktion erhält einen festgelegten Datentyp
function zeigeNachricht(nachricht: string): string {
  return nachricht;
}
let nachricht1 = zeigeNachricht('Willkommen zu Typescript');
console.log(nachricht1);
```

> **Syntax & Beispiel**: `Typescript`
```typescript
export { };

// der Parameter num2 erhält ein Fragezeichen, damit ist er optional und muss nicht mehr zwingend beim Funktionsaufruf übergeben werden
function sum(num1: number, num2?: number) {
  if (num2) {
    console.log(num1 + num2);
  } else {
    console.log(num1);
  }
}

sum(10, 20);
sum(100);
```

## 3.8 Klassen
* Anders wie Javascript, ist Typescript eine objektorientierte Programmiersprache
* Im objektorientierten programmieren, nutzen wir Klassen als einen Bauplan für ein Objekt
* Eine Klasse kann Attribute (Eigenschaften) und Methoden (Verhaltensweisen) besitzen
* Eine Klasse kann Attribute und Methoden von einer anderen Klasse "erben" dafür nutzen wir das Schlüsselwort `extends`
* Typescript implementierte Klassen, um die Vorteile objektorientierte Techniken (Interfaces, Vererbung, Abstraktion) zur verfügung zu stellen 

> **Syntax & Beispiel**: `Typescript`
```typescript
export {};

class Begrüßung {
  personenName: string;

  constructor(name: string) {
    this.personenName = name;
  }

  begrüßePerson() {
    console.log(`Willkommen, hab einen schönen Tag ${this.personenName}!`)
  }

}

let person1 = new Begrüßung('Max');
console.log('person1.personenName:',person1.personenName);
person1.begrüßePerson();
```

> **Syntax & Beispiel**: `Typescript - Klassenvererbung`
```typescript
// Klasse Person erbt von Klasse Begrüßung
class Person extends Begrüßung {

  constructor (pName: string) {
    super(pName);
  }

  schlafen() {
    console.log('*Person schläft*');
  }

}

let person1 = new Person('Tom');
console.log('person1.name:',person1.name);
person1.begrüßePerson();
person1.schlafen();
```

## 3.9 Interfaces
* Ein Interface ist eine Art Klasse, die nur aus Konstanten und abstrakten Methoden besteht
* In einem Interface können wir Konstanten und Funktionen in Form von abstrakten Methoden definieren
* Die Konstanten und Methoden sind hierbei die Properties des Interfaces
* Um ein Interface zu deklarieren, benutzen wir das Schlüsselwort `interface`
* Interfaces bieten die Möglichkeit, optionale Properties zu erstellen, dazu hängen wir an das Ende unseres Propertienamens ein `?`

> **Syntax & Beispiel**: `Typescript`
```typescript
export {};

interface Kontakt {
  vorname: string;
  nachname: string;
  alter?: number
}

function zeigeKontaktdetails (kontakt: Kontakt) {
  console.log(`Kontaktdetails: ${kontakt.vorname} ${kontakt.nachname} ${kontakt.alter}`); 
}

let kontakt1 = { 
  vorname: 'Max',
  nachname: 'Mustermann',
}

zeigeKontaktdetails(kontakt1);

let kontakt2 = { 
  vorname: 'Max',
  nachname: 'M.',
  alter: 40
}

zeigeKontaktdetails(kontakt2);
```

## 3.10 Zugriffsmodifizierer






