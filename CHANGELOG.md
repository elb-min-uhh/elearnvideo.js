### elearnvideo.js

* __0.4.1__:
  * Fehlerbehebungen:
    * Schriftarten zusätzlich als _.ttf_ hinzugefügt
    * Fehlerbehebungen für CSS Flex Attribut (WebKit)
  * Anderes:
    * Code refactoring: alle Funktionen in `eLearnVideoJS` und nicht mehr in anonymer Funktion
* __0.4.0__ (zu eLearn.js 1.0.1):
  * Neuerungen:
    * Das _elearnvideo.js_ kann nun auch unabhängig vom _elearn.js_ verwendet werden
* __0.3__ (zu eLearn.js 1.0.0):
  * Neuerungen:
    * Es wurden weitere Quelltextkommentare ergänzt, um alle Funktionen zu
    erklären
* __0.2__ (zu eLearn.js 0.9.9):
  * Neuerungen:
    * Bufferanimation
    * Videoplayerskalierung nicht mehr über JavaScript sondern CSS
    * Fehlermeldung, wenn Video nicht geladen werden kann
    * Unterstützung für Einbindung in OLAT. OLAT-Player wird dafür unterdrückt
    * Persönliche Notizen können auf Wunsch unter jedem Video ergänzt werden.
    Videos können dazu mit der Klasse "allow_user_notes" versehen werden
  * Fehlerbehebungen:
    * Zeitvorschau über Fortschrittsbalken jetzt korrekt
    * Wechsel zwischen Touch- und Maussteuerung jetzt funktionsfähig
    * Videosteuerung verbessert. Keine ungewollten Sprünge im Videofortschritt
    mehr
    * Keine Tastensteuerung zum Sectionwechsel möglich, wenn Video im
    Vollbildmodus abgespielt wird
* __0.1__ (zu eLearn.js 0.9.8):
  * Grundversion:
    * Eigener HTML5 Videoplayer (Mobile + Desktop)
    * Anmerkungen unter dem Video möglich (Durch Ersteller des Skripts)
