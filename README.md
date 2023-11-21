Start with 
``pipenv shell``

Install with
``pipenv install``

## Probleme
- Nutzung nur mit payed subscription/Guthaben von OpenAI möglich.
- Große Textmenge an Chat GPT übergeben


## Benötigte Daten:
- Rules: https://media.wizards.com/2023/downloads/MagicCompRules20230616.txt
  - als rules_shortened.txt auch in gekürzt auf relevante Parts
- Errata über https://scryfall.com/ bzw. https://mtgjson.com/

## Plan Projekt
- Verbindung Chat Gpt - Langchain
  - vektorisiertes Regelwerk per Langchain an Chat Gpt
- Prompts für Aufgabenstellung testen
  - Fragestellungen definieren & vergleichen
- Zwischenfazit
  - funktioniert es oder nicht?
- Alternative:
  - Regelabfrage algorithmisch lösen oder vorsortieren für KI-Abfrage
    - Karten einordnen in Layer
- Ausblick:
  - Refaktoring von Notebook zu Python-Dateien
  - graf. Oberfläche als Webanwendung
- Ausarbeitung & Präsentation

## Techstack
- Chat GPT 3.5
- Langchain
- Git / Github (Link zum Projekt)
- Pip Virtual Environment
  