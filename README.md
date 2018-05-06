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
