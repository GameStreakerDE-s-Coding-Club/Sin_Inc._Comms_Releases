# Sin Inc. Comms – TS3 Radio Plugin

*by GameStreakerDE*

> Funk-Simulation für TeamSpeak 3 — Frequenzen, Passwörter, Ducking, Hotkeys und Profile.

[![Download](https://img.shields.io/github/v/release/GameStreakerDE-s-Coding-Club/Sin_Inc._Comms_Releases?label=Download&style=for-the-badge)](https://github.com/GameStreakerDE-s-Coding-Club/Sin_Inc._Comms_Releases/releases/latest)

---

---

## Inhaltsverzeichnis

1. [Installation](#1-installation)
2. [Plugin aktivieren](#2-plugin-aktivieren)
3. [Dialog öffnen](#3-dialog-öffnen)
4. [General Tab – Radios einrichten](#4-general-tab--radios-einrichten)
5. [Hotkeys einrichten](#5-hotkeys-einrichten)
6. [Encryption Tab – Passwörter](#6-encryption-tab--passwörter)
7. [Ducking Tab](#7-ducking-tab)
8. [Settings Tab](#8-settings-tab)
9. [Profiles Tab](#9-profiles-tab)
10. [Buttons: OK / Abbrechen / Reset](#10-buttons-ok--abbrechen--reset)
11. [Update & Deinstallation](#11-update--deinstallation)
12. [Häufige Fragen](#12-häufige-fragen)
13. [Hinweis für Server-Admins](#13-hinweis-für-server-admins)
14. [Third-Party-Lizenzen](#14-third-party-lizenzen)

---

## 1. Installation

1. TeamSpeak 3 **schließen**
2. Doppelklick auf die Datei `gs_comms_X.Y.Z_x64.ts3_plugin`
3. TS3 öffnet sich automatisch und fragt nach Bestätigung → **Installieren**
4. TS3 neu starten

---

## 2. Plugin aktivieren

Das Plugin aktiviert sich nach der Installation **automatisch**.

Falls es nicht aktiv ist:

1. In TS3: **Extras → Optionen → Erweiterungen**
2. Tab **My Addons** öffnen
3. **Sin Inc. Comms** in der Liste suchen
4. Auf den Button **Deaktiviert** klicken um es zu aktivieren

> 💡 TS3 zeigt immer den **aktuellen Status** des Plugins an: „Deaktiviert" = aus, „Aktiviert" = an.

---

## 3. Dialog öffnen

Klicke in der TS3-Menüleiste auf:

> **Plugins → Sin Inc. Comms → Funk**

Es öffnet sich das Hauptfenster mit fünf Tabs:
`General` | `Ducking` | `Encryption` | `Settings` | `Profiles`

---

## 4. General Tab – Radios einrichten

Der General Tab ist die Hauptansicht. Hier richtest du deine Radios ein.

### Übersicht einer Radio-Zeile

| Element | Bedeutung |
|---|---|
| **Toggle (Schalter links)** | Radio ein- oder ausschalten |
| **Name** | Doppelklick zum Umbenennen (z.B. "Haupt", "Backup") |
| **HotKey** | Klicken um eine Taste zum Senden zuzuweisen |
| **Frequenz-Anzeige** | Aktuelle Frequenz (grün leuchtend) |
| **Set** | Frequenz eingeben und Radio aktivieren |
| **▲ (Pfeil oben)** | Leuchtet wenn du auf diesem Radio **sendest** |
| **▼ (Pfeil unten)** | Leuchtet wenn du auf diesem Radio **empfängst** |
| **🔒** | Passwort ist gesetzt (Schloss-Symbol) |
| **🔇** | Empfang ist stummgeschaltet |
| **Balance** | Wo das Radio im Stereo-Bild liegt (L = links, C = Mitte, R = rechts) |
| **Lautstärke** | Lautstärke dieses Radios (Standard: 1.0x) |

### Frequenz setzen und Radio aktivieren

1. Frequenz in das Eingabefeld tippen (z.B. `118.50`)
2. **Set** drücken → das Radio wird **automatisch aktiviert**

> ⚠️ Alle Nutzer auf derselben Frequenz müssen exakt dieselbe Zahl eingegeben haben.

- Wenn das Radio **an** ist: Frequenz und Set-Button sind gesperrt (grau)
- Zum **Ausschalten**: Toggle links betätigen → Frequenzfeld wird wieder editierbar
- Solange keine Frequenz gesetzt ist, ist der Toggle ohne Funktion

### Radio benennen

Doppelklick auf den Namen (z.B. "Radio 1") → Text ändern → **Enter**

### Balance und Lautstärke zurücksetzen

Doppelklick auf den Balance-Regler → Mitte (C)
Doppelklick auf den Lautstärke-Regler → Standard (1.0x)

### Advanced Modus (8 Radios)

Unten links: **Advanced** aktivieren → 8 Radios statt 4 verfügbar.

---

## 5. Hotkeys einrichten

Hotkeys werden **direkt im Plugin-Dialog** über die **HotKey-Buttons** konfiguriert — **nicht** über die TS3-Einstellungen. Sie werden sofort in der INI-Datei gespeichert.

### Hotkey für ein Radio setzen

1. Im **General Tab** auf den **HotKey**-Button des gewünschten Radios klicken
2. Den gewünschten Hotkey drücken → wird sofort in der INI gespeichert
3. Zum Abbrechen: **ESC** drücken
4. Zum Löschen: **Entf** drücken

### Globale Hotkeys

Im **Settings Tab** können weitere globale Hotkeys konfiguriert werden — ebenfalls direkt im Plugin-Dialog per HotKey-Button:

| Hotkey | Funktion |
|---|---|
| **Push-To-Mute All** | Alle Funkkanäle stummschalten (gehalten) |
| **Push-To-Mute Channel** | Nur Channel stummschalten (gehalten) |
| **Toggle Mute** | Modifier – muss in Kombination mit dem PTT-Hotkey des Kanals gedrückt werden um den Empfang zu stummschalten |
| **Toggle Radio** | Modifier – muss in Kombination mit dem PTT-Hotkey des Kanals gedrückt werden um den Funk-Channel ein-/auszuschalten |

---

## 6. Encryption Tab – Passwörter

Passwörter verhindern dass Nutzer ohne das richtige Passwort mithören können – auch wenn sie auf derselben Frequenz sind.

### Passwort setzen

1. Tab **Encryption** öffnen
2. Beim gewünschten Radio ein Passwort eingeben
3. **Setzen** klicken

> ⚠️ Alle Nutzer auf dieser Frequenz müssen **dasselbe Passwort** eingegeben haben.

### Passwort entfernen

Passwortfeld leeren → **Setzen** – danach ist die Frequenz wieder offen.

### Sicherheit

Das Passwort wird **niemals** im Klartext übertragen. Es wird als SHA-256-Hash gespeichert und über TS3 ausgetauscht. Niemand kann dein Passwort direkt auslesen.

### Kanalname mit Passwort

Wenn die Frequenz über einen **Kanalnamen** übertragen wird, muss der Kanalname den Hash in eckigen Klammern enthalten:

```
118.50 [3A7F2C1B]
```

Den Hash erfährst du vom Server-Admin.

---

## 7. Ducking Tab

Im Ducking Tab kann eingestellt werden ob bestimmte Audio-Quellen leiser gedreht werden sollen wenn du angefunkt wirst.

Für jede Option: **Button aktivieren** und den **Regler** nach Wunsch einstellen.

> Der Regler bestimmt die Stärke des Duckings: **oben = laut** (kein Ducking), **unten = stumm** (man hört niemanden mehr auf dieser Quelle).

### Verfügbare Optionen

| Option | Bedeutung |
|---|---|
| **Channel Ducking** | TS3-Kanalmitglieder werden leiser wenn du angefunkt wirst |
| **1XY.ab** | Alle anderen Frequenzen werden leiser wenn eine **Hunderter-Frequenz** dich anfunkt |
| **XY1.ab** | Alle anderen Frequenzen werden leiser wenn eine **Einer-Frequenz** dich anfunkt |
| **XYZ.1b** | Alle anderen Frequenzen werden leiser wenn eine **Zentel-Frequenz** dich anfunkt |

### Frequenz-Ziffer-Bezeichnungen

Für eine Frequenz **XYZ.ab** gilt:

| Stelle | Bedeutung |
|---|---|
| **X** | Bereichs- oder Funktionszuordnung |
| **Y** | Platzhalter für weitere Differenzierung (OL-, Bereichs- oder Funktionsebene) |
| **Z** | Staffelebene |
| **a** | Kommandoebene |
| **b** | Kommandogruppenebene |

> Änderungen im Ducking Tab werden **sofort gespeichert** – kein OK nötig.

---

## 8. Settings Tab

### Globale Hotkeys

Die globalen Hotkeys werden direkt hier im **Settings Tab** per HotKey-Button konfiguriert — siehe [Abschnitt 5](#5-hotkeys-einrichten) für die vollständige Übersicht.

### Audio-Einstellungen

| Einstellung | Bedeutung |
|---|---|
| **Play Start / End Beep** | Funk-Sounds beim Senden/Empfangen ein-/ausschalten |
| **Soundeffekt-Lautstärke** | Wie laut die Funk-Sounds sind (Schieberegler) |

### Weitere Einstellungen

| Einstellung | Bedeutung |
|---|---|
| **Activate Radio on Startup** | Schaltet Radios die beim Schließen des Fensters noch aktiv waren beim nächsten Öffnen automatisch wieder ein |
| **Forward Radio to Own Channel** | Eingehende Funksignale werden als Sprache in deinen TS3-Kanal weitergeleitet, sodass andere Kanalmitglieder den Funk mithören können |
| **Radio to Own Channel** | Sorgt dafür dass Kanalmitglieder mithören können was du selbst funkst |
| **Auf Updates prüfen** | Beim Plugin-Start (max. 1x pro Tag) wird geprüft ob eine neue Version verfügbar ist |
| **Jetzt prüfen** | Manueller Update-Check — zeigt sofort ob eine neue Version vorliegt |

### Update-Benachrichtigung

Wenn eine neue Version verfügbar ist, erscheint ein Dialog mit drei Optionen:

| Button | Funktion |
|---|---|
| **Herunterladen** | Öffnet die GitHub-Release-Seite im Browser zum Download der neuen `.ts3_plugin`-Datei |
| **Später** | Schließt den Dialog — die Frage erscheint frühestens am nächsten Tag wieder |
| **Diese Version überspringen** | Diese spezifische Version wird ignoriert, erst beim nächsten Release wird wieder gefragt |

> 🔒 Der Update-Check ruft nur die GitHub-API auf und überträgt keine persönlichen Daten. Er kann jederzeit über die Checkbox **Auf Updates prüfen** deaktiviert werden.

> Änderungen im Settings Tab werden **sofort gespeichert** – kein OK nötig.

---

## 9. Profiles Tab

Profile speichern deine komplette Radio-Konfiguration (Frequenzen, Passwörter, Namen, Lautstärken, Ducking) und lassen sich schnell wechseln.

### Profil erstellen

1. Tab **Profiles** öffnen
2. **Neu** klicken → Name eingeben → **OK**
3. Die aktuelle Konfiguration wird gespeichert

### Profil laden

Profil in der Liste **anklicken** → alle Einstellungen werden sofort übernommen.

### Profil löschen / umbenennen

Profil auswählen → **Löschen** oder **Umbenennen**

> 💡 Erstelle Profile für verschiedene Situationen, z.B. "Patrouille", "Basis", "Event".

### Profil exportieren

Mit **Export** lassen sich Profile als `.gsprofile`-Datei (JSON) speichern und an andere weitergeben.

1. **Export** klicken
2. Im Dialog die gewünschten **Profile** anhaken — pro Profil sind die einzelnen **Radios** (1–8) separat wählbar
3. Optional **Audio** (Pan, Volume, Ducking) und/oder **Passwörter** mit exportieren
4. **Verschlüsselung** wählen:
   - **Keine** — JSON ist klar lesbar
   - **Nur Passwörter verschlüsseln** — Profilnamen und Frequenzen sichtbar, Passwörter mit AES-256 geschützt
   - **Gesamte Datei verschlüsseln** — komplette Datei nur mit Passwort lesbar
5. Bei Verschlüsselung: Export-Passwort vergeben
6. Speicherort wählen → fertig

> 🔒 Die Verschlüsselung nutzt AES-256-CBC mit PBKDF2-SHA256 Key-Derivation (100.000 Iterationen). Ohne Passwort ist nichts entschlüsselbar.

### Profil importieren

1. **Import** klicken → `.gsprofile`-Datei wählen
2. Bei verschlüsselten Dateien: Passwort eingeben
3. Im Preview-Dialog erscheinen alle enthaltenen Profile mit ihren Radios und Frequenzen
4. **Ziel-Slot** pro Radio wählen — z.B. Radio 1 aus der Datei auf Slot 3 importieren
5. Bei Namenskollision: **Überschreiben**, **Umbenennen** oder **Überspringen**
6. **Audio** und **Passwörter** optional übernehmen (nur aktiv wenn in der Datei enthalten)
7. **Importieren** klicken

---

## 10. Buttons: OK / Abbrechen / Reset

| Button | Funktion |
|---|---|
| **OK** | Speichert alle Änderungen aus dem General Tab und schließt den Dialog |
| **Abbrechen** | Schließt den Dialog ohne Änderungen zu speichern |
| **Reset** | Setzt alle Radios zurück (Frequenzen auf 000.00, alles deaktiviert) – Dialog bleibt offen, erst OK speichert dauerhaft |

> **Hinweis:** Hotkeys, Ducking und Settings werden **sofort** gespeichert, unabhängig von OK/Abbrechen.

---

## 11. Update & Deinstallation

### Plugin aktualisieren

1. TeamSpeak 3 **schließen**
2. Doppelklick auf die neue `.ts3_plugin`-Datei
3. TS3 öffnet sich und fragt nach Bestätigung → **Installieren**
4. TS3 neu starten

> Die alten Dateien werden automatisch überschrieben. Deine Einstellungen (Frequenzen, Hotkeys, Profile) bleiben erhalten.

### Plugin deinstallieren

> ⚠️ Der „Deinstallieren"-Button in TS3 funktioniert nur bei Plugins die direkt aus dem offiziellen TS3-Marketplace stammen. Bei manuell installierten `.ts3_plugin`-Dateien muss die Deinstallation manuell erfolgen.

1. TeamSpeak 3 **schließen**
2. Den Windows Explorer öffnen und folgende Dateien/Ordner löschen:

```
%APPDATA%\TS3Client\plugins\gs_comms_win64.dll
%APPDATA%\TS3Client\plugins\gs_comms\
```

3. TS3 neu starten

> 💡 `%APPDATA%` in die Adressleiste des Explorers eingeben — Windows öffnet automatisch den richtigen Ordner.

---

## 12. Häufige Fragen

**Ich höre niemanden obwohl wir auf derselben Frequenz sind.**
→ Prüfe ob das Radio eingeschaltet ist und die Frequenz exakt übereinstimmt (`118.50` ≠ `118.5`).

**Ich kann die Frequenz nicht ändern.**
→ Das Radio muss erst mit dem Toggle **ausgeschaltet** werden, dann ist das Frequenzfeld wieder editierbar.

**Die ▲ ▼ Pfeile reagieren nicht auf Klicks.**
→ Das sind keine Buttons – sie sind reine Statusanzeigen (Senden/Empfangen).

**Mein Hotkey funktioniert nicht.**
→ Stelle sicher dass das Radio eingeschaltet ist und eine Frequenz gesetzt hat (nicht `000.00`).

**Ich höre jemanden aber er/sie hört mich nicht.**
→ Die Frequenz muss auf beiden Seiten identisch sein. Prüfe auch ob ein Passwort gesetzt ist.

**Die Funk-Sounds nerven.**
→ Settings Tab → **Play Start / End Beep** deaktivieren oder **Soundeffekt-Lautstärke** runterdrehen.

**Was macht Doppelklick auf Balance- oder Lautstärke-Regler?**
→ Setzt den Wert auf den Standard zurück (Balance = Mitte, Lautstärke = 1.0x).

---

## 13. Hinweis für Server-Admins

Damit das Plugin korrekt funktioniert müssen folgende **TeamSpeak-Rechte** auf dem Server gesetzt sein:

| Recht | Bedeutung |
|---|---|
| `i_client_whisper_power` | Erlaubt dem Client andere Clients anzuflüstern (Funksignal senden) |
| `i_client_needed_whisper_power` | Legt fest welche Whisper-Power ein Client benötigt um empfangen zu werden |

> ⚠️ Sind diese Rechte nicht korrekt gesetzt können Nutzer zwar auf einer Frequenz senden, andere hören jedoch nichts.

---


## 14. Third-Party-Lizenzen

Dieses Plugin enthält unmodifizierte Bibliotheken Dritter, deren Lizenzen weiterhin gelten:

| Komponente | Lizenz | Hinweis |
|---|---|---|
| **Qt 6.7.3** (`Qt6Core`, `Qt6Gui`, `Qt6Widgets`, `Qt6Network`, `Qt6Multimedia`) | LGPLv3 | © The Qt Company Ltd. — [Qt Source](https://download.qt.io/archive/qt/6.7/6.7.3/single/qt-everywhere-src-6.7.3.tar.xz) |
| **TeamSpeak 3 Plugin SDK** | TeamSpeak Lizenz | © TeamSpeak Systems GmbH |
| **Windows BCrypt API** | Microsoft Windows | Systembibliothek |

Qt wird **dynamisch gelinkt** (DLLs liegen separat im Plugin-Ordner) und ist somit unter LGPLv3 austauschbar. Die vollständigen Lizenz-Texte liegen dem Plugin-Paket als `THIRD_PARTY_LICENSES.txt` bei.

---

*Sin Inc. Comms v1.7.5 – by GameStreakerDE*
*© 2026 Daniel Meyer (GameStreakerDE) – Alle Rechte vorbehalten. Unbefugtes Kopieren oder Weitergeben ist untersagt.*
