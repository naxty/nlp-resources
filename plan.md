# Pipeline

Als Eingabe der Pipeline wird ein Text übergeben.

## Spellcheck (Optional) (Preprocessing) (NLP)
Der Spellcheck überprüft den Satz auf Richtigkeit und korrigiert die einzelnen Wörter anhand von Empfehlung. Dies könnte über die phonetische Suche mit bspw. Soundindex oder Elasticsearch implementiert.

## Sätze bilden (NLP)
Als nächste wird die Eingabe in Sätze aufgeteilt.

## Wörter bilden (NLP)
Anschließend wird mittels einem Tokenizer die Wörter des Satz identifiziert.

## POS Tagging (NLP)
Als nächstes wird die Satzstruktur um POS Tagging gebildet. Dazu kann der Kontext analysiert werden.

## Lemmatizing (NLP)
Über einen Stemmer werden die Wörter verkleinert sodass weniger Möglichkeiten der einzelnen Wörter existieren.

## Entity Extraction
Hier werden mögliche Werte wie Datum, etc. aus dem Datensatz extrahiert.

## Intent Classification (Deep Learning)
Durch mehrere Klassifizier werden die Intents (was man eigentlich will) klassifiziert. Hierzu werden mehre Klassifizier verwendet und anhand einer Konfidenz wird das Ergebnis ermittelt.

Mögliche Intents wären Telefonabfrage, Raumabfrage, Rolleabfrage, Verantwortungsabfrage, Skillabfrage

## Datenquellen

Je nachdem welcher Klassifizier die höchste Konfidenz hat, wird dadurch die eigentliche Information anhand der Kombination von Entities und Intents gewählt.

### Grakn Graph Knowledge Base

Mit [GRAKN.AI](https://grakn.ai/) kann über ein Graph das Wissen repräsentiert werden.

## Natural Language Generation

Im letzten Schritt wird anhand der Datenquelle ein Antwort erstellt. Dies kann anfangs über ein Template fungieren. Falls ausreichend Zeit vorhanden funktioniert dies auch über Recurrent Neural Networks bzw. Seq2Seq Models.
