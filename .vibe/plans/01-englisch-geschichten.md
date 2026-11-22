---
# Read by the hooks, the review, the evals. Schema: @lernapps/tooling/guidance/plan-front-matter.v1.schema.json
# Written by `lernapps plan` and the hooks. Never change a key or a value by hand.
# Archetype, null until chosen in Explore. Allowed values: explainer, interactive, quiz.
archetype: explainer
# Current phase. Allowed values: explore, plan, code, commit.
phase: commit
# prePushFailures: failed pre-push runs, written by the hook.
prePushFailures: 1
# failedChecks: failed rules and runs, written by lernapps check and the hooks.
failedChecks: { checks-pass: 7, plan-file: 1 }
---

# Plan: englisch-geschichten, first version

<!--
For you, the assistant. The process is in AGENTS.md; this plan holds the method.
- `npx --no -- lernapps plan next` prints the task to do now, `plan done` ticks it and prints the next one.
- You write only below Goal, Key decisions, Notes, Answers, Entry draft, Content method and Retrospective, in the
  creator's language. Delete the comment of a section once the section is filled.
- Work on the branch `work`, locally: push nothing before Commit.
-->

*Started 2026-11-21. Explore, Plan, Code, Commit.*

## Goal

Kinder der Stufe 5-6 lesen kurze Geschichten, füllen die story map (who, where, when, what) und hängen die Ereignisse an den story mountain (beginning, build-up, climax, ending). Sie fassen zusammen und erzählen nach, beschreiben Bilder und Bildfolgen, schreiben und setzen Geschichten fort, führen ein Tagebuch, schreiben einen Dialog und tragen Reime vor.

## Key decisions

- Archetype `explainer`, Einheiten-App (`subject: englisch`): Die Kinder brauchen Seiten mit Text, Bild und Übungen (Berg und Map werden gezeichnet, nicht gespielt); Bausteine aus den Strängen `texte` und `wortschatz`. Kein `interactive`: Berg und Map sind feste Zeichnungen, geübt wird mit Auswahl, Ordnen, Schreiben, Diktat und Sprechen.
- Auftrag fest durch Issue lernapps/apps#479 (Ersteller:in bringt die Didaktik, keine eigenen Texte); dieser Lauf baut nur Stufe 5-6, vier Kapitel, Kapitel 5 später als Inkrement.
- Hauptfigur Sophie statt „Lena“, kein „Josh“ (Konventionen, Abschnitt 7).
- Neuer Ort (im Plan-Checkpoint gemeldet): die **Geschichtenecke** im Klassenzimmer mit dem Wandbild „Geschichtenberg“ (Berg mit vier Stationen) und der Karte „story map“ daneben. Zeit: die „Geschichtenwoche“ im Januar, am Freitag liest die Klasse einander vor.
- Aussprache ohne Lesehilfe in deutscher Annäherung (Abweichung von Konventionen §4, (guess)): die App übt Erzählen, nicht neue Wörter; Hörsätze und Nachsprechen zeigen die Aussprache.
- `scope` in `src/app.yaml` und auf jeder Seite: ja, weil die App offene Aufgaben (`open-task`) hat; der Tutor beurteilt freie Texte nach dem `scope`.
- Verbindungswörter (`verbindungswoerter-erzaehlen`) stehen als erste Seite von Kapitel 2, weil `bildergeschichte` sie braucht (prerequisites-in-order); Kapitel 1 nennt nur die Stationen des Berges. (guess)

## Notes

- Fach Englisch, Einheiten-App (Stränge `texte`, `wortschatz`), Stufe 5-6 (Klasse 5-6, erstes bis zweites Lernjahr). Karte `https://lernapps.net/apps/map/englisch.json`, alle elf Bausteine dieser Stufe sind Lücken (`practisedBy` leer).
- Kapitel und Seiten (Karten-Ids):
  1. `was-passiert` („Was passiert in der Geschichte?“): Wiederholung `recap` simple-past; `figuren-ort-handlung` (Musterseite), `zusammenfassung`, `nacherzaehlen`.
  2. `bilder-erzaehlen`: Wiederholung `recap` there-is-are, present-progressive, praepositionen-ort; `verbindungswoerter-erzaehlen`, `bild-beschreiben`, `bildergeschichte`.
  3. `selbst-erzaehlen`: `geschichte-erzaehlen`, `geschichte-fortsetzen`, `tagebucheintrag`.
  4. `spielen-und-reimen`: `dialog-schreiben`, `gedichte-reime`.
  Kapitel 5 (`perspektive-wechseln`, `setting-atmosphaere`, Stufe 7-8) bleibt außen vor.
- Von außen: simple-past (#472), there-is-are (#473), present-progressive (#472), praepositionen-ort (#475). Kapitel 1 wiederholt simple-past, Kapitel 2 die drei anderen.
- Didaktik: Berg und Map tragen alles. Lesen: Map füllen, Ereignisse an den Berg hängen. Schreiben: erst Berg planen, dann schreiben (Richtung umgekehrt). Verbindungswörter sind Wegweiser (first, then, suddenly, finally). Kapitel 4: aus einer Station wird ein Dialog; bei Reimen Reimwörter sammeln, Rhythmus klatschen.
- Wie die Kinder dorthin kommen: sie leiten ab (Map aus dem Text füllen, Berg ordnen, Stationen finden), nicht nur lesen. Fehlerbilder: Details mit dem Wichtigen verwechseln (Zusammenfassung), Wort für Wort übersetzen statt nacherzählen, Stationen vertauschen, Present statt Past beim Erzählen, `suddenly` als Anfang, Dialog ohne Sprecher oder mit Erzähltext, Reim nach Schreibung statt Klang.
- Je Baustein, wie Kinder dorthin kommen und was die Rückmeldung abfängt:
  - `figuren-ort-handlung`: Sie lesen eine Geschichte und ziehen who/where/when/what aus ihr in die Map; Rückmeldung fängt: Ort und Zeit vertauschen, Nebendinge statt Hauptfigur, Handlung mit Gefühl verwechseln.
  - `zusammenfassung`: Sie streichen Nebendinge und behalten, was am Berg hängt; Rückmeldung fängt: zu viele Einzelheiten, eigene Meinung statt Inhalt, Sätze wörtlich übernehmen.
  - `nacherzaehlen`: Sie gehen den Berg Station für Station ab und erzählen in eigenen Worten im simple past; Rückmeldung fängt: present statt past, Station vergessen, Stationen vertauscht.
  - `verbindungswoerter-erzaehlen`: Sie setzen Wegweiser an die Stationen (first, then, after that, suddenly, finally) und ordnen Sätze; Rückmeldung fängt: suddenly am Anfang, finally in der Mitte, then ohne Komma-Zwang (kein Satzzeichenfehler gewertet).
  - `bild-beschreiben`: Sie lesen das Raster (foreground, background, on the left, on the right, in the middle) und beschreiben Felder; Rückmeldung fängt: in/on/at-Verwechslung, is/are bei there, simple present statt present progressive für Handlungen im Bild.
  - `bildergeschichte`: Jedes Bild ist eine Station; sie verbinden Bildsätze mit Wegweisern und schreiben im simple past; Rückmeldung fängt: present statt past, Bilder nur aufgezählt ohne Wegweiser.
  - `geschichte-erzaehlen`: Sie planen erst den Berg (Cue-Zeilen), dann schreiben sie je Station einen Satz; Rückmeldung fängt: Anfang ohne who/where, Höhepunkt fehlt, Ende offen.
  - `geschichte-fortsetzen`: Sie hängen einen zweiten Gipfel an oder wählen ein anderes Ende; Rückmeldung fängt: Fortsetzung wiederholt das Ende, Figuren wechseln, Zeit springt.
  - `tagebucheintrag`: Sie machen aus einem Tag einen kleinen Berg (Morgen, Mittag, Höhepunkt, Abend) und schreiben `Dear diary` im simple past; Rückmeldung fängt: Datum/Anrede vergessen, present statt past, nur Aufzählung.
  - `dialog-schreiben`: Aus einer Station wird ein Dialog; Sie ordnen Sprecher und Sätze; Rückmeldung fängt: Sprecher fehlt, Erzähltext im Dialog, Anführungszeichen statt Sprecher-Zeile (Skriptform: „Sophie: …“).
  - `gedichte-reime`: Sie sortieren Reimwörter nach Klang und klatschen den Rhythmus mit; Rückmeldung fängt: Reim nach Schreibung statt Klang (cat–hat ja, one–phone nein), Stummreim ohne Betonung.
- Umfang: drin: alle elf Bausteine der Stufe 5-6, deutsche Erklärtexte, englische Geschichten von höchstens etwa 80 Wörtern (simple past), Diktat und Nachsprechen mit `bf_emma`, freies Schreiben als `open-task`. Draußen: Sicht der Figur und Stimmung (Kapitel 5), Kurzgeschichten- und Gedichtanalyse (#483), Berichte (#486), Zeitformen selbst (#472). Die App bewertet nicht, wie jemand spricht, und keine freien Texte.
- Quellen: Fakten zu story mountain / story map nur als Idee aus dem Unterricht (keine Sätze übernommen); alle Geschichten, Dialoge und Reime sind eigene Texte (CC BY 4.0). Der Reim-Teil nennt zusätzlich nur Fakten (Reim = gleicher Klang am Ende), keine fremden Gedichte. Alle Zeichnungen eigen, Figuren aus `millbrook-klassenzimmer.svg` (#470).
- Geprüft: Karte (`englisch.json`, gelesen, Bausteine und `requires` oben), Grundwortschatz-Seite (erreichbar, Wortliste prüfe ich per Skript im Code), Muster der Vorgänger-Repositories (`englisch-zeiten`, `englisch-saetze-verbinden`, `englisch-adjektive-adverbien`, `hello-millbrook`). Nicht geprüft: Wikipedia „Narrative structure“ und „Freytag's pyramid“ (die Abfrage lieferte keinen Text), kein Klexikon-Artikel; der story mountain wird deshalb nur als Unterrichtsbild aus dem Auftrag benutzt, ohne Quellenzitat.
- Geprüft und behoben an der Musterseite `figuren-ort-handlung` (Lerner-Check durch einen Sub-Agenten als Kind Klasse 5, Sprachprüfung Englisch/Deutsch durch einen Sub-Agenten, Prüfung durch die Orchestrator-Session):
  - Lerner-Check, Funde: Bildunterschrift der Szene erklärte nicht, was an der Wand hängt (ergänzt); Map zeigte nicht alle Figuren (a girl ergänzt); Schreibaufgabe wiederholte die Lösung der Ordnungsaufgabe darüber (neue Geschichte und Cues); Merke und Map-Eintrag nicht gleich (angeglichen); Lösung der offenen Aufgabe nannte Wörter, die niemand kannte (einfacher). Von der Vorlage, nicht geändert: generische Meldung „Deine Fassung kann trotzdem richtig sein“, Hinweise zu Groß-/Kleinschreibung bei `punctuation: ok`, `ordering` ohne Hinweis auf die falsche Stelle, KI-Tutor-Leiste oben.
  - Sprachprüfung, Funde: Figuren als „Personen“ (jetzt Personen oder Tiere), „Inside“ mehrdeutig, Ort und Dinge der Übungsgeschichte unklar, „story mountain“ fehlte, Zielantworten zu eng, falscher Intonationshinweis, Kasus („einen Film“), „erzählt wird“, Wörter stick und suddenly (nach Prüfung gegen die Wortliste A1/A2: bekannt, nicht in die Tabelle).
  - Prüfung der Orchestrator-Session, Funde: Notes, Inhaltsführer (Platzhalter, Wortliste), `when` nicht geübt, Zuordnung wiederholte den Text, Textmenge, Wörtertabelle zu lang, Schreibaufgabe prüft nur die Zeitform, Ordnungsaufgabe ohne Erklärung der Stationen, zwei Kisten, längste Option richtig, Musterlösung wie Beispielgeschichte, Fähnchenzahlen zu klein. Alle behoben (eigene Aufgabe zu `when`, Einzelauswahl zu climax/ending, Tabelle auf sechs Wörter, Schriftgröße 16).
  - Skripte: `.agents/skills/app-content/scripts/pruefen.py` (Hörsätze gegen den Text derselben Seite, Wörter gegen die Liste), `woerter-erklaert.json`.
- Gesamtcheck der fertigen App (Sub-Agent als Kind Klasse 5, 360 und 1280 px, alle 13 Seiten in der Reihenfolge) und Sprachprüfung Englisch/Deutsch (zwei Sub-Agenten, je Kapitel 1-2 und 3-4):
  - Funde (Auswahl) und Behebung: Mrs Parker, Alter, Herkunft und Schule nur auf der Startseite, jetzt auf der ersten Lernseite (`das-brauchst-du`) eingeführt; „Station“ und „Klassenzimmer-Poster“ erklärt, „Cue“ → „Hinweis“, „Baustein“ weg; Schneemann-Geschichte stand auf drei Seiten, „Suddenly all the lights went out“ auf zwei, Katze auf vier: je nur noch eine Seite; „Sophie · her dog Amir“ (Hund hieß wie der Mitschüler) → Bella; Sophies zwei Donnerstagsgeschichten hängen jetzt zusammen (Drachen-Geschichte, Fortsetzung auf der nächsten Seite); neue Kindernamen (Lena, Bo, Kim, Joe, Mia, Tara, Ben, Nora, Dennis, Lara, Zara, Sam) durch die bekannten Figuren ersetzt; Wegweiser-Regel widerspruchsfrei (then und after that in der Mitte, suddenly leitet den climax ein, überall gleiche Reihenfolge); „drei Sätze“ und „vier Stationen“ geklärt, „Hauptereignisse“; falsche Zielantworten (eats the cake all, his/a), zu enge Zielgruppen (a bus, Amir's bag, on the beach, my mother …) und falsche Meldungen („Vor cake fehlt a“) korrigiert; unregelmäßige Formen der App auf der Wiederholungsseite; Skript-Szene (Garten, Fuchs, Regieanweisung) und Reimkarte, Rasterbilder bei 360 px lesbar; Reim-Aussagen geprüft, ein Vers ohne Reim ersetzt; Hörsätze mit einsilbigem Ende ersetzt (zweisilbig).
  - Nicht behoben: Brillen und Zöpfe der Bildfolgen sind bei 360 px klein; Berg-Fähnchen auf den Wandbildern sind nur nummeriert; generische Vorlagenmeldung „Deine Fassung kann trotzdem richtig sein“, Hinweise zu Groß-/Kleinschreibung bei `punctuation: ok`, `ordering` ohne Hinweis auf die falsche Stelle, `mistakes` im Modus `choice` unsichtbar, KI-Tutor-Leiste oben; kein Hörtest der MP3 (die Reimverse hört die Ersteller:in).
- Wörter: Grundwortschatz A1/A2 (https://lernapps.net/apps/map/englisch/grundwortschatz/); Ausnahmen stehen auf der Seite erklärt und im Inhaltsführer.

## Explore

<!--
- Find out what the app teaches, for whom, how much and how it looks. Ask; write no code, run no `create`.
- An answer counts only in the creator's words under "Answers". At most 2 questions per message, one topic each.
-->

### Tasks

- [x] Check the start: the folder `.agents/skills/lernapps-app` exists (else stop and tell the creator that the folder
      was not started with `init`), and `git branch --show-current` prints `work` (else `git switch -c work`).
- [x] Load skill `lernapps-app`. Tell the creator in two sentences what a lernapps app is and where it will live: at
      their own address, free and public, and once listed as a copy on lernapps.net. Say that the technical part
      (GitHub) comes at the end and that you do it.
- [x] Interview: ask the topics "Goal" and "Learners" of "Answers".
- [x] Load skill `lernapps-map-assignment` and read the learning map of the subject as it says. The creator brings
      the content themselves (material, a word list, the pages): note under "Notes" which competencies of the map it
      covers. Else write the skill's assignment, with its story; the creator's yes answers the topics Content and
      Amount. A subject without a map: skip this task and say so.
- [x] Load skill `lernapps-exercise-patterns` and read its reference for the subject. Note under "Notes" how learners
      will practise what the goal names.
- [x] Choose the archetype as skill `lernapps-app` says: read the README of each archetype in question, then tell the
      creator in plain words what the chosen one can and cannot do. Write the archetype and its reason under "Key
      decisions".
- [x] Run `npx --no -- lernapps skills --archetype <name>` with the chosen archetype. It installs the archetype's
      skills and adds the archetype's tasks to this plan.
- [x] Load skill `lernapps-explainer-design`. An explainer has the look of the runtime: write "fixed by the
      archetype" under the topic "Look and feel" of "Answers".
- [x] Interview: ask every other topic of "Answers", in order. Leave out only a topic that an answer of the creator
      already covers, and note which answer. A topic nobody answered is asked once before you write an assumption
      with "(guess)".
- [x] Load skill `lernapps-content-research` and research as it says. Write under "Notes": the strand or subject, the
      competencies by chapter with their ids, the sources you opened.
- [x] Write under "Notes" which competency goes on which page and which pages form a chapter, as "Map the content" of
      skill `lernapps-explainer-design` says. Per page, name the prerequisites the app does not practise.
- [x] Write under "Notes", one line per competency: how learners get there (they derive it, they do not only read it
      off), and which misconception the feedback catches.
- [x] Write under "Notes" the scope: what is in, what is out and why, the data range (for example "all main-group
      elements", never a silent "1–20"), the languages.
- [x] **Checkpoint:** research. Show in plain words: the strand or why none, the competencies by chapter, the didactic
      approach, the scope, every "(guess)", the sources and what is unchecked, the archetype and its reason. Stop and
      wait. Changes: change them, then ask again.
      Creator: Ja, Plan-Phase. Karten-Ids als competencies, Wiederholungsseiten ohne; Reime nach Schreibung und Muster, Klang nur über Nachsprechen, Hörliste in Notes; offene Aufgaben mit points und Musterlösung; Seitenlänge nach Abschnitt 7.

### Answers

<!-- The interview: per topic the creator's answer, in their words. Keep the topics. -->

Alle Antworten aus dem Auftrag (Issue #479, Epic #489, Konventionen) in den Worten der Ersteller:in; offen bleibende Punkte „(guess)“ unter Key decisions.

- Goal: „Ich kann einer Geschichte entnehmen, wer, wo, wann und was, sie wiedergeben und selbst Geschichten erzählen, spielen und weiterschreiben.“ (Issue #479, Leitidee)
- Learners: Englisch, Stufe 5-6 (Klasse 5-6); Vorwissen aus #470, #471, #472, #473, #475, #476 (Startnachricht, Konventionen 1).
- Model and focus: die fertigen Vorgänger (`englisch-zeiten`, `englisch-saetze-verbinden`, `englisch-adjektive-adverbien` …); Schwerpunkt Seitenaufbau und Begriffe wie dort (Startnachricht). Der story mountain mit der story map trägt den Explainer.
- Hurdles: nicht genannt; aus der Didaktik des Issues: Zusammenfassen statt Abschreiben, Berg vor dem Schreiben planen.
- Content: „die Geschichten selbst schreibst du eigen (keine übernommenen Texte)“, Lizenzen und Quellen im Inhaltsführer (Startnachricht). Kein Material der Ersteller:in.
- Amount: Stufe 5-6, Kapitel 1 bis 4; Kapitel 5 später als Inkrement (Startnachricht).
- Languages: Deutsch mit englischen Beispielen (Konventionen 4).
- Look and feel: fixed by the archetype; Szenen gezeichnet, eine je Seite wie die Vorgänger (Konventionen 2).
- Terms: story mountain (beginning, build-up, climax, ending), story map (who, where, when, what), Wegweiser (first, then, suddenly, finally); Sophie, Ellie, Peter, Amir, Mr Hill, Mrs Parker (Startnachricht).
- Finding the app: nicht gefragt (guess): „Englisch Geschichten schreiben und nacherzählen, Klasse 5 und 6“.

## Plan

<!--
- Map the confirmed content onto the archetype. No new content questions: a gap in the content goes back to Explore.
- The creator confirms the plan in one read. After the yes you work on your own.
-->

### Tasks

- [x] Map the content as "Map the content" of skill `lernapps-explainer-design` says, and write the result under
      "Content method".
- [x] Choose a pattern per competency as skill `lernapps-exercise-patterns` says, and add it to "Content method".
- [x] Add to "Content method" one line per page, as "Engagement" of skill `lernapps-explainer-design` says: the
      opening task, the change of activity, the reward, the story.
- [x] Add the tasks of Code, each one a piece of work that ends in a commit. First the pattern: one complete page or
      screen, `npx --no -- lernapps plan add --at pattern "<task>"`. Then the others, one call each:
      `npx --no -- lernapps plan add --at pages "<task>"`. Each task says what it builds and what it shows.
- [x] Draw a sketch of each screen, component or interactive exercise: a static SVG or image, or the steps with what
      learners see after each. Keep the files in `.vibe/sketches/`.
- [x] Show the creator, short: goal, competencies by chapter, the Code tasks, the sketches, and the content method in
      plain words (what learners see and do, what the app cannot do). At most 2 questions.
- [x] **Checkpoint:** confirm the plan and the content method. Stop and wait for an explicit yes. Changes: change
      them, then ask again.
      Creator: Orchestrator-Session (in der Rolle der Ersteller:in): Ja, Plan bestätigt. Bedingungen: Beispielgeschichte nie die der Übungen, Berg/Map-Figur nicht dieselben Ereignisse wie die erste Aufgabe; Reimseite erst nach Hörprobe, Hörliste an die Ersteller:in; offene Aufgaben mit points, Musterlösung und Hinweis, dass die App den Text nicht bewertet; höchstens eine kurze Wörtertabelle; Lerner-Check mit Sub-Agent und Sprachprüfung vor dem Checkpoint Musterseite.

### Content method

<!-- One line each: the patterns and where; the figures and how they are made; the data files; each component, what it
checks and what it cannot; how a later agent adds a chapter. It becomes the content guide in Code. -->
<!-- An explainer: per figure, model and component its learning action in two to four sentences
(`explainer-representation-explained`); per page its prerequisites the app does not practise, and which get a recap
page, which a link. -->

- **Aufbau:** `src/app.yaml` (Format 2, `subject: englisch`, `chapters: [was-passiert, bilder-erzaehlen, selbst-erzaehlen, spielen-und-reimen]`), je Kapitel `src/<kapitel>/chapter.yaml` und Seiten `src/<kapitel>/<seite>.yaml`, Bilder `src/images/`, Audio `src/audio/`. Keine Datendateien, keine Komponenten (`prefer-built-in-block`: Berg und Map sind Zeichnungen, geübt wird mit Standardbausteinen; ein Ziehen der Karten wäre ein Wunsch für ein Inkrement). Je Seite eine Karten-Id in `competencies:`; die Wiederholungsseiten (`das-brauchst-du`, `recap: [englisch/…]`) haben keine.
- **Voraussetzungen, die die App nicht übt:** Kapitel 1 `das-brauchst-du` (Wiederholungsseite, ohne Übung) für `englisch/simple-past` (gebraucht von `nacherzaehlen`, auch `geschichte-erzaehlen`, `tagebucheintrag`, `bildergeschichte`). Kapitel 2 `das-brauchst-du` für `englisch/there-is-are`, `englisch/present-progressive`, `englisch/praepositionen-ort` (gebraucht von `bild-beschreiben`). Die anderen `requires` (bild-beschreiben, verbindungswoerter-erzaehlen, geschichte-erzaehlen) sind Seiten der App und stehen früher.
- **Seiten, gleiche Abschnitts-IDs** (Titel sagen, was der Abschnitt tut): `einstieg` (Szene als Bild, erste leichte Aufgabe, „Das kannst du danach“, höchstens eine kurze Wörtertabelle „Klassenzimmer-Poster · …“), `neu` (Berg- oder Map-Figur, Merke), `uebung` (mindestens vier Übungen, leicht → schwer), `anwenden` (`speaking-task` und `open-task` mit `points` und `solution`), `weiter` (nächster Schritt in der Geschichtenwoche; am Kapitelende Rückblick). Höchstens 350 Wörter Text, höchstens vier Textblöcke hintereinander, Bild oder Übung in den ersten vier Blöcken.
- **Geschichte der Seiten:** Geschichtenwoche im Januar in Mr Hills Klassenzimmer. Kapitel 1 = Montag: Mr Hill hängt in der Geschichtenecke den Geschichtenberg und die story map auf. Kapitel 2 = Dienstag und Mittwoch, Kapitel 3 = Donnerstag, Kapitel 4 = Freitag: Spielszene und Reim. Jede Seite endet mit dem nächsten Schritt. Die Texte der Kinder (Geschichten, Dialoge, Reime) sind eigene Texte; jede Seite hat ihre eigene kleine Geschichte (höchstens etwa 80 Wörter, simple past), die Beispielgeschichte im Text ist nie die der Übungen.
- **Figuren (Zeichnungen) und ihre Lernhandlung:**
  - Geschichtenberg (`geschichtenberg-<seite>.svg`): ein Berg mit vier Fähnchen (beginning, build-up, climax, ending); Gipfel = climax; Schilder first, then, suddenly, finally auf dem Weg. Die Kinder lesen daran ab, wo ein Ereignis hängt, und ordnen Ereignisse den Fähnchen zu. Er zeigt nie die Lösung einer Aufgabe der Seite.
  - Story map (`geschichtenmap-<seite>.svg`): vier Felder who (blau), where (grün), when (orange), what (rot); Farben nur dafür. Die Kinder tragen aus dem Text Figuren, Ort, Zeit und Handlung ein; das Beispiel der Figur ist eine andere Geschichte als die der Aufgabe.
  - Szenen `szene-<seite>.svg` mit den Figuren als `<g id>` aus hello-millbrook (`millbrook-klassenzimmer.svg`), gleich gelassen; `alt` sagt, was die Szene zeigt, nie die Lösung.
  - Bildfolge (Kapitel 2): drei bis vier eigene Strichzeichnungen ohne Text als Stationen des Berges; Raster für die Bildbeschreibung: 3 × 3 Felder (foreground/middle/background mal left/in the middle/right).
  - Alle Zeichnungen eigen, `CC-BY-4.0`, Hintergrund #f4efe2, Schrift mindestens 16 im 480er viewBox, alles innerhalb des viewBox. Ein kleines Skript im Scratchpad erzeugt sie (liegt nicht im Repository); die SVG-Dateien sind die Quelle. Skizzen in `.vibe/sketches/`.
- **Muster (Übungen), je Baustein:**
  - `figuren-ort-handlung`: Map füllen (`matching` Frage ↔ Feld, `language-task` choice), Berg-Station finden (`single-choice` mit `info`), Details der Map zuordnen (`multiple-choice`).
  - `zusammenfassung`: Wichtiges von Nebensachen trennen (`multiple-choice`), die beste Zusammenfassung wählen (`single-choice`), drei Sätze ordnen (`ordering`), kürzen (`language-task` write mit Cue).
  - `nacherzaehlen`: Stationen ordnen (`ordering`), Satz im simple past bilden (`language-task` write, `cue: "Amir · lose · bag · bus"`), Fehler suchen (present statt past).
  - `verbindungswoerter-erzaehlen`: Wegweiser setzen (`language-task` choice), Sätze ordnen (`ordering`), Wegweiser einer Station zuordnen (`matching`), Satz schreiben.
  - `bild-beschreiben`: Ort im Raster (`matching`), Lücke (`gap`) mit in/on/at, there is/are, present progressive, Satz mit Cue schreiben.
  - `bildergeschichte`: Bildsätze ordnen, mit Wegweisern verbinden (`language-task` write), Past-Form wählen.
  - `geschichte-erzaehlen`: Berg planen (Cue-Zeilen je Station), Sätze der Stationen schreiben, Anfang prüfen (who und where?).
  - `geschichte-fortsetzen`: zweiten Gipfel oder anderes Ende wählen (`single-choice` mit `info`), Fortsetzung schreiben mit Cue, Figuren-Treue prüfen.
  - `tagebucheintrag`: Tagesberg ordnen, Anrede und Datum setzen, Sätze im simple past schreiben.
  - `dialog-schreiben`: Sprecher zuordnen (`matching`), Zeilen ordnen, Skriptform („Sophie: …“) schreiben.
  - `gedichte-reime`: Reimpaare nach Schreibung und Muster zuordnen (`matching`), den Reim in einer Zeile wählen (`single-choice`), Verse ordnen, Verse nachsprechen. Auflage der Orchestrator-Session: Klang und Rhythmus lassen sich ohne Spracherkennung nicht prüfen; „klatschen“ ist eine Anleitung, kein geprüftes Ergebnis; nur ganze Verse als Audio; die Stimme bei cat/hat und light/night vorher anhören.
  - Je Seite ein anderer Satz an Übungsarten (`explainer-page-variety`); je Übung `mistakes` mit eigener Meldung und `hint`; gleichwertige Antworten als `(a|b)`; `punctuation: ok` bei richtigen Antworten, Kommas zählen nicht als Fehler; Auswahl nur mit echten Lernerfehlern; offene Aufgaben haben immer `points` und eine Musterlösung; Diktat und Nachsprechen immer mit neuen Sätzen.
- **Wörter:** Quelle der Wörter ist der Grundwortschatz Englisch (A1/A2, https://lernapps.net/apps/map/englisch/grundwortschatz/); ein Skript prüft alle englischen Inhaltswörter der Seiten gegen die Liste (Feld `vocabulary` der Karte); Wörter außerhalb (zum Beispiel climax, beginning, build-up, foreground, background, diary, summary) stehen auf der Seite erklärt und im Inhaltsführer.
- **Hörliste:** alle 66 Hörsätze (je Seite drei Diktat- und drei Nachsprechsätze, Namen am Satzende zweisilbig) stehen in `.agents/skills/app-content/scripts/audio-texte.json` (Datei → Satz); die frühe Liste dieses Plans wurde beim Bauen ersetzt.
  Vor dem Bau läuft ein Skript über alle Seiten, das jeden Hörsatz gegen Einstieg, Poster, Merke, Bildtext und Übungen derselben Seite prüft (Konventionen 7).
- **Engagement je Seite** (Eröffnung · Wechsel · Belohnung · Geschichte):
  - Alle Seiten: Eröffnung = eine leichte Aufgabe mit Begründung vor der Erklärung; Wechsel = Szene, Aufgabe, Figur, Merke, Übung (nie mehr als vier Textblöcke); Belohnung = nicht nur „Richtig“: das Fähnchen am Berg oder das Feld der Map füllt sich, am Kapitelende ein Rückblick auf alle Stationen; Wiederholung nur absichtlich (die Map kommt auf jeder Seite wieder, in anderer Aufgabe).
  - `figuren-ort-handlung`: Mr Hill hängt Berg und Map auf; die Kinder füllen die Map zu seiner Kurzgeschichte. `zusammenfassung`: Mr Hill gibt nur drei Zettel für die Wand. `nacherzaehlen`: Amir erzählt Ellie eine Geschichte nach, Sophie hört zu.
  - `verbindungswoerter-erzaehlen`: Peter hängt Schilder an den Berg. `bild-beschreiben`: ein Bild der Klasse hängt an der Geschichtenecke. `bildergeschichte`: vier Bilder werden vier Stationen.
  - `geschichte-erzaehlen`: Sophie plant ihren Berg. `geschichte-fortsetzen`: die Kinder bauen einen zweiten Gipfel an die Geschichte vom Montag. `tagebucheintrag`: Sophie schreibt am Abend ihren Tag auf.
  - `dialog-schreiben`: aus einer Station wird eine Spielszene für den Freitag. `gedichte-reime`: Mr Hill schließt die Woche mit einem Reim; Rückblick auf den ganzen Berg.
- **Prüfungen vor dem Pull-Request:** Skript für „keine Lösung im Text“ und Hörsätze, Wortliste, `lernapps check`, Gesamtcheck und Sprachprüfung durch Sub-Agenten.
- **Ein späterer Agent** ergänzt Kapitel 5 so: Baustein wählen, Seite mit denselben Abschnitten anlegen, die Map-Figur um „who mit Brille“ und „where mit Farbe“ erweitern, Hörsätze mit `regen_audio.py` erzeugen, Wörter prüfen, `lernapps check`.

## Code

<!--
- Build the app, locally on `work`, on your own. After each task: `plan done`, then one commit with the work and this
  plan. The hooks check each commit; a failing check is fixed from its message, as skill `lernapps-cli` says.
- What you cannot decide: choose, write it under "Key decisions" with "(guess)", go on.
- The creator asks for a change: say your reading in one sentence first, then change every place it holds for
  (`feedback-applied-everywhere`).
-->

### Tasks

- [x] Load skill `lernapps-cli`. Create the app as its section "Create" says:
      `npx --no -- lernapps create --archetype explainer`.
- [x] Fill the content guide `.agents/skills/app-content/SKILL.md` from "Notes" and "Content method": every heading,
      no "FILL IN" left. Commit it before any content.
- [x] Load skill `lernapps-explainer`.
- [x] Load skill `lernapps-content-questions`. Read whole, with your file tool:
      `.agents/skills/lernapps-explainer/references/blocks.md` and
      `.agents/skills/lernapps-explainer/references/exercises.md`. A foreign language: also
      `references/language-tasks.md` in the same folder. A component in the plan: also `references/components.md`.
- [x] Decide whether the app needs `scope`, as "`scope`" in
      `.agents/skills/lernapps-explainer/references/structure.md` says. Write the choice under "Key decisions".
- [x] Musterseite was-passiert/figuren-ort-handlung: Szene Geschichtenecke, Map-Figur und Berg-Figur, Einstieg, neu, mindestens vier Übungen, Diktat, Nachsprechen, offene Aufgabe mit points; dazu app.yaml, chapter.yaml, Wörter- und Hörsatz-Skripte; Szenen-Generator im Scratchpad
<!-- tasks: pattern (1 added): the one page or screen that is the pattern for the others -->
- [x] **Checkpoint:** the pattern page. Load skill `lernapps-learner-check` and do its learner check on the page. Fix
      what it finds. Then show the creator the page and ask whether the others may follow it. Stop and wait. A
      change: change the pattern first.
      Creator: Orchestrator-Session (in der Rolle der Ersteller:in): Die übrigen Seiten dürfen folgen, sobald die Auflagen auf der Musterseite umgesetzt sind (erledigt, Commit e1119dc).
- [x] Kapitel was-passiert: Wiederholungsseite das-brauchst-du (simple-past) und die Seiten zusammenfassung und nacherzaehlen mit Szenen, Figuren, Audio und Rückblick am Kapitelende
- [x] Kapitel bilder-erzaehlen: Wiederholungsseite das-brauchst-du (there-is-are, present-progressive, praepositionen-ort) und die Seiten verbindungswoerter-erzaehlen, bild-beschreiben (Raster) und bildergeschichte (Bildfolge) mit Audio
- [x] Kapitel selbst-erzaehlen: die Seiten geschichte-erzaehlen, geschichte-fortsetzen und tagebucheintrag mit Berg-Planung, Audio und Rückblick
- [x] Kapitel spielen-und-reimen: die Seiten dialog-schreiben und gedichte-reime mit Audio (Reimzeilen vorher anhören) und Rückblick auf die ganze Woche
- [x] Audio: alle Hörsätze mit regen_audio.py erzeugen, Skript für Hörsätze und Lösung-im-Text über alle Seiten, Wortliste gegen den Grundwortschatz
<!-- tasks: pages (5 added): the other pages or screens, after the pattern -->
- [x] Update the content guide so that it describes the app as built (`app-content-matches`).
- [x] Run `npx --no -- lernapps check` until it passes.
- [x] Look at every screen and state, at 360 px and on a desktop, as "Look at the app" of skill `lernapps-cli` says.
      Compare each with its sketch.
- [x] Do the whole-app check of skill `lernapps-learner-check`. Fix what it finds and write under "Notes" what you
      fixed.

## Commit

<!--
- Put the app on GitHub, publish it with the creator's yes, then list it. A push to `main` publishes.
- Open the pull requests (to `main`, to the catalog) without asking: they publish nothing.
- The creator asked to stop before publishing (a trial): stop here and say so.
-->

### Tasks

- [x] Load skill `lernapps-explainer-self-assessment`. Add the self-assessment as it says, or write under "Key
      decisions" why the app has none. Commit.
- [x] Load skill `lernapps-github`. Set up the repository and Pages as it says. Ask for the repository's name and
      every click only the creator can make, in one message.
- [x] Push `work`, open the preview pull request and see its checks to green, as skill `lernapps-github` says.
- [ ] **Checkpoint:** publish. Show what the app does and the preview link from the comment "Vorschau der App". Ask
      whether it may go online. Stop and wait for the yes.
- [ ] Load skill `lernapps-commit`. Publish as skill `lernapps-github` says: `work` into `main` as one squash commit,
      the run of `Pages` watched to its end.
- [ ] Open the address the job `deploy` printed and confirm that the app shows. Never use a derived address.
- [ ] Load skill `lernapps-listing`. Write the entry under "Entry draft" as it says, with the creator's answer to
      "Finding the app".
- [ ] Fill the retrospective.
- [ ] Commit this plan on `main` and push it: the listing check and the review read it there.
- [ ] **Checkpoint:** list. Open the listing pull request as skill `lernapps-listing` says, without asking first: the
      pull request is the review. See it to "bestanden", then show the creator the pull request and its result.
- [ ] If the plan changed since its last push, commit it on `main` and push again.

### Entry draft

<!-- YAML valid against the entry schema the listing skill names. Only known values, never invented. -->

```yaml
```

## Retrospective

<!-- At the end of Commit, before the listing pull request. Facts, short, no names. Read by review and evals. -->

### Phases reached

Commit (bis zum Vorschau-Pull-Request); bestätigt in Explore (Recherche), Plan (Plan und Inhaltsmethode) und Code (Musterseite) von der Orchestrator-Session (in der Rolle der Ersteller:in). Nicht veröffentlicht: der Vorschau-Pull-Request #1 bleibt offen, `lernapps check` grün, die Prüfungen „app“ und „preview“ grün.

### Creator turns after the plan

Menschliche Nachrichten nach der Planbestätigung: 0 (die einzige menschliche Nachricht der Session erlaubte vor dem Plan die npx-Befehle). Die Orchestrator-Session (in der Rolle der Ersteller:in) antwortete nach der Planbestätigung dreimal: Auflagen an der Musterseite (when üben, Textmenge, Tabelle, Inhaltsführer, Notes), Freigabe der Musterseite mit der Bitte um ganze Sätze im `scope`, Regel „Hörsatz endet zweisilbig“ und „Ding nur für Gegenstände“.

### Where I had to guess

- Hurdles und „Finding the app“ standen nicht im Auftrag: von mir angenommen („Englisch Geschichten schreiben und nacherzählen, Klasse 5 und 6“).
- `verbindungswoerter-erzaehlen` steht als erste Seite von Kapitel 2 (nicht in Kapitel 1), weil `bildergeschichte` sie braucht.
- Wörter wie stick, suddenly, forest, noise gelten laut Wortliste (Skript) als A1/A2 und stehen nicht in den Tabellen; build-up, climax, pond, character, shed, shelf, script, scene, rhyme, verse, rhythm, fox, bowl, umbrella, kite, melt, diary, foreground, background, sandcastle sind auf den Seiten erklärt.
- Haustiernamen der Übungsgeschichten (Max, Goldie, Coco, Bella) und Verwandte (grandpa, mum, dad) sind Nebenfiguren ohne Rückfrage; Kindernamen außerhalb der sechs Figuren gibt es nicht.
- Die Seiten wurden von vier Sub-Agenten je Kapitel nach dem Muster der Musterseite gebaut, danach durch Gesamtcheck und zwei Sprachprüfungen und vier Korrektur-Agenten überarbeitet; die MP3 wurden nicht angehört.
- Die Pages-Einstellung (Branch gh-pages) konnte ich nicht lesen (die API ist für diese Session gesperrt); `gh-pages` und die Vorschau-Adresse bestehen.
