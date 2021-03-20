# Typescript für Anfänger


# 1. Was ist Typescript und was bietet es für Vorteile? 


## 1.1 Was ist Typescript? 

* Typescript ist eine Open Source Programmiersprache für die Webentwicklung 
* Es ist typsicher, objektorientiert und wird compiliert 
* Entwickelt wurde es von Anders Hejlsberg, am 1. Oktober 2012 wurde es von Microsoft veröffentlicht

## 1.2 Typescript vs Javascript 

* TypeScript erweitert JavaScript um Typings und bietet damit im Vergleich zu Javascript Typsicherheit
* Typscript unterstützt objektorientierte Konzepte wie `Klassen`, `Interfaces`  und `Vererbung` 
* Javascript wird interpretiert, Typescript compiliert (in Javascript Code)

## 1.3 Warum also Typescript? 

* Typescript bietet im Vergleich zu Javascript mehr Sicherheit beim Programmieren und vermeidet Fehler
* Durch die Compilierung wird die Fehlersuche vereinfacht  
* Mithilfe von objektorientierten Konzepten, könne Entwickler saubereren, schnellern und übersichtlicheren Code schreiben



# 2. Aufsetzen der Entwicklungsumgebung 


## 2.1 Installieren von Node, NPM und Typescript 

* installieren Sie Node.js [hier](https://nodejs.org/en/)
* öffnen Sie ihre Konsole (CMD oder Powershell) und überprüfen Sie die erfolgreiche Installation über den folgenden Befehl: `node -v`  
* installieren Sie Typscript über den Befehl: `npm install -g typescript`
* falls noch nicht vorhanden, installieren Sie sich eine Entwicklungsumgebung ([VSCode](https://code.visualstudio.com/download), [Notepad++](https://notepad-plus-plus.org/downloads/), etc.). Die Wahl liegt hierbei bei ihnen 

## 2.2 Ihr erstes Programm 

* erstellen Sie einen neuen Ordner mit dem Namen "TSSchulung"
* erstellen Sie in dem Ordner "TSSchulung" eine .ts Datei mit dem Namen "ErstesProgramm"
* öffnen Sie nun in dem Verzechnis, in welchem sich ihre .ts Datei befindet, ein Konsolenfenster
* geben Sie nun in der Konsole den Befehl `tsc --init` und danach `tsc --build` ein
* kopieren Sie den unteren Code und fügen Sie ihn in ihre .ts Datei ein

 Syntax & Beispiel Code:
```typescript

console.log('Hello World');

```
* Nachdem sie den Code in ihrer Datei eingefügt haben, geben Sie den Befehl `tsc --build; node .\ErstesProgramm.js ` in ihre Konsole ein, um das Ergebniss in der Konsole ausgeben zu lassen


# 3.0 Typescript features und Konzepte


## 3.1 Typescript - Die Syntax

Die Syntax einer Programmiersprache, ist nichts anderes als eine Reihe an Regeln, welche man beim schreiben von Code beachten muss. In Typescript bestehen diese Regeln aus: 

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
* Variablen können wie folgt deklariert werden: 
```typescript

var vorname: string = 'Max';
var alter: number = 35;
var istEntwickler: boolean = true;
console.log('Meine Daten sind : ' + name + ' ' + alter + ' ' + istEntwickler);

var vorname = 'Tom';
console.log('Mein Name ist : ' + name); 
```

### 3.2.2 Var vs Let

* Beim deklarieren von Datentypen können wir var oder let verwenden
* Variablen welche mit let deklariert wurden, haben einen Gültigkeitsbereich, welcher auf den Block, den Befehl oder den Ausdruck in dem sie deklariert wurden, beschränkt ist
* Variablen welche mit var deklariert wurden, haben einen Gültigkeitsbereich, welcher auf die Funktion, in welcher sie deklariert wurde, beschränkt ist. 
* das folgende Beispiel veranschaulicht den Unterschied: 

```typescript

function namensAusgabe() {
  var vorname1 = "Max";
  let vorname2 = "Tom";

  console.log(vorname1, vorname2); // Ausgabe: Max Tom

  {
    var nachname1 = "Mustermann"
    let nachname2 = "Müller";
    console.log(nachname1, nachname2); // Ausgabe: Mustermann Müller
  }

  console.log(nachname1); // Ausgabe: Mustermann
  console.log(nachname2); // wirft Fehler, da die Variable nachname2 hier keinen Gültigkeitsbereich mehr hat 
}

namensAusgabe();

```

### 3.2.3 const Variablen Deklaration 

* const ist eine Abkürzung und steht für constant 
* Eine Variable vom Typ constant muss bereits bei der deklaration/initialisierung einen Wert erhalten
* Eine Variable vom Typ constant kann nach der deklaration/initialisierung nicht mehr verändert werden
* der Gültigkeitsbereich einer Variable vom Typ const, ist auf den Block-Scope beschränkt 


## 3.3 Datentyp `Any`

* Typescript besitzt einen neuen Datentyp namens `any` 
* Eine Variable vom Typ `any` kann einen Wert von jedem Datentyp beinhalten 

> **Syntax & Beispiel**: `Typescript`
```typescript
let data1:string = 'Data1'

//bei der untern Zuweisung würde der Compiler einen Fehler werfen, da Variablen vom Typ String keine Zahlen beeinhalten können
// data1 = 50; 

// hat eine Variable allerdings den Typ Any, können ihr alle möglichen Werte zugewiesen werden
let data2:any = 'Data2';
data2 = 50;
data2 = true;
data2 = ['Hallo','Hello','Bonjour'];

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

let arrayStädte: string [] = ['Hamburg','Berlin','München','Stuttgart'];
console.log('arrayStädte:',arrayStädte);


let arraySprachen: Array<string> = ['C','C++','Java','Ruby','Phthon'];
console.log('arraySprachen',arraySprachen);
```

## 3.5 Tuples

* Typescript bietet eine neue Art von Array namens Tuples 
* Tuples ermöglichen das speichern von mehreren Datentypen in einem Array
* Wir deklarieren einen Tuple wie folgt: let kontaktDetails  : [string, number] = ['Dinanath', 35];

> **Syntax & Beispiel**: `Typescript`
```typescript

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

* Zugriffsmodifizierer legen die Zugriffsmöglichkeiten/Verfügbarkeit von Klassen, Interfaces, Properties und Funktionen fest
* In Typescript gibt es 3 Arten von Zugriffsmodifizierern:
  1. **public** - 
      - Auf Klassen, Methoden, etc. mit einem public Zugriffsmodifizierer kann von jeder Klasse zugegriffen werden
      - Standardmäßig sind in Typescript alle Klassen, Methoden, etc. public 
      - Auf sie kann von überall ohne Einschränkungen zugegriffen werden
  2. **private** - 
      - Sind Klassen, Methoden, etc. als private gekennzeichnet, kann auf sie nur in der Klasse, in welcher sie erstellt wurden, zugegriffen werden
      - Versucht eine andere Klasse auf sie zuzugreifen, wirft der Compiler einen Fehler
  3. **protected** - 
      - Der protected Zugriffsmodifizierer kann nur von Variablen und Methoden genutzt werden
      - Auf Methoden oder Variablen, welche mit protected gekennzeichnet sind, kann nur die Klasse, in welcher sie erstellt wurden zugreifen, oder eine Klasse, welche dieser Klasse erbt

> **Syntax & Example**: `Typescript`
```typescript

class Begrüßung {
  public name: string; //andere Klassen können zugreifen
  private privateName: string; //nur die Klasse Begrüßung kann zugreifen
  protected protectedName: string; //nur die Klasse Begrüßung kann zugreifen und Klassen, welche von Begrüßung erben

  constructor(_name: string) {
    this.name = _name;
  }

  begrüßePerson() {
    console.log(`Willkommen, hab einen schönen Tag ${this.name}!`)
  }

}

let begrüßung1 = new Greetings('Max');
console.log('begrüßung1.name:',begrüßung1.name);
begrüßung1.begrüßePerson();

// bei dem unteren console.log() würde der Compiler einen Fehler werfen, da wir außerhalb der Klasse nicht auf private Propteries zugreifen können
// console.log(begrüßung1.privateName);

console.log(`// ------------------------------`);

// Klasse Person erbt von Begrüßung
class Person extends Begrüßung {

  constructor (pName: string) {
    super(pName);
  }

  machAufgaben() {
    console.log('Person macht verschieden Aufgaben');
    // bei dem unteren console.log(), würde der Compiler nun wieder einen Fehler werfen, da die Klasse Person keinen Zugriff auf privateName hat
    // console.log(begrüßung1.privateName);

    // dadurch, dass die Klasse Person von der Klasse Begrüßung erbt, kann sie auch auf protectedName zugreifen 
    console.log('this.protectedName:',this.protectedName);
  }

}

let person1 = new Person('Tom');
console.log('person1.name:',person1.name);
person1.begrüßePerson();
person1.machAufgaben();
```


# 4. Referenzen 
 
## 4.1. Websiten / Blogs

- Offizielle website: http://www.typescriptlang.org/
- Source code: https://github.com/Microsoft/TypeScript  
- Doukemntation: https://www.typescriptlang.org/docs/




