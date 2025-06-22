---
layout: post
title: "Von iCloud zu Nextcloud: 1 Jahr später – ein ehrliches Review"
date: 2025-06-22 02:30:00 +0100
categories: [blog, tutorial]
tags: [icloud, nextcloud, speicher, backup, dateien]
excerpt: "Eine kurze Beschreibung des Posts, die in Übersichten angezeigt wird."
---

# Von iCloud zu Nextcloud: 1 Jahr später – ein ehrliches Review

Ein Jahr ist vergangen, seit ich den Sprung von iCloud Drive zu Nextcloud gewagt habe. Zeit für ein ehrliches Fazit: Was funktioniert besser als erwartet, wo hakt es noch und würde ich es wieder machen?

## Warum der Wechsel überhaupt?

Vor rund 2 Jahren war ich noch die typische Apple-Userin: iCloud Drive für alles, weil es einfach funktioniert. Mit der Einrichtung eines Smart Homes und der damit verbundenen Beschaffung und Einrichtung eines eigenen Servers änderte sich dann aber doch einiges und ich beschloss, darüber auch weitere Dienste selbst zu hosten. Plötzlich störte mich nicht nur der fehlende Einblick in meine eigenen Daten, sondern auch die Abhängigkeit von Apple. Der finale Auslöser war schließlich, dass bei mir im Keller ein Gerät stand, das das auch leisten konnte.

Damit es keine Missverständnisse gibt: Ich schwöre weiterhin auf macOS/iOS und werde mir auch in Zukunft entsprechende Geräte kaufen, weil ich nicht nur seit Ewigkeiten schon damit arbeite, sondern insbesondere auch von dem System, App-Design und den Apps im Allgemeinen überzeugt bin. Für viele Anwendungsbereiche gibt es leider auf anderen Systemen keine für mich adäquaten Alternativen. Gleichwohl bedeutet das nicht, dass ich mich mit anderen Diensten auch im Apple-Ökosystem bewegen muss – und auch weitere kleine Geräte müssen nicht mehr exklusiv von Apple sein. (Gesendet von meinem Lenovo ThinkPad mit Arch Linux)

## Das Setup: Sicherheit first

Bevor wir zu den Erfahrungen kommen, kurz zu meinem Setup: Nextcloud läuft auf meinem QNAP TS-873AeU-RP und ist nicht direkt über das Internet erreichbar. Stattdessen greife ich von unterwegs über VPN zu – aktuell noch über die Fritz!Box, aber der Wechsel zu WireGuard steht auf meiner To-Do-Liste. Hätte ich damals mein heutiges Wissen gehabt, hätte ich mir nicht den Rackmount-NAS von QNAP gekauft – zumal ich die meisten Dienste gar nicht nutze, Docker sei dank –, sondern mir einen eigenen Server zusammengestellt. Egal, das Gerät steht da jetzt und funktioniert.

Besonders praktisch: Ich habe Automationen auf meinen Geräten eingerichtet, die automatisch die VPN-Verbindung aufbauen, sobald ich das Heimnetzwerk verlasse. So bin ich immer mit meinen Daten verbunden, ohne daran denken zu müssen.

## Was funktioniert besser als erwartet

### Stabilität und Zuverlässigkeit

Nach einem Jahr kann ich sagen: Nextcloud läuft verdammt stabil. Synchronisation funktioniert schnell und zuverlässig – tatsächlich schneller als iCloud Drive es manchmal war, gerade bei der Synchronisation von neuen oder geänderten Dateien auf anderen Geräten; keine mysteriösen Sync-Probleme aus dem Nichts.

### Akzeptanz in der Familie

Überraschend positiv war auch die Reaktion der Familie: Für jedes Familienmitglied habe ich auch ein eigenes Benutzerkonto angelegt. Während manche Familienmitglieder es wenig bis gar nicht nutzen, gibt es auch regelmäßige User. Der geteilte Familienordner für Fotos und Dokumente wird gut und gerne angenommen.

### Performance und Skalierung

Mit meinem strukturierten Ansatz für mein Archiv bleibt die Performance auch bei großen Datenmengen gut, sowohl für Fotos als auch sonstige Dateien oder Dokumente.

## Was immer noch nervt (und meine Workarounds)

### macOS-App Probleme

Die größte Baustelle ist leider die macOS-App. Sie hängt sich regelmäßig beim Öffnen auf, besonders bei der Einrichtung verschiedener Ordnerfreigaben. Das liegt hauptsächlich daran, dass bei der Fülle an Ordnern das Scrollen in der Auswahl laggt und die App überfordert ist. Das liegt hauptsächlich daran, dass für jedes Jahr im Fotoarchiv ein eigener Ordner als Sync-Ordner hinzugefügt wurde, damit bei einer Änderungen an einzelnen Dateien nicht gleich der gesamte Ordner abgeblichen werden muss. Auch das Ignorieren von bestimmten Ordnern oder Dateien funktioniert leider nicht, wie es sein sollte; hier geht es insb. um Vorschaubilder und Cache-Dateien von Capture One.

### UI/UX-Kleinigkeiten

Manche Sachen könnten im Interface einfacher zugänglich sein:

- Medien auf Smartphone/Tablet sind umständlich zu handhaben
- Download von geteilten Dateien im Browser versteckt sich hinter dem 3-Punkte-Menü
- Allgemein ist die Bedienung weniger intuitiv als die Apple-Pendants

### Foto-Management nicht auf Apple-Niveau

Neben  der Nextcloud-Galerie ist auch Nextcloud Memories  eine tolle App, aber die Übersicht und besonders die Suchfunktion erreichen nicht die Qualität von Apple Fotos. Hier teste ich parallel noch Immich als Alternative.

## Apps und Erweiterungen: Weniger ist mehr

Nextcloud bietet unzählige Apps und Erweiterungen . Ironischerweise nutze ich aber fast keine davon. Neben den Standard-Apps läuft nur Nextcloud Memories für die Fotoverwaltung.

Die Apps für Kalender, Notizen und Kontakte schaue ich mir für die Zukunft noch genauer an – könnte interessant werden, wenn ich wirklich komplett aus dem Apple-Ökosystem aussteigen will.

## iCloud Drive heute: Fast abgelöst

Nextcloud hat iCloud Drive bei mir zu fast vollständig ersetzt. Dateien lege ich nur noch temporär und in spezifischen Fällen in iCloud Drive ab.

## Sicherheit und Zukunftspläne

Aktuell läuft der externe Zugriff noch über das Fritz!Box-VPN. Für die Zukunft plane ich:

1. Umstellung auf WireGuard: Bessere Performance und modernere Verschlüsselung
2. Eingeschränkter VPN-Zugriff für Familienmitglieder: Statt Vollzugriff aufs Netzwerk nur Port-Forwarding für Nextcloud
3. Erweiterte Backup-Strategie: Automatisierung von Backups nach der 3-2-1-Regel

## Kosten vs. Nutzen nach einem Jahr

### Kosten

- Hardware: Rackmount-NAS wurde angeschafft, hätte aber auch ein Eigenbau sein können; auf einem Raspberry Pi 5 mit M.2-SSD (meine Testumgebung) lief es übrigens auch schnell und zuverlässig
- Strom: rund 540 kWh
- Zeit: Initial-Setup (10 Tage), Wartung  (1 Stunde/Monat)
- vs. Apple One Premium mit 2 TB (35 €/Monat) zzgl. iCloud+ 2 TB (10 €/Monat) = 540 €/Jahr (durch ein Downgrade auf Apple One Family mit 200 GB lägen die Kosten bei 310 €/Jahr, was einer Ersparnis von 230 €/Jahr entspricht)

### Nutzen

- Vollständige Kontrolle über meine Daten
- Keine Speicherlimits (außer der Hardware)
- Lerneffekt über Server-Administration
- Privacy: Meine Daten bleiben bei mir
- Flexibilität bei Apps und Konfiguration

## Was habe ich gelernt?

1. Migration schrittweise machen: Nicht alles auf einmal umstellen
2. Familie früh einbeziehen: Change-Management ist wichtig 😄
3. Backups nicht vergessen: Selbst gehostete Daten brauchen auch Backups
4. UI-Gewohnheiten umstellen: Apple hat mich verwöhnt, aber vielleicht kann ich mich umgewöhnen
5. Automationen sind Gold wert: automatische VPN-Verbindung macht den Alltag einfacher

## Würde ich es wieder machen?

Ja, definitiv. Trotz aller kleinen Macken und der gelegentlich hängenden macOS-App überwiegen die Vorteile deutlich. Die einzige Einschränkung: Man braucht die Bereitschaft, sich mit der Technik auseinanderzusetzen. Wer wirklich nur «es soll einfach funktionieren» will, ist mit iCloud besser bedient.

## Was kommt als nächstes?

- Immich-Test: Bessere Foto-Verwaltung als Alternative zu Memories
- WireGuard-Migration: Moderneres VPN-Setup
- Apps-Deep-Dive: Kalender und Notizen genauer anschauen
- Performance-Tuning: Noch mehr aus dem Setup herausholen
