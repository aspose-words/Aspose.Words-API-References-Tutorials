---
title: Erweitertes Feld ohne Document Builder einfügen
linktitle: Erweitertes Feld ohne Document Builder einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein erweitertes Feld in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Erweiterte Feldeinfügung ohne DocumentBuilder“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

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

## Schritt 3: Einfügen des erweiterten Feldes

 Wir benutzen das`AppendField()`Methode zum Einfügen eines erweiterten Felds in den Absatz.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Anschließend konfigurieren wir die verschiedenen Eigenschaften des erweiterten Felds, indem wir die gewünschten Werte angeben.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Abschließend nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispiel des Quellcodes zum Einfügen eines erweiterten Felds ohne DocumentBuilder mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentenerstellung.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Fügen Sie das erweiterte Feld ein.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, ein erweitertes Feld ohne Verwendung von DocumentBuilder eingefügt, die verschiedenen Feldeigenschaften konfiguriert und das Dokument unter einem angegebenen Dateinamen gespeichert.

Damit ist unsere Anleitung zur Verwendung der Funktion „Erweitertes Feld ohne DocumentBuilder einfügen“ mit Aspose.Words für .NET abgeschlossen.

