---
# Read by the hooks, the review, the evals. Schema: @lernapps/tooling/guidance/plan-front-matter.v1.schema.json
# Written by `lernapps plan` and the hooks. Never change a key or a value by hand.
# Archetype, as in the app's first plan. Allowed values: explainer, interactive, quiz.
archetype: explainer
# Current phase. Allowed values: explore, plan, code, commit.
phase: plan
# prePushFailures: failed pre-push runs of this increment, written by the hook.
prePushFailures: 0
# failedChecks: failed rules and runs, written by lernapps check and the hooks.
failedChecks: {}
---

# Increment: increment-02-anders-erzaehlen

<!--
For you, the assistant. One increment of a published app: new competencies, chapters, pages, rounds, questions, or a
correction. The process is in AGENTS.md; this plan holds the method.
- `npx --no -- lernapps plan next` prints the task to do now, `plan done` ticks it and prints the next one.
- You write only below Goal, Key decisions, Notes, Answers, Content method and Retrospective, in the creator's
  language. Delete the comment of a section once the section is filled.
- The first version's decisions stand: archetype, content method, content guide. Never change an earlier plan.
- Work on the branch `increment/<NN>-<short name>`. Until Commit everything is local: push nothing.
-->

*Started 2026-11-22. Explore, Plan, Code, Commit.*

## Goal

Jugendliche der Stufe 7-8 erzählen eine Geschichte aus der Sicht einer anderen Figur neu und beschreiben, wie Ort, Zeit und Sprache eine Stimmung erzeugen. Der Berg und die story map aus Kapitel 1 bis 4 bleiben das Werkzeug: das Feld who bekommt eine Brille (wessen Sicht?), das Feld where eine Farbe für die Stimmung.

## Key decisions

- Neues Kapitel 5 `anders-erzaehlen` („Anders erzählen“, Stufe 7-8) in derselben App, zwei Seiten: `perspektive-wechseln`, `setting-atmosphaere` (Karte: beide Band 7-8, Schritt 1; `requires` figuren-ort-handlung und nacherzaehlen stehen im Kapitel 1, keine Wiederholungsseite nötig).
- Lesestücke tragen die Seiten (Konventionen 8): je Seite ein eigenes Lesestück von etwa 150 bis 300 Wörtern in Abschnitten, mit Randglossar (`definition`-Blöcke), dann Aufgaben in drei Stufen (Verstehen, Belegen mit Zeile, Meinung), zuletzt ein Schreib- oder Sprechauftrag. Das Lesestück zählt nicht zu den 350 Wörtern Erklärtext; höchstens etwa 25 Items je Seite.
- Alle Texte eigen, keine fremden Sätze, keine Quellen nötig außer der Karte (kein VOA, Wikinews, Gutenberg usw.). Figuren: Sophie, Ellie, Peter, Amir, Mr Hill, Mrs Parker; Sophie ist 13 bis 14 (ein Jahr später, Klasse 8), die Texte sind Chats, Tagebuch und Geschichtenauszüge, ein Bild nur wo es etwas zeigt.
- Ort und Zeit: wieder die Geschichtenecke der Millbrook School, ein Jahr später: Mr Hills „Geschichtenwoche“ im Januar mit dem Berg und der story map, die jetzt eine Brille (who) und eine Farbe (where) bekommt. Kein neuer Ort, keine neue Figur. (guess)
- Der Begriff „Perspektive“ heißt für die Kinder „Sicht“ (Brille); Stimmung = mood, Atmosphäre nur als Fachwort mit Erklärung. (guess)

## Notes

- Kapitel 5 „Anders erzählen“ (Stufe 7-8), Strang `texte`:
  - `perspektive-wechseln` (Seitendatei `anders-erzaehlen/perspektive-wechseln`): „Ich kann eine Geschichte aus der Sicht einer anderen Figur neu erzählen.“ (`requires` figuren-ort-handlung, nacherzaehlen; Band 7-8, Schritt 1)
  - `setting-atmosphaere` (`anders-erzaehlen/setting-atmosphaere`): „Ich kann beschreiben, wo und wann eine Geschichte spielt und wie die Sprache eine Stimmung erzeugt.“ (`requires` figuren-ort-handlung; Band 7-8, Schritt 1)
- Didaktik: Lesen → Verstehen → Belegen → Meinung → Schreiben. perspektive-wechseln: Lesestück erzählt eine Szene aus Sophies Sicht (Ich-Form, simple past); die Kinder finden heraus, was Sophie weiß, fühlt und nicht weiß (Brille am Feld who), belegen mit Zeilennummern, und schreiben dieselbe Szene kurz aus Ellies Sicht neu (Pronomen, Wissen, Gefühl wechseln, Ereignisse bleiben). Fehlerbilder: nur die Pronomen tauschen (Gefühl und Wissen bleiben von Sophie), Wissen der anderen Figur verwenden, das Geschehen verändern, Zeitform wechseln. setting-atmosphaere: Lesestück beschreibt einen Weg durch den Park an einem Novemberabend; die Kinder sammeln Ort-/Zeitangaben (where/when), sortieren Stimmungswörter (Farbe am Feld where), belegen mit Zeilen und schreiben die Szene mit anderer Stimmung neu. Fehlerbilder: nur Ort nennen ohne Zeit, Stimmung behaupten statt zeigen („It was scary“), Wortwahl und Stimmung widersprechen sich.
- Umfang: drin: zwei Seiten (Kapitel 5), je Lesestück, Randglossar, drei Aufgabenstufen, Schreib- oder Sprechauftrag, Diktat/Nachsprechen mit `bf_emma`; Berg- und Map-Figur um Brille und Farbe erweitert; Selbsteinschätzung für Kapitel 5. Draußen: Kurzgeschichten- und Gedichtanalyse (#483), Berichte (#486), Stufe 9-10.
- Quellen: alle Texte eigen (CC BY 4.0); keine fremden Sätze; keine Fakten aus fremden Quellen nötig. Nicht benutzt: VOA, Wikinews, African Storybook, Simple English Wikipedia (kein Bedarf), Gutenberg (ausgeschlossen).

## Explore

<!--
- All content questions belong here; Plan maps the answers onto the app. Ask; write no code.
- Skip what earlier answers or the app already tell. At most 2 questions per message, one topic each.
-->

### Tasks

- [x] Read the README of the archetype's template (its path is in skill `lernapps-app`): what the app can do now.
      Tell the creator what is new, if it matters for this increment.
- [x] Load the content guide `.agents/skills/app-content/SKILL.md` and read the earlier plans in `.vibe/plans/`: what
      the app teaches, how its content is made, what is open.
- [x] Interview, one topic per question, the creator's words under "Answers": which competencies, chapters or rounds,
      for which school years; hurdles and examples; the amount; any change of look and feel or of terms. No answer:
      ask once more, then write your assumption with "(guess)".
- [x] Load skill `lernapps-content-research`. Research what the content guide does not cover. Write under "Notes":
      the new competencies by chapter with their ids, the sources you opened.
- [x] Write under "Notes" the didactic approach per competency and the scope (in, out, data range).
- [x] The increment needs a kind of content the guide does not cover (a new page structure, screen, component or kind
      of exercise): load skills `lernapps-explainer-design` and `lernapps-exercise-patterns`. Else skip this task.
- [x] **Checkpoint:** research. Show in plain words: the new competencies by chapter, the didactic approach, the
      scope, every "(guess)", the sources and what is unchecked. Stop and wait. Changes: change them, then ask again.
      Creator: Orchestrator-Session (in der Rolle der Ersteller:in): Ja, passt (zwei Seiten, je ein eigenes Lesestück, Geschichtenecke ein Jahr später, „Sicht“ für die Kinder). Weiter zu Plan und Inhaltsmethode. Push des Inkrement-Branchs und zweiter Vorschau-PR nur nach Erlaubnis der Ersteller:in; bis dahin lokal.

### Answers

- Auftrag der Orchestrator-Session (in der Rolle der Ersteller:in): „Baue Kapitel 5 ‚Anders erzählen‘ (Stufe 7-8) als Inkrement in dasselbe Repository; hier tragen Lesestücke (Geschichtenauszüge, Tagebucheinträge, Erzähler-Perspektiven) die Seiten. … Alle Geschichten eigen (keine fremden Sätze); Gutenberg bleibt vorerst außen vor.“ Issue #479, Kapitel 5: „Ich kann eine Geschichte aus der Sicht einer anderen Figur erzählen und beschreiben, wie Ort und Sprache eine Stimmung erzeugen. … das Feld who bekommt eine Brille (wessen Sicht?), das Feld where eine Farbe für die Stimmung. Die Kinder erzählen denselben Berg aus einer anderen Sicht und sammeln Wörter, die Stimmung machen.“
- Konventionen Abschnitt 8: Lesestück 150 bis 300 Wörter, Randglossar, drei Aufgabenstufen, Schreib- oder Sprechauftrag, höchstens ein Lesestück je Seite, höchstens etwa 25 Items, Hörlisten nur mit gehörten Sätzen.

## Plan

<!--
- Map the new content onto the app with the guide's patterns. The creator confirms the plan in one read.
- After the yes you work on your own.
-->

### Tasks

- [x] Load skill `lernapps-content-growth`. Add the tasks of Code as slices, one per competency, in the guide's
      order, one call each: `npx --no -- lernapps plan add --at slices "<task>"`. Say in each which sub-agent may
      write it in parallel, if any.
- [x] Write "Content method": the guide's patterns, figures and components per slice. Anything new: map it as skill
      `lernapps-explainer-design` says, and say why the guide's patterns do not fit.
- [x] Draw a sketch of each new component or interactive exercise, in `.vibe/sketches/`.
- [x] Show the creator, short: goal, new competencies by chapter, slices; in plain words what learners see and do and
      what is new. At most 2 questions.
- [ ] **Checkpoint:** confirm the plan and the content method. Stop and wait for an explicit yes. Changes: change
      them, then ask again.

### Content method

<!-- One line each: the guide's patterns, figures and components used, and where; anything new, what it does and
cannot. Something new goes into the guide in the slice that adds it. -->
- **Neu: Seite mit Lesestück (Konventionen 8).** Gleiche Abschnitts-IDs wie in Kapitel 1 bis 4, aber `einstieg` (Szene, Vorwissen-Frage, „Das kannst du danach“), `lesen` (Lesestück in Abschnitten als `text`-Blöcke, Randglossar als `definition`-Blöcke direkt neben dem Abschnitt, ein Bild nur wo es etwas zeigt), `neu` (Erklärung mit der erweiterten Map-Figur, Merke), `uebung` (drei Stufen mit Überschriften „Verstehen“, „Belegen“, „Meinung“: die Zeilen des Lesestücks sind nummeriert, Belegaufgaben fragen nach Zeilennummern), `anwenden` (Schreibauftrag `open-task` mit `points` und Musterlösung, `speaking-task` mit drei Sätzen), `weiter`. Das Lesestück hat 150 bis 300 Wörter, höchstens ein Lesestück je Seite; höchstens etwa 25 Items. Es zählt nicht zu den 350 Wörtern Erklärtext (`lernapps check` entscheidet; zählt es mit, kommt es in `quote`/`material` oder wird gekürzt).
- **Kapitel 5 `anders-erzaehlen`:** `src/anders-erzaehlen/chapter.yaml` (Titel „Anders erzählen“, `pages: [perspektive-wechseln, setting-atmosphaere]`, `selfAssessment`), `src/app.yaml` bekommt das Kapitel am Ende von `chapters`, die Karten-Ids stehen in `competencies:`; kein Recap (die `requires` stehen auf den Seiten 1 und 3 von Kapitel 1). Die Geschichte der Seiten: Geschichtenwoche im Januar ein Jahr später (Klasse 8), Mittwoch und Donnerstag; Sophie 13 bis 14.
- **Seite `perspektive-wechseln` (Slice 1):** Lesestück „The Late Bus“ (Sophie erzählt in der Ich-Form im simple past, etwa 220 Wörter, 6 bis 8 Zeilen je Abschnitt nummeriert, 2 Abschnitte, Randglossar zu 4 bis 6 Wörtern); Vorwissen-Frage: „Wer erzählt?“ (aus Kapitel 1: who). Aufgaben: Verstehen (`single-choice` Wer erzählt, was weiß die Erzählerin nicht, `matching` Gefühl ↔ Satz), Belegen (`multiple-choice` Zeilennummern, die zeigen, was Sophie denkt; `ordering`), Meinung (`single-choice` mit `info`: welche Sicht gibt mehr Spannung; keine falsche Antwort, jede Option hat eine Begründung), Schreiben (`language-task` write mit Hinweis: zwei Sätze aus Ellies Sicht, Pronomen und Gefühl; Diktat; `speaking-task`); offene Aufgabe: dieselbe Szene aus Ellies oder Amirs Sicht in 4 bis 5 Sätzen, mit `points` und Musterlösung. Typische Fehler: nur die Pronomen tauschen, Wissen der anderen Figur benutzen, Geschehen verändern, Zeitform wechseln.
- **Seite `setting-atmosphaere` (Slice 2):** Lesestück „The Park in November“ (Ellie geht allein heim; etwa 200 Wörter, Wetter, Licht, Geräusche; Randglossar zu 4 bis 6 Wörtern). Aufgaben: Verstehen (`single-choice` wo und wann spielt es; `multiple-choice` welche Angaben gehören zu where/when), Belegen (`matching` Stimmungswörter ↔ Zeilen, `ordering` Wörter nach Stärke des Gefühls ist ausgeschlossen: kein Raten ohne Karte), Meinung (`single-choice` mit `info`: welches Wort macht die Stimmung am stärksten), Schreiben (`language-task` gap/write: Stimmung ändern, Wortwahl tauschen, Diktat, `speaking-task`), offene Aufgabe: dieselbe Szene an einem Sommermorgen in 4 bis 5 Sätzen (Wörter für die andere Stimmung). Typische Fehler: Stimmung behaupten statt zeigen („It was scary“), Wortwahl widerspricht der Stimmung, nur Ort ohne Zeit.
- **Figuren:** Map-Figur `geschichtenmap-<seite>.svg` mit Erweiterung: Feld who bekommt eine Brille (kleines Brillen-Symbol und der Satz „wessen Sicht?“ nur als Beschriftung im Bild: „who · Sicht von: Sophie“), Feld where eine Farbe für die Stimmung (grau-blau = bedrückt, gelb = froh; die Farbe steht als Fläche im Feld und als Wort daneben, die vier Map-Farben who blau, where grün, when orange, what rot bleiben der Rand der Felder); Szenen `szene-<seite>.svg` aus den Figuren (Sophie 13 bis 14 etwas größer gezeichnet, gleiche Merkmale), Berge als Zeilen am Lesestück nur wo sie etwas zeigen. Skizze: `.vibe/sketches/map-sicht-farbe.svg`.
- **Muster:** `single-choice` mit `info` je Option, `multiple-choice`, `matching`, `ordering`, `language-task` write/gap, Diktat, `speaking-task`, `open-task` mit `points` und Musterlösung; Belegaufgaben fragen nach Zeilennummern; je Seite eine andere Mischung (`explainer-page-variety` zählt kapitelübergreifend). Hörsätze: ganze natürliche Sätze, keine Namen für den Klang, einsilbig endende Sätze in die Hörliste, Lesestück nur in kurzen Abschnitten (höchstens 3 Sätze, wenn überhaupt); nichts Ungehörtes als „geprüft“.
- **Prüfungen:** `pruefen.py` (Hörsätze, Wörter, jetzt auch die Wörter der Lesestücke: außerhalb A1/A2 stehen im Randglossar), `lernapps check`, Lerner-Check der Musterseite (Kind Klasse 7), Gesamtcheck und Sprachprüfung durch Sub-Agenten, Regeln aus Abschnitt 7.
<!-- An explainer: per figure, model and component its learning action in two to four sentences
(`explainer-representation-explained`); per page its prerequisites the app does not practise, and which get a recap
page, which a link. -->

## Code

<!--
- Build locally on the branch, on your own. After each task: `plan done`, then one commit with the work and this
  plan. The hooks check each commit; a failing check is fixed from its message, as skill `lernapps-cli` says.
- What you cannot decide: choose, write it under "Key decisions" with "(guess)", go on.
- The creator asks for a change: say your reading in one sentence first.
-->

### Tasks

- [ ] `git switch -c increment/<NN>-<short name>` from `main`. Commit this plan on it.
- [ ] Load skill `lernapps-cli`. Update the app as its section "Update" says. Commit the update alone and fix its
      findings before any content. The update replaces the `lernapps-*` skills: read again those you use.
- [ ] Load skill `lernapps-explainer` and the content guide.
- [ ] Load skill `lernapps-content-questions`. Read whole, with your file tool:
      `.agents/skills/lernapps-explainer/references/blocks.md` and
      `.agents/skills/lernapps-explainer/references/exercises.md`. A foreign language: also
      `references/language-tasks.md` in the same folder. A component in the plan: also `references/components.md`.
- [ ] Decide whether the app needs `scope`, as "`scope`" in
      `.agents/skills/lernapps-explainer/references/structure.md` says. Write the choice under "Key decisions".
- [ ] Slice 1 (Musterseite des Lesestücks, ich selbst): Kapitel anders-erzaehlen (chapter.yaml, app.yaml) und Seite perspektive-wechseln: Lesestück von Sophie in Ich-Form, Randglossar, drei Aufgabenstufen, Schreibauftrag aus Ellies Sicht, Map-Figur mit Brille, Szene, Hörsätze; Lerner-Check mit Sub-Agent
- [ ] Slice 2 (ich selbst, nach der Musterseite): Seite setting-atmosphaere: Lesestück Weg durch den Park im November, Randglossar, drei Aufgabenstufen, Schreibauftrag mit anderer Stimmung, Map-Figur mit Farbe, Szene, Hörsätze
- [ ] Hörlisten und Prüfungen: Audio mit regen_audio.py (neue Fassung mit Schnitt), Hörliste im Inhaltsführer, pruefen.py über alle Seiten, Gesamtcheck der Seiten des Kapitels und Sprachprüfung durch Sub-Agenten
<!-- tasks: slices (3 added): one per competency, as written in Plan -->
- [ ] **Checkpoint:** the pattern page, after the first slice. A slice in a pattern the app already has: show it to
      the creator and go on. A new pattern: load skill `lernapps-learner-check`, do its learner check, fix what it
      finds, then ask the creator whether the others may follow it, and wait.
- [ ] Update the content guide so that it describes the app as it is now (`app-content-matches`).
- [ ] Run `npx --no -- lernapps check` until it passes.
- [ ] Look at every changed screen, at 360 px and on a desktop, as "Look at the app" of skill `lernapps-cli` says.

## Commit

<!--
- Publish with the creator's yes. A push to `main` publishes.
- Open the pull requests (to `main`, to the catalog) without asking: they publish nothing.
-->

### Tasks

- [ ] If pages or exercises changed, load skill `lernapps-explainer-self-assessment` and update the self-assessment
      as it says. Commit.
- [ ] Load skill `lernapps-github`. Push the branch, open the preview pull request and see its checks to green, as it
      says.
- [ ] **Checkpoint:** publish. Show what the increment adds and the preview link. Ask whether it may go online. Stop
      and wait for the yes.
- [ ] Load skill `lernapps-commit`. Publish as skill `lernapps-github` says: the pull request squash-merged into
      `main`, the run of `Pages` watched to its end.
- [ ] Open the address the job `deploy` printed and confirm the new content. Never use a derived address.
- [ ] The app is listed and its entry changes (school years, summary): load skill `lernapps-listing` and write the
      changed entry. Else skip this task.
- [ ] Fill the retrospective.
- [ ] Commit this plan on `main` and push it. A push of only `.vibe/` publishes nothing.
- [ ] **Checkpoint:** list. The entry changed: open the pull request to the catalog as skill `lernapps-listing`
      says, without asking first, see it to "bestanden", then show the creator the pull request and its result. The
      entry did not change: tell the creator that the catalog updates the app by itself.
- [ ] If the plan changed since its last push, commit it on `main` and push again.

## Retrospective

<!-- At the end of Commit. Facts, short, no names. Read by review and evals. -->

### Phases reached

<!-- Last phase completed, checkpoints passed. E.g. "commit; confirmed, published". -->

### Creator turns after the plan

<!-- Number of creator messages after the confirmation, topic of each. Target: at most 3. -->

### Where I had to guess

<!-- Each gap in plan, skills, content guide, messages or answers, and your choice. "None" if none. -->
