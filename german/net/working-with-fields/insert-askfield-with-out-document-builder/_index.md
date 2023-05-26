---
title: Fügen Sie ASKField ohne Document Builder ein
linktitle: Fügen Sie ASKField ohne Document Builder ein
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein ASK-Feld in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Ein ASK-Feld ohne DocumentBuilder einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Dokument und Absatz erstellen

Wir beginnen damit, ein neues Dokument zu erstellen und den ersten Absatz abzurufen.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Schritt 3: Einfügen des ASK-Feldes

 Wir benutzen das`AppendField()` Methode zum Einfügen eines ASK-Feldes in den Absatz.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Anschließend konfigurieren wir die verschiedenen Eigenschaften des ASK-Felds, indem wir die gewünschten Werte angeben.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Abschließend nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispiel des Quellcodes zum Einfügen eines ASK-Feldes ohne DocumentBuilder mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentenerstellung.
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

Damit ist unser Leitfaden zur Verwendung der Funktion „ASK-Feld ohne DocumentBuilder einfügen“ mit Aspose.Words für .NET abgeschlossen.