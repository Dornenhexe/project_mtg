## Up next
- write first prompt
  - test prompt
- create first case for testing
- research how to give ChatGPT amount of text via langchain

## 29.02.2024
- Feedbackgespräch

## 21.02.2024
- Entwurf Prompt
- Testen Prompt

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
- Idee: Prompt soll allgemein gültig sein für Regelfragen betreffend continuous effects
  - Alternative: ggf. müssen die Karten im Vorfeld erkannt werden und anhand ihrer Fähigkeiten vorgefiltert werden
  - also algorithmisch vorsortiert
- vektorisiertes Regelwerk per Langchain an ChatGPT nötig oder ist das Wissen bereits vorhanden?

## Prompts


## Fazit

## Ausblick
- möglich wäre eigenes trainiertes/finetuning Modell
  - Kosten vs. Nutzen
- Refaktoring von Notebook zur Python-Anwendung, Umsetzen als (Web-)App
- Ausbauen für andere Regelfragen