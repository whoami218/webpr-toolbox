# Woche 14

## JS-Goodie
```
['8','9','10'].map(n => Number(n));      // [8, 9, 10]
['8','9','10'].map(n => parseInt(n));    // [8, 9, 10]

['8','9','10'].map(Number);               // [8, 9, 10]
['8','9','10'].map(parseInt);             // [8, NaN, 2]

```
parseInt kann also nicht Etareduziert werden, da es eigentlich 2 Argumente erwartet
also eigentlich parseInt(n, radix) wobei radix die Basis ist.

Wenn man also im 10ner System rechnet nimmt man am besten immer Number anstatt einer parse Funktion


## UI Framework
Unterschiedliche Lösungsansätze für den Aufbau / Nutzung eines FW

- Starte am Ende (statisches HTML)
- Tests sind alle fehlerhaft
- einfachste Lösung welche irgendwie funktioniert
- dann Schritt für Schritt verbessern

**Milestone 1**
- es läuft alles
- angemessene Anzahl an Tests
- alle Tests sind grün
- Verantwortlichkeiten verbessern
- Code vereinfachen und verbessern  

**Milestone 2**
- Separiere die Logik von der Darstellung
- Alle Tests müssen immernoch grün sein

**Milestone 3**
- View, Model, Controller trennen
- Alle Tests müssen immernoch grün sein

**Milestone 4**
- Alle Views sind separiert
- Alle Tests müssen immernoch grün sein
