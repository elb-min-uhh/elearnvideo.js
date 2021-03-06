### elearnvideo.js

* __0.4.3__:
    * General
        * CSS -> SASS/SCSS: use variables for color styling
        * Changed a few colors
    * Fixes:
        * Do not stop on stopping notes when skipping with the mouse
        * Do not stop on stopping notes when toggling `Display all`

* __0.4.2__:
    * New:
        * Support for localization including German and English language
        with `<.. lang="en">` or `eLearnVideoJS.setLanguage("en")`
            * German is selected per default
        * Video notes of class `stopping` stop the video automatically
        * Arrow keys let the video skip 5 seconds
    * Fixes:
        * `hinted` notes select the correct note tab on click
        * note hint shadow added for better visibility
        * `Display all` in own line to prevent overlapping

#### Older versions (currently not available in _english_)

* __0.4.1__:
  * Neuerungen:
    * Video Notizen mit der Klasse `hinted` erzeugen einen Hinweis, der beim
    Anklicken die Notiz anzeigt, Vollbild beendet und das Video pausiert
  * Fehlerbehebungen:
    * Schriftarten zusätzlich als _.ttf_ hinzugefügt
    * Fehlerbehebungen für CSS Flex Attribut (WebKit)
    * Im Vollbildmodus ist wieder ein Springen in der Zeit sowie
    Lautstärkeänderung möglich
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
