---
title: ASKField ohne Document Builder einfügen
linktitle: ASKField ohne Document Builder einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein ASK-Feld in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes unten, der die Funktion „Ein ASK-Feld ohne DocumentBuilder einfügen“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und des Absatzes

Wir beginnen mit der Erstellung eines neuen Dokuments und dem Abrufen des ersten Absatzes.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Schritt 3: Einfügen des ASK-Feldes

 Wir benutzen das`AppendField()` Methode, um ein ASK-Feld in den Absatz einzufügen.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Anschließend konfigurieren wir die verschiedenen Eigenschaften des ASK-Feldes, indem wir die gewünschten Werte angeben.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Schließlich nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispiel des Quellcodes zum Einfügen eines ASK-Feldes ohne DocumentBuilder mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumenterstellung.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Fügen Sie das ASK-Feld ein.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, ein ASK-Feld ohne Verwendung von DocumentBuilder eingefügt, die verschiedenen Eigenschaften des Felds konfiguriert und das Dokument unter einem angegebenen Dateinamen gespeichert.

Damit ist unsere Anleitung zur Verwendung der Funktion „ASK-Feld ohne DocumentBuilder einfügen“ mit Aspose.Words für .NET abgeschlossen.

### Häufig gestellte Fragen

#### F: Was ist ein ASK-Feld in Aspose.Words?

A: Ein ASK-Feld in Aspose.Words wird verwendet, um dem Benutzer beim Öffnen eines Dokuments eine Frage zu stellen. Es wird häufig verwendet, um bestimmte Informationen oder Feedback anzufordern, die von Benutzer zu Benutzer unterschiedlich sein können.

#### F: Wie füge ich ein ASK-Feld in ein Word-Dokument ein, ohne den Document Builder in Aspose.Words zu verwenden?

A: Um ein ASK-Feld in ein Word-Dokument einzufügen, ohne den Document Builder in Aspose.Words zu verwenden, können Sie diese Schritte befolgen:

1. Importieren Sie die Dokument- und Feldklasse aus dem Aspose.Words.Fields-Namespace.
2. Erstellen Sie eine Instanz von Document, indem Sie Ihr vorhandenes Dokument laden.
3. Verwenden Sie die Methode InsertField, um ein ASK-Feld einzufügen, indem Sie den Fragennamen angeben.
4. Speichern Sie das Dokument.

#### F: Wie erhalte ich die Benutzerantwort für ein ASK-Feld in einem Word-Dokument?

A: Um die Benutzerantwort für ein ASK-Feld in einem Word-Dokument abzurufen, können Sie die in der Document-Klasse verfügbare Methode GetFieldNames verwenden. Diese Methode gibt eine Liste mit den Namen der im Dokument vorhandenen Felder zurück. Sie können dann prüfen, ob der ASK-Feldname in der Liste vorhanden ist, und die zugehörige Antwort abrufen.

#### F: Kann das ASK-Feld verwendet werden, um weitere Informationen vom Benutzer anzufordern?

A: Ja, das ASK-Feld kann verwendet werden, um mehrere Informationen vom Benutzer abzufragen. Sie können mehrere ASK-Felder in Ihr Dokument einfügen, jedes mit einer anderen Frage. Beim Öffnen des Dokuments wird der Benutzer zur Eingabe der entsprechenden Antworten aufgefordert.