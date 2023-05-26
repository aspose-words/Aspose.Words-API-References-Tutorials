---
title: Zusammenführungsfeld mithilfe von DOM einfügen
linktitle: Zusammenführungsfeld mithilfe von DOM einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET benutzerdefinierte Feldzusammenführungsfelder in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-merge-field-using-dom/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Feld einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und DocumentBuilder

Wir beginnen mit der Erstellung eines neuen Dokuments und der Initialisierung eines DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Bewegen Sie den Cursor zum Absatz

 Wir benutzen das`MoveTo()` -Methode des DocumentBuilders, um den Cursor zu dem Absatz zu bewegen, in dem wir das Feldzusammenführungsfeld einfügen möchten.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Schritt 4: Einfügen des Feldzusammenführungsfelds

 Wir verwenden den DocumentBuilder`InsertField()` Methode zum Einfügen eines Feldzusammenführungsfelds in den Absatz.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Anschließend konfigurieren wir die Eigenschaften des Feldzusammenführungsfelds, indem wir die entsprechenden Optionen angeben, z. B. den Feldnamen, den Text vor und nach dem Feld sowie Optionen für die vertikale Formatierung.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Abschließend nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispielquellcode zum Einfügen eines Feldzusammenführungsfelds mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bewegen Sie den Cursor zum Absatz.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Feldzusammenführungsfeld einfügen.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Aktualisieren Sie das Feld.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, den Cursor auf den gewünschten Absatz bewegt und dann ein Feldzusammenführungsfeld in das Dokument eingefügt.