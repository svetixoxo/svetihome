# Meine Homelab-Infrastruktur: Ein Überblick

Was als einfaches Smart-Home-Projekt begann, ist inzwischen zu einer umfassenden Infrastruktur gewachsen. In diesem Beitrag gebe ich einen Überblick über die verschiedenen Komponenten und erkläre, warum bestimmte Entscheidungen getroffen wurden.

## Das Netzwerk als Grundlage

Das Herzstück jeder vernetzten Infrastruktur ist ein stabiles Netzwerk. Als Hauptrouter dient eine AVM Fritz!Box 6690 Cable, die durch fünf weitere Fritz!Box 7590 AX ergänzt wird. Zusätzlich sorgen vier FRITZ!Repeater 6000 und zwei FRITZ!Repeater 3000 für eine weitestgehend lückenlose WLAN-Abdeckung im Haus und Garten. Diese Konfiguration entstand durch die baulichen Gegebenheiten des Grundstücks – im Grunde befinden sich in jedem Stockwerk zwei Router, die über Kabel zusammenlaufen. Die Repeater sorgen dafür, dass das WLAN-Netzwerk auch um das Haus herum sichergestellt ist.

Für die kabelgebundene Infrastruktur kommen drei Netgear-Switches zum Einsatz, nämlich zwei mit jeweils mit 24 Ports und eine mit 48 Ports. Die eine 24er Switch ist für die LAN-Buchsen im Haus sowie Geräte im Netzwerkschrank zuständig. An der anderen 24er Switch laufen die Geräte für das Smart Home zusammen. Die Switch mit 48 Ports verbindet 37 elektrische Jalousien mit dem Netzwerk.

Für zusätzliche Sicherheit sorgt eine WatchGuard Firebox M290 als Firewall-Lösung.

## Server-Landschaft: Getrennte Aufgaben

Die Server-Infrastruktur besteht aus zwei QNAP-Systemen.

Das erste ist ein TS-1273AU-RP mit einer NVIDIA Quadro P1000 (Grafikkarte), 64 GB Arbeitsspeicher  und 12 Festplatten mit je 24 TB (Seagate Exos X24). Diese Konfiguration ist ausschließlich für die Videoüberwachung ausgelegt – die Grafikkarte übernimmt dabei das Transcoding von Videos, während der große Speicherplatz die Aufzeichnung von 26 Kameras über längere Zeiträume ermöglicht. Das SSD-Caching übernehmen zwei Samsung 990 Pro mit je 4 TB.

Der zweite Server, ein TS-873AeU-RP mit 64 GB Arbeitsspeicher und 8 Festplatten mit je 12 TB (Seagate Exos X14). Dieses System fungiert als Heimserver. Hier laufen die Automatisierungslogik, Homebridge und weitere Dienste, die für die Haussteuerung erforderlich sind. Das SSD-Caching übernehmen zwei Samsung 980 Pro mit je 2 TB.

Beide Systeme nutzen Samsung SSD-Cache (990 Pro bzw. 980 Pro) für bessere Performance bei häufig zugegriffenen Daten.

## Videoüberwachung: Professionelle Sicherheit

Die Videoüberwachung umfasst 26 Kameras von ABUS, aufgeteilt in verschiedene Typen je nach Einsatzgebiet. Zwölf Thermal Tube Bi-Spektral Kameras überwachen den Außenbereich und können sowohl im normalen als auch im Wärmebild-Modus arbeiten. Acht Thermal Dome Kameras mit ähnlicher Technologie kommen im Innenbereich zum Einsatz, während sechs IP-Fisheye-Kameras mit ihrer 360-Grad-Sicht größere Räume abdecken.

Für die Aufzeichnung sorgen zwei 16-Kanal NVR-Systeme von ABUS, die redundant arbeiten. Die eigentliche Speicherung erfolgt jedoch auf dem Haupt-NAS, was eine zentrale Verwaltung und bessere Integration in die Backup-Strategie ermöglicht.

## Smart Home: Vollständige Automatisierung

Die Klimatisierung des Hauses übernehmen mehrere Mitsubishi Multi-Split-Anlagen. Zwei MXZ-3F68VF4 Außengeräte mit je 6,8 kW Leistung versorgen zusammen mit sechs MUZ-AY42VG Innengeräten verschiedene Bereiche. Über acht MAC-587IF WLAN-Brücken lassen sich alle Geräte in die Smart Home Zentrale einbinden. Ergänzt wird das System durch verschiedene Steuermodule und zwei Viessmann Vitovent 300-W Lüftungsanlagen.

Die Fußbodenheizung in neun Räumen wird über ein separates Gateway-System gesteuert, das wiederum in Apple HomeKit integriert ist. Diese Trennung der Systeme ermöglicht es, auch bei Ausfall einzelner Komponenten die Grundfunktionen aufrechtzuerhalten.

Für die Sicherheit sorgt eine umfassende Alarmanlage mit 16 Bewegungsmeldern, 50 Tür- und Fensterkontakten, 17 Rauch- und vier Gasmeldern. Auch diese Anlage ist über ein Gateway in das Smart Home System eingebunden.

Die Beleuchtung ist vollständig automatisiert - sowohl die Außenbeleuchtung auf beiden Grundstücken als auch die Innenbeleuchtung in jedem Raum mit direkter und indirekter Beleuchtung. 83 smarte Steckdosen von Legrand und 25 Lichtschalter mit Dimmer-Funktion ergänzen das System. Bewegungsmelder in jedem Raum sorgen für automatisches Ein- und Ausschalten je nach Anwesenheit.

54 Jalousien werden über separate Gateways gesteuert und in das Gesamtsystem eingebunden. Eine Gira Wetterstation Plus liefert Wetterdaten für die Automatisierung - bei starkem Wind fahren beispielsweise automatisch alle Jalousien hoch.

## Zentrale Steuerung und Monitoring

Drei iPad Air mit M1-Chip sind fest in verschiedenen Stockwerken installiert und dienen als zentrale Steuereinheiten. Sie zeigen den Status aller Systeme an und ermöglichen die manuelle Steuerung einzelner Komponenten. Die Integration erfolgt über insgesamt 62 verschiedene Gateways und Bridges, die die unterschiedlichen Protokolle der Geräte in Apple HomeKit übersetzen.

Für die tägliche Arbeit steht ein iMac mit M3-Chip, 24 GB RAM und 1 TB Speicher zur Verfügung, ergänzt durch einen Mac Studio und verschiedene mobile Geräte.

## Kosten und Wirtschaftlichkeit

Die Hardware-Investition bewegt sich im mittleren fünfstelligen Bereich. Besonders die Klimaanlagen und die Videoüberwachung schlagen dabei zu Buche. Die laufenden Kosten entstehen hauptsächlich durch den Stromverbrauch der Server und der zahlreichen Netzwerkkomponenten.

Dennoch amortisiert sich die Investition teilweise durch Energieeinsparungen bei der intelligenten Steuerung von Heizung und Klimaanlage sowie durch den Wegfall externer Dienstleister für Überwachung und Wartung.

## Erfahrungen und Lessons Learned

Die größte Herausforderung liegt in der Komplexität des Systems. Je mehr Komponenten vernetzt sind, desto wichtiger wird eine saubere Dokumentation und strukturierte Fehlersuche. Was als einfache Automatisierung beginnt, kann schnell zu einem Vollzeitjob werden, wenn man nicht von Anfang an systematisch vorgeht.

Gleichzeitig bietet die umfassende Automatisierung einen Komfort, auf den man nicht mehr verzichten möchte. Das Haus "denkt mit" - von der automatischen Anpassung der Temperatur über die Beleuchtung bis hin zur Sicherheit.

## Ausblick

Die Infrastruktur ist nie wirklich "fertig". Regelmäßig kommen neue Komponenten dazu oder bestehende werden durch bessere Alternativen ersetzt. Aktuell stehen Optimierungen bei der Energieeffizienz und die Integration weiterer Automatisierungen auf der Agenda.

Für jeden, der ein ähnliches Projekt plant: Fangt klein an, dokumentiert alles und lasst das System organisch wachsen. Rom wurde auch nicht an einem Tag erbaut.
