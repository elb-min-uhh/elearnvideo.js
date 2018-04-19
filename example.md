# Einfaches elearnvideo.js Beispiel

<!-- Nachfolgendes Video mit Kommentaren nur mit dem video.js und zugehörigem video.css möglich -->
<!-- Nutzer können selbst Notizen (Text) hinterlegen. Diese werden der Video-Src zugeordnet. Ändert man diese
    Sind die persönlichen Notizen zu dem Video weg (werden gelöscht wenn passendes Video nicht gefunden). -->
<video preload="auto" controls="controls" class="allow_user_notes">
        <source src="assets/media/beispiel-video.mp4" type="video/mp4"></source>
        <source src="assets/media/beispiel-video.webm" type="video/webm"></source>
        Dein Browser unterstützt kein HTML5-Video. Um dir das Video dennoch ansehen zu können,
        folge einfach diesem <a href="assets/media/beispiel-video.mp4">Link</a>.
</video>
<div class="video_notes timestamps">
    <h4>Videoannotationen</h4>
    <div class="video_note" timefrom="0m01s" timeto="0m5s">
        Hier werden zusätzliche Informationen zu dem Videoabschnitt eingeblendet. Es scheint, als nehmen wir den nächsten Schritt.
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
