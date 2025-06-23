# Mein Smart Home und die Infrastruktur dahinter

Was als einfaches Smart-Home-Projekt begann, ist inzwischen zu einer umfassenden Infrastruktur gewachsen. In diesem Beitrag gebe ich einen Überblick über die verschiedenen Komponenten und erkläre, warum bestimmte Entscheidungen getroffen wurden.

## Das Netzwerk als Grundlage

Das Herzstück jeder vernetzten Infrastruktur ist ein stabiles Netzwerk. Als Hauptrouter dient eine AVM Fritz!Box 6690 Cable, die durch fünf weitere Fritz!Box 7590 AX ergänzt wird. Zusätzlich sorgen vier FRITZ!Repeater 6000 und zwei FRITZ!Repeater 3000 für eine weitestgehend lückenlose WLAN-Abdeckung im Haus und Garten. Diese Konfiguration entstand durch die baulichen Gegebenheiten des Grundstücks – im Grunde befinden sich in jedem Stockwerk zwei Router, die über Kabel zusammenlaufen. Die Repeater sorgen dafür, dass das WLAN-Netzwerk auch um das Haus herum sichergestellt ist.

Für die kabelgebundene Infrastruktur kommen drei Netgear-Switches zum Einsatz, nämlich zwei mit jeweils mit 24 Ports und eine mit 48 Ports. Die eine 24er Switch ist für die LAN-Buchsen im Haus sowie Geräte im Netzwerkschrank zuständig. An der anderen 24er Switch laufen die Geräte für das Smart Home zusammen. Die Switch mit 48 Ports verbindet 44 elektrische Jalousien mit dem Netzwerk.

Für zusätzliche Sicherheit sorgt eine WatchGuard Firebox M290 als Firewall-Lösung.

## Server-Landschaft: Getrennte Aufgaben

Die Server-Infrastruktur besteht aus zwei QNAP-Systemen.

Das erste ist ein TS-1273AU-RP mit einer NVIDIA Quadro P1000 (Grafikkarte), 64 GB Arbeitsspeicher  und 12 Festplatten mit je 24 TB (Seagate Exos X24). Diese Konfiguration ist ausschließlich für die Videoüberwachung ausgelegt – die Grafikkarte übernimmt dabei das Transcoding von Videos, während der große Speicherplatz die Aufzeichnung von 26 Kameras über längere Zeiträume ermöglicht. Das SSD-Caching übernehmen zwei Samsung 990 Pro mit je 4 TB.

Der zweite Server, ein TS-873AeU-RP mit 64 GB Arbeitsspeicher und 8 Festplatten mit je 12 TB (Seagate Exos X14). Dieses System fungiert als Heimserver. Hier laufen die Automatisierungslogik, Homebridge und weitere Dienste, die für die Haussteuerung erforderlich sind. Das SSD-Caching übernehmen zwei Samsung 980 Pro mit je 2 TB. Über Homebridge können alle Geräte über Apple HomeKit angesteuert werden. Darüber hinaus läuft hierüber mit Nextcloud auch meine eigene Daten-Cloud. Darüber soll es in diesem Beitrag aber nicht gehen.

Beide Systeme nutzen Samsung SSD-Cache (990 Pro bzw. 980 Pro) für bessere Performance bei häufig zugegriffenen Daten.

## Videoüberwachung: Professionelle Sicherheit

Die Videoüberwachung umfasst 26 Kameras, aufgeteilt in drei verschiedene Typen je nach Einsatzgebiet. Dazu zählen 12 bispektrale Tube-Kameras (Wärmemild) im Außenbereich sowie 8 bispektrale Dome-Kameras (schwenkbar und neigbar) und 6 Fisheye-Kameras (360 Grad) im Innen- und Außenbereich.

Die Kameras laufen an zwei 16-Kanal-NVR-Systemen zusammen, die Speicherung der Aufzeichnungen erfolgt jedoch auf dem 12-Bay-NAS, was eine zentrale Verwaltung, reaktionsfreudigere Handhabung, längere Speicherdauer und bessere Integration via Homebridge ermöglicht.

## Smart Home: Vollständige Automatisierung

Die Klimatisierung des Hauses übernehmen 8 Multi-Split-Klimaanlagen von Mitsubishi Electric, 2 mit je 6,8 kW und 6 mit je 4,2 kW Leistung. Über WLAN-Brücken sind diese in das Smart Home eingebunden. Ergänzt wird das System durch verschiedene Steuermodule und eine Lüftungsanlage (Viessmann Vitovent 300-W).

Die Fußbodenheizung in neun Räumen wird über ein separates Gateway-System gesteuert, das wiederum über eine der Switches in das Smart Home integriert ist. Darüber hinaus ist auch weiterhin eine manuelle Steuerung möglich. Dadurch ist es möglich, auch bei Ausfall einzelner Komponenten die Grundfunktionen aufrechtzuerhalten.

Für die Sicherheit sorgt eine umfassende Alarmanlage mit 16 Bewegungsmeldern, 50 Tür- und Fensterkontakten, 15 Rauch- und 4 Gasmeldern. Auch diese Anlage ist über ein Gateway in das Netzwerk eingebunden.

Die Beleuchtung ist vollständig automatisiert – sowohl die Außenbeleuchtung auf dem Grundstück und am Haus als auch die Innenbeleuchtung in jedem Raum mit direkter und indirekter Beleuchtung. 83 smarte Steckdosen und 25 smarte Lichtschalter mit Dimmer-Funktion (bei Bedarf einsetzbar) ergänzen das System. Bewegungsmelder in jedem Raum sorgen für automatisches Ein- und Ausschalten je nach Anwesenheit.

Die Jalousien werden ebenfalls über separate Gateways gesteuert und in das Gesamtsystem eingebunden. Eine Wetterstation liefert darüber hinaus Wetterdaten für die Automatisierung. So werden etwa alle Jalousien bei starkem Wind hochgefahren oder die Klimaanlagen (je nach Anwesenheit) bei hohen Außentemperaturen eingeschaltet; dies gilt entsprechend auch für die Heizung. Darüber hinaus wird über den Stromverbrauch bestimmter Steckdosen (Computer im Arbeitszimmer, Fernseher im Wohnzimmer, Nachtlicht im Schlafzimmer usw.) erkannt, in welchem Raum bzw. Stockwerk ich gerade unterwegs bin und Klimaanlage bzw. Heizung dort dementsprechend auch etwas stärker eingesetzt.

## Zentrale Steuerung und Monitoring

Drei iPad Air mit M1-Chip sind fest in verschiedenen Stockwerken installiert und dienen als zentrale Steuereinheiten. Sie zeigen den Status aller Systeme an und ermöglichen die manuelle Steuerung einzelner Komponenten. Die Integration erfolgt über insgesamt 62 verschiedene Gateways und Bridges, die die unterschiedlichen Protokolle der Geräte in Apple HomeKit übersetzen.

An den Treppenaufgängen jeder Etage ist je ein iPad in der Wand installiert, die als weitere Steuereinheiten dienen. Sie zeigen den Status der jeweiligen Systeme an und ermöglichen die manuelle Steuerung einzelner Komponenten. Darüber hinaus ist eine Steuerung über iPhone, Mac usw. möglich.

## Kosten und Wirtschaftlichkeit

Die Hardware-Investition in das Smart Home bewegt sich im mittleren fünfstelligen Bereich. Die Kosten beziehen sich dabei nicht auf die Endgeräte (Steckdosen etc. ausgenommen), sondern auf die dafür notwendige smarte Infrastruktur wie Gateways, Bridges und Steuerungskomponenten zur Einbindung in das vernetzte Gesamtsystem.

Die laufenden Kosten entstehen hauptsächlich durch den Stromverbrauch der Server und der zahlreichen Netzwerkkomponenten.

Dennoch amortisiert sich die Investition teilweise durch Energieeinsparungen bei der intelligenten Steuerung von Heizung und Klimaanlage sowie durch den Wegfall externer Dienstleister für Überwachung und Wartung. Außerdem ist es irgendwie cool, wenn solche Sachen von selbst laufen bzw. man es so einfach bedienen kann.

## Erfahrungen

Die größte Herausforderung liegt in der Komplexität des Systems. Je mehr Komponenten vernetzt sind, desto wichtiger wird eine saubere Dokumentation und strukturierte Fehlersuche. Was als einfache Automatisierung beginnt, kann schnell zu einem Teilzeitjob werden, wenn man nicht von Anfang an systematisch vorgeht.

So hatte ich bspw. das Dokument verlegt, aus dem hervorging, welche Nummer welche Steckdose hat; der Betrieb, der die Installation dieser Geräte vornahm, hatte auf meine Anweisung auch keine Kopie behalten. Während der Einrichtung und Benennung in der Home-App lief ich also mit iPad in der einen und Tischlampe in der anderen Hand von Steckdose zu Steckdose und schaute, welches Gerät in der Home-App plötzlich Stromverbrauch registrierte, wenn ich die Lampe einschaltete. Das ursprüngliche Papier ist übrigens bis heute nicht wieder aufgetaucht.

Gleichzeitig bietet die umfassende Automatisierung einen Komfort, auf den ich nicht mehr verzichten möchte. Das Haus denkt mit – von der automatischen Anpassung der Temperatur über die Beleuchtung bis hin zur Sicherheit und vielem mehr.

## Ausblick

Die Infrastruktur ist nie wirklich fertig. Regelmäßig kommen neue Ideen dazu und es stehen immer wieder Optimierungen bei der Energieeffizienz und insbesondere Integration weiterer Automatisierungen auf der Agenda.

Für jeden, der ein ähnliches Projekt plant, empfehle ich, klein anzufangen, alles zu dokumentieren und das System organisch wachsen zu lassen.
