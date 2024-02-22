## Up next
- write first prompt
  - test prompt
- create first case for testing
- research how to give ChatGPT amount of text via langchain

## 29.02.2024
- Feedbackgespräch

## 23.02.2024
- card1 & card2 als Daten übergeben (z.B. von mtgjson oder scryfall), nicht als string
  - sonst Probleme mit Chain
  - von scryfall via requests
- Ausgabe im Notebook erweitern oder Ausgabe als .txt

## 22.01.2024
- RAG 
  - Documentloader
  - Textsplitter
  - VectorStore, Embeddings
- LCEL für Chain mit RAG
- Prompt gekürzt
- Regelwerk gekürzt

## 21.02.2024
- Testfälle definieren
- Entwurf Prompt nach folgendem Muster:
1. erhalte zwei Karten
2. gib an, was die Regeln der beiden Karten sind
3. stelle den Bezug zu Regel 613 her
4. entscheide, was zutrifft: 
    - timestamp
    - dependency
5. gib das Ergebnis aus
6. begründe Ergebnis

- Testen Prompt
  - Punkte 1-3 funktionieren
  - Entscheidung zwischen Timestamp & Dependency wird falsch getroffen, deshalb ist das Ergebnis falsch
  - Ausgabe im Notebook zu kurz

- ChatGPT sagt: "As of my last update in January 2022, I don't have access to the specific text of Magic: The Gathering's rule 613.7b. However, I can tell you that rule 613 generally pertains to continuous effects. If you need the most current version of this rule, I recommend checking the official Magic: The Gathering rules document, which is regularly updated by Wizards of the Coast, the company behind the game. You can find it on their website or through other reliable sources."
  - Folglich: Regelwerk per RAG übergeben für hoffentlich präzisere Angaben

## 20.02.2024
- Struktur Ausarbeitung
- Recherche Prompting, Regelfragen & Beispiele
  - Verständnis LCEL, RAG

## 19.02.2024
- update Dependancies

## September - Dezember 2023
- Konzept & Idee
- Projekt aufsetzen & erste Struktur
  - OpenAI einbinden

-----------------

# Struktur Ausarbeitung

# Titel: Regelfragen zu "Continuous Effects" bei Magic: The Gathering per AI beantworten

## Stand der Forschung
- Definitionen: 
  - LLM
  - ChatGPT
    - Wissen ChatGPT um MtG Rules
  - Prompt
- Problem: Antworten erscheinen richtig, enthalten aber Fehler
  - Halluzinationen (= Konfabulation) statt Regeln
  - out of date  (Lösung: Regelwerk durch RAG)
  - no sources (Lösung: Regelwerk durch RAG)
- hier benötigt: jede Menge Domänenwissen (-> Aktualität für Machine Learning Fragen)
- Aktuelle Themen: LLMs & RAG

## Techstack
- Chat GPT 3.5
- Langchain
  - LCEL = Langchain Expression Language
  - RAG = Retrieval Augmented Generation
- Github https://github.com/Dornenhexe/project_mtg 
- Pip Virtual Environment
- Jupyter Notebook

## Problemstellung
- Leitfrage: Ist es möglich, mithilfe von ChatGPT komplexe Regelfragen zu klären?
- Halluzinationen von LLMs umgehen durch konkrete Prompts 
- Große Textmenge an Chat GPT übergeben
- Definition von 3 Beispielfällen:
  - Bloodmoon vs. Urborg
  - Opalescence vs. Humility
  - ?
- Exkurs: Regeln für continuous effects mit Layern
  - einfach: bei einer Kreatur werden power/toughness vertauscht, dann erhält sie +1/+0
  - komplex: Layer/Sublayer
  - 613.7b: timestamp
  - 613.8: dependency
- Motivation: Autorin selbst Spielerin: Wie detailliert kann LLM Fragen beantworten?

## Vorgehen
- zuerst Fragen testen normal via ChatGPT: 
  - Antworten lasen sich gut und überzeugend, waren aber falsch
  - durch Nachfragen kam das richtige Ergebnis
  - Schlussfolgerung: Prompt muss in Schritte aufgeteilt sein
- langchain für gegliederte Prompts
  - CoT = Chain of Thoughts -> gegliederte Prompts in Schritten
- Idee: Prompt soll allgemein gültig sein für Regelfragen betreffend continuous effects
  - Alternative: ggf. müssen die Karten im Vorfeld erkannt werden und anhand ihrer Fähigkeiten vorgefiltert werden
  - also algorithmisch vorsortiert
- vektorisiertes Regelwerk per Langchain an ChatGPT nötig oder ist das Wissen bereits vorhanden?
  - Regelwerk veraltet Stand Januar 2022 -> das aktuelle muss übergeben werden
  - Kombination mit DSP = Directional Stimulus Prompting (-> Hinweise geben für spezifische Tasks)
- ggf. über scryfall API oder mtgjson API zuerst Gatherer Notes checken, ob der Fall schon behandelt wurde

## Prompts


## Fazit

## Ausblick
- möglich wäre eigenes trainiertes/finetuning Modell
  - Kosten vs. Nutzen
- Refaktoring von Notebook zur Python-Anwendung, Umsetzen als (Web-)App
- Ausbauen für andere Regelfragen