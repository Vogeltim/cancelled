[README.md](https://github.com/user-attachments/files/31756686/README.md)
# Angela – Deine persönliche KI-Assistentin 🤖✨

Angela ist eine Windows-Desktop-App (Electron), mit der du **reden**, **Aufgaben erledigen** und mehr kannst – auf Deutsch, mit Sprachausgabe und Sprachsteuerung.

![Angela](assets/icon.svg)

## Features

- 💬 **Chatten** – Schreibe oder **spreche** mit Angela (Mikrofon-Button 🎤)
- 🔴 **Live-Modus** – durchgehend freihändig sprechen wie bei Gemini Live („beenden“ stoppt)
- 🔊 **Sprachausgabe** – Angela antwortet per Stimme (deutsche Stimme)
- 🎙️ **Offline-Erkennung** – deine Stimme wird lokal erkannt (whisper), ganz ohne Cloud & Limits
- ⏱️ **Timer & Erinnerungen** – „timer 5 minuten", „erinnere mich in 10 minuten an Pause"
- 📝 **Notizen & ✅ To-dos** – dauerhaft gespeichert
- 🌤️ **Wetter** – live, für deine Stadt oder jede beliebige Stadt
- 📚 **Wissen** – Wikipedia-Zusammenfassungen zu jedem Thema
- 🧮 **Rechnen** – „was ist 12 x 7 + 3", „20% von 80", „wurzel aus 144"
- 🌐 **Webseiten öffnen** – „öffne youtube", „öffne github"
- 🚀 **ALLE installierten Apps starten** – „öffne rechner", "öffne discord", "öffne photoshop" – Angela findet jedes Programm & jede UWP-App auf dem PC (mit Vorschlägen bei Tippfehlern)
- 🎵 **Musik & Videos** – "spiel musik von rick astley" → Angela sucht auf YouTube, spielt in einem eigenen Fenster ab, "stopp musik" beendet
- 🎮 **Game-Companion** – erkennt automatisch, wenn du Roblox, Minecraft, Fortnite u.a. spielst: "ich spiele?", "spielzeit" (Pausen-Erinnerung ab 1h), "spiele roblox" startet das Spiel
- 🔎 **Websuche** – „suche katzen bilder"
- 🕐 **Uhrzeit/Datum**, 😄 **Witze**, 🎲 **Würfeln**, 🪙 **Münzwurf**
- 🧠 **Optional: Echter KI-Chatmodus** (ChatGPT-kompatible API) in den Einstellungen ⚙️

## Schnellstart (Entwicklung)

```bash
npm install
npm start
```

> Beim ersten Start fragt Windows ggf. die Firewall – das ist normal (Wetter/Wikipedia).

## Angela.exe bauen

```bash
npm install
npm run dist          # portable Angela.exe  ->  release/Angela.exe
npm run dist:installer  # optional: Installer (Angela-Setup.exe)
```

Die fertige **Angela.exe** liegt danach im Ordner `release/` – einfach doppelklicken, keine Installation nötig. **Alt+Shift+A** zeigt/versteckt Angela aus jedem Programm.

## Beispiele zum Ausprobieren

| Du sagst | Angela tut |
|---|---|
| „hallo" | Begrüßt dich mit Namen (wenn du „ich heiße Max" gesagt hast) |
| „timer 5 minuten" | Startet einen Timer + Signalton |
| „erinnere mich in 10 minuten an Pause" | Erinnerung mit Sprachausgabe |
| „notiere: Milch kaufen" | Speichert die Notiz dauerhaft |
| „aufgabe: Bericht schreiben" | Fügt To-do hinzu |
| „aufgabe bericht erledigt" | Hakt die Aufgabe ab |
| „wie wird das wetter" | Live-Wetter für deinen Standort |
| „wetter in hamburg" | Wetter für Hamburg |
| „was ist ein quasar" | Wikipedia-Erklärung |
| „was ist 12 x 7 + 3" | 87 🧮 |
| „öffne youtube" | Browser mit YouTube |
| "spiel musik von rick astley" | Sucht das Video auf YouTube & spielt es ab ("stopp musik" stoppt) |
| "spiele roblox" | Startet Roblox (oder ein anderes installiertes Spiel) |
| "ich spiele" / "spielzeit" | Game-Companion erkennt das Spiel & misst die Spielzeit |
| „öffne rechner" | Windows-Rechner |
| "öffne discord" | Startet die Discord-App (falls installiert, sonst Web) |
| „erzähl einen witz" | Einen Witz 😄 |

## KI-Chatmodus – gratis & unbegrenzt 🎉

Standardmäßig läuft Angela **komplett offline** mit allen Skills. Für echte (freie) Gespräche:

1. ⚙️ Einstellungen öffnen
2. **KI-Chatmodus** aktivieren
3. Anbieter wählen:

| Anbieter | Kosten | Limits | API-Key |
|---|---|---|---|
| **Ollama** (lokal) | ⭐ **100% gratis** | **unbegrenzt** | ❌ nein |
| **Groq** | kostenlos | begrenzt (ratenlimit) | ✅ ja (gratis-Key) |
| **Google Gemini** | kostenlos | begrenzt | ✅ ja (gratis-Key) |
| **OpenAI** | kostenpflichtig | gut | ✅ ja |
| **Eigene API** | variabel | variabel | ✅ ja |

**Empfohlen: Ollama** – läuft direkt auf deinem PC, braucht weder Internet noch API-Key und hat keine Nutzungslimits. Setze es so auf:

```bash
# 1) Ollama installieren:  https://ollama.com
# 2) Ein Modell holen (z.B. Llama 3.2):
ollama run llama3.2
# 3) In Angelas Einstellungen: Anbieter = Ollama, dann „Modelle laden“ klicken
```

Fertig – Angela chattet jetzt frei & unbegrenzt. Skills wie Timer, Wetter und Notizen laufen weiterhin lokal (schneller & offline).

## Bedienung

- **Alt+Shift+A** – Angela ein-/ausblenden (global, aus jedem Programm)
- **✕** – Angela in den System-Tray (läuft weiter, Timer klingeln weiter!)
- **⚙️** – Einstellungen (Sprachausgabe, KI-Modus)

## Spracheingabe – wie sie funktioniert 🎙️

Angela erkennt **deutsche Sprache vollständig lokal & offline** über `whisper-cli` (whisper.cpp). Kein Cloud-Dienst, kein API-Key, keine Limits – deine Stimme verlässt den PC nie.

- **🎤 Mikrofon-Button:** klicken → einmal sprechen → Angela versteht und antwortet.
- **🔴 Live-Modus:** klicken → durchgehend zuhören. Sprich einfach, Angela antwortet, und lauscht direkt weiter. **„beenden“** stoppt.
- Beim ersten Klick fordert Windows den **Mikrofon-Zugriff** an → **„Zulassen“** klicken. Falls es fehlschlägt: Windows → Einstellungen → Datenschutz → Mikrofon → „Desktop-Apps“ erlauben.

> **Hinweis:** In der Browser-Vorschau (ohne Electron) ist die Offline-Erkennung nicht verfügbar; dort fällt Angela auf die Cloud-Spracherkennung des Browsers zurück.

## Technik

- Electron 33, kein Framework – reines HTML/CSS/JS
- `main.js` – Fenster, Tray, sichere IPC-Skills (Apps, Dateisuche, Netz) + Mikrofon-Berechtigung
- `preload.js` – sichere Brücke (contextIsolation)
- `skills.js` – alle deutschen Befehle (Regex-basiert)
- `brain.js` – Skill-Dispatcher + optionaler LLM-Modus
- `renderer.js` – Chat-UI, Sprachausgabe/-eingabe, Einstellungen
- `voice-capture.js` – Mikrofon-Aufnahme mit Sprachaktivitäts-Erkennung (VAD)
- `stt.js` – lokale Spracherkennung (whisper-cli) im Main-Prozess
- `yt-search.js` – YouTube-Suche ohne API-Key (parst die Ergebnisseite)
- `app-index.js` – indexiert alle installierten Apps (Get-StartApps, Startmenü) mit Fuzzy-Suche
- `bin/` + `models/` – gebündelte whisper.cpp-Binaries & Modell (deutsch)
- Speicher: `%APPDATA%/angela-ai-assistant/angela-memory.json`

## Lizenz

MIT
