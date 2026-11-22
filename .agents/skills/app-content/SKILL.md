---
name: app-content
description: Use for any content work in this app - researching, writing, extending, correcting or reviewing its competencies, chapters, pages, rounds, questions, exercises, figures, terms or sources. This app's own content decisions; they take precedence over the generic lernapps content skills. Load it before you change any content.
---

# Content guide of this app

„Geschichten lesen, erzählen und weiterschreiben“: Explainer (Einheiten-App `subject: englisch`, Format 2, Sprache Deutsch, englische Beispiele) über das Lesen, Nacherzählen, Beschreiben, Schreiben und Spielen von Geschichten. Der Geschichtenberg (story mountain: beginning, build-up, climax, ending) mit der story map (who, where, when, what) trägt die App. Auftrag: Issue lernapps/apps#479 (Epic lernapps/apps#489, Konventionen dort). Die erste Version baut nur Stufe 5-6 (Kapitel 1 bis 4); Kapitel 5 „Anders erzählen“ (Stufe 7-8) kommt als Inkrement `increment/<NN>-<name>`.

## Curriculum

Englisch als erste Fremdsprache, Klasse 5-6 (erstes und zweites Lernjahr, Stufe 5-6 der Karte). Kein Lehrplan: Reihenfolge und Bausteine kommen aus der Lernlandkarte `https://lernapps.net/apps/map/englisch.json` (Fokus `competency`; diese App ist eine Einheiten-App über die Stränge `texte` und `wortschatz`; jede Seite übt Bausteine eines Strangs). Vorwissen aus anderen Explainern: simple past (#472), there is/there are (#473), present progressive (#472), Präpositionen des Ortes (#475). Nicht hier: Zeitformen selbst (#472), Kurzgeschichte, Gedicht, Drama und Film untersuchen (#483), Sachtexte und Bericht (#486), Sicht der Figur und Stimmung (Kapitel 5, später).

## Competencies

Alle elf sind Lücken der Karte, Band 5-6. Eine Seite je Baustein, Ordnung nach `requires`; Id = Karten-Id, in `competencies:` jeder Seite (die Wiederholungsseiten haben keine).

1. Kapitel `was-passiert` („Was passiert in der Geschichte?“, Montag)
   - Wiederholung `recap: [englisch/simple-past]` → `was-passiert/das-brauchst-du`
   - `figuren-ort-handlung` → `was-passiert/figuren-ort-handlung` (Musterseite): „Ich kann in einer Geschichte oder einem Film herausfinden, wer vorkommt, wo und wann sie spielt und was passiert.“
   - `zusammenfassung` → `was-passiert/zusammenfassung`: „Ich kann das Wichtigste eines kurzen Textes in wenigen Sätzen zusammenfassen.“
   - `nacherzaehlen` → `was-passiert/nacherzaehlen`: „Ich kann den Inhalt einer Geschichte in eigenen Worten nacherzählen.“
2. Kapitel `bilder-erzaehlen` („Bilder erzählen“, Dienstag und Mittwoch)
   - Wiederholung `recap: [englisch/there-is-are, englisch/present-progressive, englisch/praepositionen-ort]` → `bilder-erzaehlen/das-brauchst-du`
   - `verbindungswoerter-erzaehlen` → `bilder-erzaehlen/verbindungswoerter`: „Ich kann Sätze in einer Erzählung mit first, then, after that und finally ordnen.“
   - `bild-beschreiben` → `bilder-erzaehlen/bild-beschreiben`: „Ich kann ein Bild beschreiben und dabei sagen, wo sich etwas befindet (in the foreground, on the left).“
   - `bildergeschichte` → `bilder-erzaehlen/bildergeschichte`: „Ich kann zu einer Bildergeschichte einen zusammenhängenden Text schreiben.“
3. Kapitel `selbst-erzaehlen` („Selbst erzählen“, Donnerstag)
   - `geschichte-erzaehlen` → `selbst-erzaehlen/geschichte-schreiben`: „Ich kann eine kurze Geschichte mit Anfang, Mitte und Ende schreiben.“
   - `geschichte-fortsetzen` → `selbst-erzaehlen/geschichte-fortsetzen`: „Ich kann eine Geschichte fortsetzen oder ein anderes Ende dafür schreiben.“
   - `tagebucheintrag` → `selbst-erzaehlen/tagebucheintrag`: „Ich kann einen Tagebucheintrag über meinen Tag oder ein Erlebnis schreiben.“
4. Kapitel `spielen-und-reimen` („Spielen und reimen“, Freitag)
   - `dialog-schreiben` → `spielen-und-reimen/dialog-schreiben`: „Ich kann einen kurzen Dialog oder eine Spielszene schreiben.“
   - `gedichte-reime` → `spielen-und-reimen/gedichte-reime`: „Ich kann Reime, Lieder und kurze Gedichte vortragen und Reimwörter finden.“

Die „Ich kann“-Sätze oben sind die der Karte (nicht umformulieren); eine Seite trägt nur ihre Karten-Id in `competencies:` und sagt im Abschnitt „Das kannst du danach“ in Kinderworten, was man danach kann. Übungs-IDs: Präfix = Seite (`figuren-…`), Diktat `<seite>-hoeren`, Nachsprechen `<seite>-nachsprechen`, offene Aufgabe `<seite>-schreiben`.

## Content structure

- Pfad: `src/<kapitel>/chapter.yaml`, Seiten `src/<kapitel>/<seite>.yaml`, Bilder `src/images/`, Audio `src/audio/`.
- Jede Seite (außer den Wiederholungsseiten) hat dieselben Abschnitts-IDs in dieser Reihenfolge: `einstieg` (Szene als Bild, erste leichte Aufgabe, „Das kannst du danach“, höchstens eine kurze Wörtertabelle „Klassenzimmer-Poster · Neue Wörter“), `neu` (Berg- oder Map-Figur, Merke-Kasten), `uebung` (mindestens vier Übungen, leicht → schwer, mindestens zwei mit eigener Fehlermeldung je typischem Fehler), `anwenden` (`speaking-task` und `open-task` mit `points` und `solution`), `weiter` (nächster Schritt der Geschichtenwoche; am Kapitelende ein Rückblick). Titel sagen, was der Abschnitt tut. Die Wiederholungsseiten haben nur Text und eine Tabelle, keine Übung.
- Länge: höchstens 350 Wörter Text, höchstens 4 Textblöcke hintereinander, Bild oder Übung in den ersten vier Blöcken. Jede Seite bringt einen neuen Schritt (`explainer-one-step`).
- Szene (Wo, Wer, Wann): Wo: die **Geschichtenecke** im Klassenzimmer der Millbrook School mit dem Wandbild „Geschichtenberg“ (Berg mit vier Fähnchen) und der „story map“ daneben (neuer Ort, nur für diesen Explainer und seine Inkremente). Wer: Mr Hill, Sophie, Ellie, Peter und Amir. Wann: Mr Hills **Geschichtenwoche im Januar**: Kapitel 1 Montag, Kapitel 2 Dienstag und Mittwoch, Kapitel 3 Donnerstag, Kapitel 4 Freitag (Vorlesen und Spielszene). Kein Schulfest und kein Lagerraum (#475), keine Ausstellung „Our Millbrook“ im Flur (#476), keine Satzstreifen-Wand (#481), kein Zeitstrahl (#472).
- Figuren und Orte wie in #470 (nicht ändern): Sophie (blond, Zöpfe, grüne Jacke, aus Deutschland, wohnt bei den Parkers, 11 bis 12), Ellie Parker (11, roter Pferdeschwanz, rote Jacke), Peter Parker (9, kurze braune Haare, gelbe Jacke, Ellies Bruder), Amir (11, schwarze Locken, Brille, blaue Jacke), Mr Hill (Englischlehrer, graue Haare, braune Jacke), Mrs Parker. Millbrook School, Schultag ab 8:45. Geburtstage: Peter 5. Mai, Ellie 10. Juli, Amir 12. Oktober, Sophie 14. Oktober. Tabellen heißen „Klassenzimmer-Poster · …“ und „Schulkalender · …“; der Tabellenkopf der Wörter ist [Wort, Bedeutung] („Ausdruck“ nur für feste Ausdrücke). Keine neue Figur.
- Die Beispielgeschichten (Text) und die Übungsgeschichten sind je Seite verschieden, alle eigene Texte (keine übernommenen); sie sind höchstens etwa 80 Wörter lang und im simple past erzählt.
- Anrede „du“.

## Terminology

- „Ausdruck“ (fester Ausdruck), nie „Wendung“. Fachbegriffe noun, verb, adjective, sentence, tense (aus #470).
- Berg-Wörter (immer dieselben): Geschichtenberg, Fähnchen, Station; die vier Stationen heißen beginning, build-up, climax, ending. Map-Wörter: story map, Feld, who, where, when, what. Wegweiser sind first, then, after that, suddenly, finally (auf Schildern am Berg).
- Britisches Englisch (favourite, colour). Englische Aufgaben enthalten kein deutsches Wort. Englisches mit deutscher Bedeutung, wo ein Wort neu ist.
- Aussprache: keine Lesehilfe und keine Lautschrift (IPA gehört zu #482); Hörtexte nur als ganze Sätze.
- Wörter: Grundwortschatz A1/A2; jedes Wort steht vor der Übung auf der Seite; Wörter außerhalb der Liste stehen auf der Seite erklärt und unten unter „Sources“.

## Exercise patterns

Aufbau leicht → schwer: wählen/zuordnen → ordnen → Lücke → schreiben mit Cue → Diktat und Nachsprechen → freie Aufgabe. Je Übung `mistakes` mit eigener Meldung, `hint` nur dort, wo er einen Weg zeigt, ohne die Lösung zu nennen; gleichwertige Antworten mit `(a|b)`.

- Map füllen (`matching` Frage ↔ Feld; `language-task` choice), Station finden (`single-choice` mit `info` je Option), Details zuordnen (`multiple-choice`), Berg ordnen (`ordering`).
- Zusammenfassung: Wichtiges von Nebensachen trennen (`multiple-choice`), beste Zusammenfassung wählen (`single-choice`), kürzen (`language-task` write mit Cue).
- Nacherzählung und Bildergeschichte: Stationen ordnen, Satz im simple past bilden (`language-task` write, `cue: "Amir · lose · bag · bus"`).
- Wegweiser setzen (`language-task` choice, `ordering`), Bild beschreiben (Raster `matching`, `gap`, `write` mit Cue).
- Geschichte planen und schreiben (Cue-Zeilen je Station), fortsetzen (`single-choice` zweiter Gipfel oder anderes Ende mit `info`, `write`), Tagebuch (Anrede, Datum, Tagesberg ordnen), Dialog (Sprecher zuordnen, Zeilen ordnen, Skriptform „Sophie: …“), Reime (Reimpaare nach Schreibung und Muster zuordnen, Verse ordnen).
- Hören und schreiben (`language-task` mit `audio`) und Nachsprechen (`speaking-task`): je Seite drei ganze Sätze, die auf der Seite nicht vorkommen.
- Anwenden (`open-task`): immer `points` und eine Musterlösung; die App bewertet den Text nicht, die Kinder prüfen ihn selbst an den Punkten.
- Gleichwertige Antworten stehen als Gruppe `(a|b)` im `target` (nicht verschachtelt; das Feld `accepted` einer Aufgabe wird nicht beachtet). `form: { punctuation: ok }` bei richtigen Antworten, Kommas sind nicht Thema.
- Eine kurze Wörtertabelle je Seite („Klassenzimmer-Poster · Neue Wörter“), einfache Wörter gelten als bekannt. Keine Komponenten (`prefer-built-in-block`), keine Datendateien: Berg und Map sind Zeichnungen.
- Jede Seite hat eine andere Menge an Übungsarten (`explainer-page-variety`).
- Reime: Klang lässt sich nicht prüfen; Reimpaare werden nach Schreibung und Muster zugeordnet (cat–hat, light–night), der Klang kommt über Hören und Nachsprechen ganzer Verse hinzu. „Klatschen“ ist eine Anleitung, kein geprüftes Ergebnis.
- Typische Fehler (jeweils `mistakes`): present statt past beim Erzählen, Nebensachen in der Zusammenfassung, Ort und Zeit vertauscht, suddenly und finally an der falschen Station, in/on/at im Bild, is/are bei there, Dialog ohne Sprecher oder mit Erzähltext, Reim nach Schreibung statt nach Klang.

## Figures

(Das Zeichenskript liegt nicht im Repository; die SVG-Dateien sind die Quelle. Neue Zeichnungen im gleichen Stil, Figuren aus `szene-figuren-ort-handlung.svg` kopieren.)

- Familie `src/images/geschichtenberg-<seite>.svg` (Berg mit vier Fähnchen, neutrale Farbe #34495e, Gipfel = climax; Schilder für Wegweiser) und `src/images/geschichtenmap-<seite>.svg` (vier Felder who #2c6fd8, where #138d75, when #d35400, what #c0392b; diese Farben bedeuten nur diese Felder). Szenen `src/images/szene-<seite>.svg` mit den Figuren als `<g id>` aus `millbrook-klassenzimmer.svg` von hello-millbrook, gleich gelassen. Bildfolgen (Kapitel 2): eigene Strichzeichnungen ohne Text.
- Eigene Zeichnung, `CC-BY-4.0`, Hintergrund #f4efe2, Schrift mindestens 16 im 480er viewBox, Beschriftung innerhalb des `viewBox`; keine Fotos, keine Figuren aus Büchern, Filmen oder Marken. `alt` sagt, was die Figur zeigt, nie die Lösung; in Aufgaben zeigt die Figur nur die Legende. Bildunterschrift nennt, wer wer ist.
- Berg und Map in einer Figur zeigen nie dieselben Ereignisse oder Wörter wie die erste Aufgabe darunter.
- Gebaut (erste Version, `src/images/`): Szenen `szene-<seite>.svg` für `figuren-ort-handlung`, `zusammenfassung`, `nacherzaehlen`, `verbindungswoerter`, `bild-beschreiben`, `bildergeschichte`, `geschichte-schreiben`, `geschichte-fortsetzen`, `tagebucheintrag`, `dialog-schreiben`, `gedichte-reime`; `geschichtenmap-figuren-ort-handlung` (Beispiel „red hat“); Berge `geschichtenberg-<seite>` für `figuren-ort-handlung`, `zusammenfassung` (Hauptereignisse am Berg, Nebensachen fallen), `nacherzaehlen`, `verbindungswoerter` (mit Wegweiser-Schildern), `geschichte-schreiben` (leere Planvorlage), `geschichte-fortsetzen` (zwei Gipfel), `tagebucheintrag` (Tagesberg); Bilder für Kapitel 2: `bild-park-raster` und `bild-strand-raster` (3 × 3-Raster) und die Bildfolgen `bildfolge-ball-fenster`, `bildfolge-amir-katze`, `bildfolge-sophie-bus`; Kapitel 4: `skript-dialog-schreiben` (Skriptstreifen) und `reime-gedichte-reime` (Reimkarte). Die Fähnchenzahlen der Szenen haben Schriftgröße 16.
- Skizzen in `.vibe/sketches/`; ein kleines Skript im Scratchpad (nicht im Repository) erzeugt die Zeichnungen: die SVG-Dateien sind die Quelle.

## Built (Stand der ersten Version)

Seiten, Übungs-IDs (Präfix = Seite; Diktat `…-hoeren`, Nachsprechen `…-nachsprechen`, offene Aufgabe `…-schreiben…`):
- `was-passiert`: `das-brauchst-du` (Wiederholung simple-past, Tabelle „Klassenzimmer-Poster · Wiederholung“, keine Übung), `figuren-ort-handlung` (figuren-start, -who, -where, -when, -berg, -ende, -map-schreiben), `zusammenfassung` (zusammen-start, -beste, -zuordnen, -ordnen, -kuerzen), `nacherzaehlen` (nacherzaehlen-start, -ordnen, -fehler, -station, -schreiben-satz).
- `bilder-erzaehlen`: `das-brauchst-du` (Wiederholung there-is-are, present-progressive, praepositionen-ort), `verbindungswoerter` (verbindung-start, -berg, -waehlen, -ordnen, -schreiben), `bild-beschreiben` (bild-start, -raster, -luecke, -schreiben), `bildergeschichte` (folge-start, -form, -fehler, -ordnen, -schreiben).
- `selbst-erzaehlen`: `geschichte-schreiben` (schreiben-start, -stationen, -plan, -anfang, -saetze), `geschichte-fortsetzen` (fortsetzen-start, -weg, -treue, -schreiben, -suddenly), `tagebucheintrag` (tagebuch-start, -tag, -anrede, -saetze, -fehler).
- `spielen-und-reimen`: `dialog-schreiben` (dialog-start, -sprecher, -ordnen, -fehler, -luecken, -skript), `gedichte-reime` (reime-start, -paare, -zeile, -klang, -verse, -luecke).
- Audio: alle Hörsätze stehen in `.agents/skills/app-content/scripts/audio-texte.json` (Datei → Satz, 66 Einträge: je Seite drei Diktat- und drei Nachsprechsätze, Reimseite mit Versen). Die Reimverse (`gedichte-reime`) sind vor der Veröffentlichung von der Ersteller:in abzuhören.
- Selbsteinschätzung (`selfAssessment` je `chapter.yaml`): 2 bis 3 Übungen je Seite, die ohne die Seite verständlich sind (Geschichte steht in der Frage oder im `material`): `was-passiert` figuren-start, -ende, -map-schreiben · zusammen-start, -beste, -kuerzen · nacherzaehlen-start, -fehler, -schreiben-satz; `bilder-erzaehlen` verbindung-berg, -waehlen · bild-raster, bild-luecke · folge-form, folge-fehler; `selbst-erzaehlen` schreiben-stationen, -anfang · fortsetzen-suddenly, -weg · tagebuch-tag, -anrede; `spielen-und-reimen` dialog-ordnen, -fehler · reime-paare, -zeile, -klang. Offene Aufgaben, Diktat und Sprechen sind nicht dabei.
- Zeitformen: Geschichten im simple past; Map-Einträge und Anweisungen im simple present (auf der Musterseite erklärt).

## Sources

Karte `https://lernapps.net/apps/map/englisch.json` und die Baustein-Seiten `https://lernapps.net/apps/map/englisch/c/<id>/`; Grundwortschatz `https://lernapps.net/apps/map/englisch/grundwortschatz/` (A1/A2). Der story mountain und die story map sind Unterrichtsbilder aus dem Auftrag (Issue #479); es wird keine Quelle zitiert und kein Satz übernommen. Nicht geprüft: Wikipedia „Narrative structure“ und „Freytag's pyramid“ (die Abfrage lieferte keinen Text), kein Klexikon-Artikel gelesen. Alle Geschichten, Dialoge und Reime sind eigene Texte (CC BY 4.0), alle Zeichnungen eigen. Audio: KI-Stimme `bf_emma` (britisch, weiblich), mit Skill `lernapps-audio` erzeugt und als KI-generiert markiert. Material der Ersteller:in: keines. Wörter außerhalb des Grundwortschatzes, auf der Seite erklärt (Datei `.agents/skills/app-content/scripts/woerter-erklaert.json`, die das Prüfskript liest): build-up, climax, pond (`figuren-ort-handlung`), character, shed, shelf; summary, detail, goldfish, carry (`zusammenfassung`); retell, glove, fox, kitten (`nacherzaehlen`); foreground, background, sandcastle, kite, shop (`bild-beschreiben`, `bildergeschichte`); kite, melt, diary (`geschichte-schreiben`, `geschichte-fortsetzen`, `tagebucheintrag`); script, scene (`dialog-schreiben`); rhyme, rhymes, rhythm, verse (`gedichte-reime`); Haustiernamen der Übungsgeschichten (Smoky, Goldie, Coco, Max) sind Eigennamen. Prüfskript: `python3 -I .agents/skills/app-content/scripts/pruefen.py` (Hörsätze gegen den Text derselben Seite, Wörter gegen die Liste der Karte; die Wortmeldungen zu deutschen Wörtern in englischen Feldern sind Rauschen).

## Adding a chapter or round

1. Baustein auf der Karte wählen; die Voraussetzungen müssen auf früheren Seiten stehen oder eine Wiederholungsseite bekommen.
2. Seite `src/<kapitel>/<seite>.yaml` mit den Abschnitten `einstieg`, `neu`, `uebung`, `anwenden`, `weiter` anlegen, in `chapter.yaml` eintragen, Competency-Id setzen.
3. Zeichnungen: Berg- und Map-Figur um das Neue erweitern (Kapitel 5: das Feld who bekommt eine Brille, das Feld where eine Farbe für die Stimmung); Szene mit den kopierten Figuren.
4. Übungen aus den Mustern oben, je mit `mistakes` und `hint`; 1 bis 3 ihrer Übungen in `selfAssessment` des Kapitels aufnehmen (Skill `lernapps-explainer-self-assessment`).
5. Hörtexte: Datei `src/audio/<satz>.mp3` und Eintrag in `.agents/skills/app-content/scripts/audio-texte.json` (Datei → Satz, je Seite 3 Diktat- und 3 Nachsprechsätze), erzeugt mit `~/.cache/lernapps/audio/venv/bin/python .agents/skills/app-content/scripts/regen_audio.py .agents/skills/app-content/scripts/audio-texte.json "<Satz>"` (schneidet das Ausklingen ab); anhören lassen; Sätze nicht zwischen Seiten wiederholen, Namen am Satzende zweisilbig.
6. Wörter gegen den Grundwortschatz prüfen; Hörsätze gegen den Text derselben Seite prüfen; `npx --no -- lernapps check`; committen.

## Rules learned from mistakes

Aus den Vorgängern (#470 bis #481) übernommen:
- Jede Übung fragt nur Wörter ab, die vorher auf der Seite stehen.
- Eine Tabelle, die eine Übung beantwortet, steht nicht direkt über ihr; Poster, Merke, Einstieg und Bild nennen andere Beispielsätze und Wörter als die Übungen darunter.
- Englische Aufgaben enthalten kein deutsches Wort; der Cue ist englisch, der deutsche Hinweis steht in `source` oder in der Aufgabe.
- Mit `(a|b)` gleichwertige richtige Antworten zulassen; Auswahlaufgaben zur Großschreibung zeigen alle Optionen gleich geschrieben.
- Audio: das Ausklingen der Stimme am Satzende abschneiden (`regen_audio.py`), Namen am Satzende zweisilbig (Sophie, Peter, Ellie, Amir).
- Diktat und Nachsprechen bringen neue Sätze: kein Hörsatz steht wörtlich oder fast wörtlich (nur Name oder Farbe getauscht) im Einstieg, Poster, Merke, Bildtext oder in einer Auswahl-, Ordnungs-, Schreib- oder Übersetzungsübung derselben Seite (ein Skript prüft alle Seiten).
- Bilder: Beschriftungen innerhalb des `viewBox`; Bildunterschrift nennt, wer wer ist; das `alt` verrät nie die Lösung.
- Als Auswahl nur echte Lernerfehler, keine Unwörter; jeder Distraktor und jedes typische Fehlerbild eine eigene Meldung; ein Einstiegs-`single-choice` hat mindestens drei Optionen.
- Die Rückmeldung einer Einzelauswahl hängt „: “ an den Optionstext: Optionstexte enden ohne Punkt.
- Eine Auswahl-Übung (`mode: choice`) braucht einen deutschen Satz (`source`) als Start.
- Höchstens eine kurze Wörtertabelle je Seite; Seiten mit mehr als etwa 25 Items oder 10 Übungen kürzen.
- Wörter, die eine Übung braucht, aber nur im Fließtext erklärt sind, stehen zusätzlich in der Tabelle.
- Die `competencies:` jeder Seite sind Karten-Ids (nicht Seitentitel); Wiederholungsseiten haben keine.
- Bekannte Eigenheiten der Vorlage: `ordering` zeigt Auswahlfelder statt Karten, `accepted` einer Sprach-Aufgabe wirkt nicht, im Modus `choice` zeigt die App `mistakes` nicht, `punctuation: hint` meldet bei richtiger Antwort „Achte auf die Satzzeichen“ (darum `punctuation: ok`).
- Offene Aufgaben: immer `points` und Musterlösung mit dem Hinweis, dass die App den Text nicht bewertet.

Aus der Musterseite (Lerner-Check, Sprachprüfung, Prüfung der Orchestrator-Session):
- Jedes Feld der Map (who, where, when, what) wird geübt, nicht nur als Distraktor oder in einer Zuordnung, die den Text darüber wiederholt.
- Übungsgeschichten haben eindeutige Orte und Dinge (nicht zwei Kisten, keine Tür ohne Ort); die richtige Option ist nicht die längste.
- Ein Cue verlangt keinen Satz, den eine Ordnungsaufgabe darüber schon zeigt; Map-Einträge (what) sind klare Handlungen im simple present, mit eigener Meldung für fehlendes -s, falsche Zeit und fehlenden Artikel.
- Eine Ordnungsaufgabe zum Berg erklärt alle vier Stationen; eine Einzelauswahl danach fängt typische Verwechslungen (climax und ending) mit je einer Meldung ab.
- Wörtertabelle: nur Wörter außerhalb von A1/A2 oder weniger einfache, Kopf [Wort, Bedeutung]; Wörter wie beginning, ending, suddenly und stick gelten als bekannt.
- `lernapps check` zählt Texte, Optionen, Infos und Meldungen zusammen (höchstens 350 Wörter): Meldungen knapp halten.
- Ein Doppelpunkt in einem Hinweis, einer Meldung oder einer `explanation` lässt das YAML scheitern: vermeiden oder in Anführungszeichen setzen.
- Offene Aufgaben haben eine Musterlösung in der Form der Aufgabe (vier Zeilen who/where/when/what) mit anderen Figuren als die Beispielgeschichte der Seite.
- Ein Intonationshinweis nur, wenn er stimmt (Fragen mit who, where, what fallen am Ende); im Zweifel streichen.
- Poster, Tafel und Bilder an der Wand heißen in Text und Bildunterschrift gleich (Geschichtenberg, story map, Klassenzimmer-Poster für die Wörter).
- Ein Hörsatz endet auf ein zweisilbiges Wort, am besten auf einen zweisilbigen Namen (Sophie, Peter, Amir, Ellie); Sätze, die auf ein kurzes einsilbiges Wort enden, bekommen beim Erzeugen einen Fehllaut am Ende. Bei Reimen zweisilbige Reimwörter am Versende wählen.
- „Ding“ steht nur für Gegenstände; Menschen und Tiere sind keine Dinge.
