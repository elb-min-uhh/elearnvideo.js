# elearnvideo.js

Das _elearnvideo.js_ wurde als Erweiterung für
[elearn.js](https://github.com/elb-min-uhh/elearn.js) entwickelt.
Es ist aber auch alleine nutzbar, es wird jedoch _jQuery_ benötigt, damit
_elearnvideo.js_ funktioniert.

> There is no English or international version so far.

## Nutzung

Zum Einbinden von _elearnvideo.js_ gibt es mehrere Möglichkeiten.

Ist das _elearnvideo.js_ eingebunden, wird jedes `<video>` zu einem
_elearnvideo_. Um das zu verhindern kann dem Videoelement die Klasse
`ignore_elearnvideo` ergänzt werden:

    <video class="ignore_elearnvideo">

## Supported Languages

The _elearnvideo.js_ supports a simple language selection. The default language
is _german_. To change it, you can do one of the following:

1. A `lang` attribute will cause this node and all included _elearnvideo.js_ nodes to
appear in the selected language. E.g. `<html lang="en">` to change the language
for the whole document. It is recommended to use the `lang` attribute only
on the `<html>` element and nowhere else because you will get an inconsistent
document. Changing the `lang` attribute after the document was
loaded will not change already localized elements. Use method _2_ for this.
2. The `eLearnVideoJS.setLanguage("en")` function can be used to set the language from
inside a script. You can use this for _atom-elearnjs_ projects in the
_meta custom_ block. This may be overwritten by the first method if present.

Available languages are:
* _de_: German (default)
* _en_: English

### Mit elearn.js

Mit dem _elearn.js_ ist der einfachste Weg das
[atom-elearnjs](https://github.com/elb-min-uhh/atom-elearnjs) Paket für
den Editor _Atom_. Dort kann man einfach `<video>` in seine Markdown Datei
einbauen und beim Export das _elearnvideo.js_ aktivieren und der Rest ist
automatisiert.

Die Datei [example.md](/example.md) wurde für das _atom-elearnjs_
Paket geschrieben. Es erzeugt eine einfache _elearn.js_ Ausgabe, welche das
Video beinhaltet.

### Manuell

Um _elearnvideo.js_ manuell seiner HTML Datei hinzuzufügen, müssen die folgenden
Zeilen in den `<head>`:

    <link rel="stylesheet" type="text/css" href="assets/css/elearnvideo.css">
    <script type="text/javascript" src="assets/js/min.js"></script>
    <script type="text/javascript" src="assets/js/elearnvideo.js"></script>

__Hinweis:__ Die Dateien befinden sich in dem assets _assets_ folder.
Gegebenenfalls müssen die Attribute _href_/_src_ angepasst werden, wenn Sie
manuell kopiert werden. Allerdings wird empfohlen, die Ordnerstruktur
beizubehalten, damit bspw. im _css_ verlinkte Schriftarten gefunden werden.

### Zusätze

Das _elearnvideo.js_ bietet nicht nur ein bestimmtes Player-Design an, sondern
auch ergänzende Funktionen, welche hier kurz erklärt werden.

#### Videoannotationen

Unter dem Video können freie Videoannotationen ergänzt werden, welche dann
automatisiert, während des Videos eingeblendet werden. Diese befinden
sich immer unter dem Video und sind somit im Vollbild nicht sichtbar
(Ergänzung _hinted_ beachten). Allerdings werden in der Zeitleiste gelbe
Markierungen eingefügt, welche auf die Annotationen hinweisen.

![Videoannotationen](assets/media/annotationen.png)

Um solche Notizen einzubauen ergänzt man zunächst den folgenden Block direkt
unter dem `<video>` Element:

    <div class="video_notes timestamps">
        // Notizen hier einfügen
    </div>

Innerhalb dieses `<div>` können nun einzelne Notizen ergänzt werden, welche
bspw. so aussehen:

    <div class="video_note" timefrom="0m01s" timeto="0m5s">
        Hier werden zusätzliche Informationen zu dem Videoabschnitt eingeblendet.
        Es scheint, als nehmen wir den nächsten Schritt.
    </div>

Dabei muss das Attribut `timefrom` gesetzt sein, das Attribut `timeto` ist
optional. Wird letzteres nicht angegeben, wird die Notiz nicht wieder
ausgeblendet. Mögliche Angaben sind in Form von Stunden (_h_), Minuten (_m_)
und Sekunden (_s_) möglich, wie bereits in dem Beispiel gezeigt.
Andere Beispiele wären `1h30s` oder `5m`. Lässt man die Einheit weg und gibt
bspw. nur `15` an, wird der Wert als Sekunden interpretiert.

In einer solchen Notiz kann beliebiger HTML Inhalt angezeigt werden.

##### Annotationshinweis

Ergänzt man die Klasse `hinted`, wird in dem Video zusätzlich durch ein
`Notiz anzeigen` auf eine entsprechende Notiz hingewiesen. Klingt man auf
diesen Hinweis wird zudem das Video automatisch pausiert, bei Bedarf der
Vollbildmodus beendet und die Notiz per Animation hervorgehoben.

    <div class="video_note hinted" timefrom="0m01s" timeto="0m5s">

Ein stoppendes Video kann z.B. sinnvoll sein, wenn durch ein Quizelement zu
einem bestimmten Zeitpunkt eine Verständisfrage gestellt werden soll.

##### Automatisches Stoppen

Das Video kann ab _v0.4.2_ automatisiert gestoppt werden, wenn der Notiz die
Klasse `stopping` ergänzt wird. Diese Funktion wird ggf. nicht von allen Geräten
unterstützt. Außerdem sollte diese Funktion nur in Verbindung mit `hinted`
verwendet werden, um den Nutzer nicht durch ein einfach stoppendes Video zu
verwirren.

    <div class="video_note hinted stopping" timefrom="0m01s" timeto="0m5s">

#### Nutzernotizen

Es ist möglich, dem Nutzer die Möglichkeit zu geben, eigene Notizen zu
hinterlassen.

![Notizen](assets/media/notizen.png)

Hierzu muss man dem `<video>` nur die Klasse `allow_user_notes`
hinzufügen

    <video class="allow_user_notes">
        ...
    </video>

Diese Notizen werden ebenso bestimmten Zeiten zugeordnet und dem Nutzer wieder
entsprechend angezeigt. In der Zeitleiste werden zudem blaue Markierungen
eingefügt, welche auf die Notizen hinweisen.

Da die Daten jedoch nur im lokalen Browserspeicher hinterlegt sind, ist es
möglich sie zu exportieren und somit als Datei auch dem eigenen Gerät zu
speichern.

## Beispiel

Ein einfaches Beispiel für ein Videoelement mit Notizen:

    <!--
    Nachfolgendes Video mit Kommentaren nur mit dem elearnvideo.js und zugehörigem
    elearnvideo.css möglich
    Nutzer können selbst Notizen (Text) hinterlegen. Diese werden der Video-Src zugeordnet.
    Ändert man diese `src` sind die persönlichen Notizen zu dem Video weg.
    -->
    <video preload="auto" controls="controls" class="allow_user_notes">
            <source src="assets/media/beispiel-video.mp4" type="video/mp4"></source>
            <source src="assets/media/beispiel-video.webm" type="video/webm"></source>
            Dein Browser unterstützt kein HTML5-Video. Um dir das Video dennoch ansehen zu können,
            folge einfach diesem <a href="assets/media/beispiel-video.mp4">Link</a>.
    </video>
    <div class="video_notes timestamps">
        <h4>Videoannotationen</h4>
        <div class="video_note" timefrom="0m01s" timeto="0m5s">
            Hier werden zusätzliche Informationen zu dem Videoabschnitt eingeblendet.
            Es scheint, als nehmen wir den nächsten Schritt.
        </div>
        <div class="video_note" timefrom="0m14s">
            Das war 's eigentlich auch schon damit.
        </div>
        <div class="video_note" timefrom="0m5s" timeto="0m14s">
            Hallo! Hier nur ein kurzes Beispielvideo, um zu zeigen,
            wie man mit einem HTML-Video-Tag ein Video in ein Markdown
            Dokument einbinden kann.
        </div>
    </div>

Das funktionierende Beispiel kann man hier betrachten
https://elb-min-uhh.github.io/elearnvideo.js/.


## License

_elearnvideo.js_ is developed by
[dl.min](https://www.min.uni-hamburg.de/studium/digitalisierung-lehre/ueber-uns.html)
of Universität Hamburg.

The software is using [MIT-License](http://opensource.org/licenses/mit-license.php).

cc-by Michael Heinecke, Arne Westphal, dl.min, Universität Hamburg
