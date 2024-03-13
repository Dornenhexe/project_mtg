## Up next
- Karteninformationen in einer Abfrage holen & speichern
- ausprobieren:
  - zwei Schritte: 1. Karten in Layern zuordnen lassen 2. Regelentscheidung
    - https://python.langchain.com/docs/modules/model_io/prompts/pipeline
- Ausarbeitung

## 13.03.2024
- Prompt
- Ausarbeitung

## 12.03.2024
- Prompt
- Card-Informationen refactor

## 11.03.2024
- Ausarbeitung

## 08.03.2024
- Ausarbeitung

## 07.03.2024
- Ausarbeitung
- Alter Prompt vom 28.02. mit komplettem Regelwerk & zusätzlichen Karteninfos:
  - Urborg & Blood Moon funktioniert in beide Richtungen
  - Humility & Opalescence nicht

## 06.03.2024
- Ausarbeitung
- Karten für zusätzliches ruling checken und übergeben: https://scryfall.com/docs/api/rulings
  - ändert sich nichts mit aktuellem Prompt

## 05.03.2024
- Ausarbeitung
- Prompt überarbeiten
  - keine besseren Ergebnisse

## 04.03.2024
- Ausarbeitung
- Notebook kommentieren
- Update README
- Regelabfrage Blood Moon vs. Urborg wieder mit falscher Begründung 
- Case 2 testen
  - im Judging falsch, aber in Begründung richtig
  - 2b komplett falsch
  - mit card1 & card2 als earlier/later timestamp im Prompt ist Judging & Begründung richtig
  - 2b wird immer noch als "earlier timestamp ist richtig" ausgegeben
  - Durch Umstellung im Prompt: Case 2a & 2b richtig erkannt und begründet


## 01.03.2024
- Ausarbeitung

## 29.02.2024
- Feedbackgespräch
- Start Ausarbeitung
- Regelabfrage Blood Moon vs. Urborg war bei Vorführung korrekt

## 28.02.2024
- Anpassungen Prompt
  - Layer im Vorfeld bestimmen
- Ergebnis: 
  - Urborg vs. Blood Moon wird korrekt erkannt, bei Blood Moon vs. Urborg wird sich auf immer noch auf Timestamp-Rule versteift
- Anpassung: 
  - komplettes Regelwerk übergeben
- Ergebnis:
  - Urborg vs Blood Moon korrekt erkannt, nicht mehr Timestamp rule, aber dafür 613.9 statt 613.8
  - Blood Moon vs Urborg verwendet immer noch Timestamp rule
- weiteres Beispiel testen: Humility vs. Opalescence
- Ergebins: auch hier wird nur Rule 613.9 verwendet ...

## 27.02.2024
- Type Error in chain.invoke gefixed: json-cards als retriever (vectorstore)
- Problem: nun werden zwei zufällige Karten gewählt
- LLM vs ChatModel
  - string vs messages für in- und output
  - ChatModels haben zusätzlich Rollen (HumanMessage, AIMessage, SystemMessage), sind spezialisiert auf Gepräche
  - LLMs für Text Vervollständigung 
  - -> für den Case: LLM --> funktioniert nicht, Prompt zu lang
- Partial_variables im prompt gewählt, um Card1 & 2 doch wiederrum als json übergeben zu können
  - es funktioniert!
- Antworten als .txt speichern um Fortschritt vergleichen zu können

## 26.02.2024
- Fehlersuche
- Definition dritter Testcase: Possessed Nomad vs Humility
  - Continuous effect auf mehreren Layern

## 23.02.2024
- card1 & card2 als json dict übergeben, nicht als string
  - von scryfall via requests

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