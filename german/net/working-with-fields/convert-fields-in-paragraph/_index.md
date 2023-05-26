---
title: Felder im Absatz konvertieren
linktitle: Felder im Absatz konvertieren
second_title: Aspose.Words für .NET API-Referenz
description: Konvertieren Sie IF-Felder in einfachen Text in einem Absatz mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/convert-fields-in-paragraph/
---

Hier ist ein Tutorial, das zeigt, wie Sie die Funktion „Felder in Absatz konvertieren“ mit Aspose.Words für .NET verwenden. Dieser Code wandelt alle Felder vom Typ IF, die im letzten Absatz eines Dokuments vorkommen, in einfachen Text um. Führen Sie die folgenden Schritte aus, um diesen Code zu verstehen und auszuführen.

Stellen Sie sicher, dass Sie Aspose.Words für .NET installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen.

## Schritt 1: Referenzen importieren

Um Aspose.Words in Ihrem Projekt verwenden zu können, müssen Sie die erforderlichen Referenzen hinzufügen. Stellen Sie sicher, dass Sie in Ihrem Projekt einen Verweis auf die Aspose.Words-Bibliothek hinzugefügt haben.

## Schritt 2: Laden des Dokuments

Bevor Sie Felder konvertieren können, müssen Sie das Dokument laden, das die zu konvertierenden Felder enthält. Stellen Sie sicher, dass Sie den korrekten Pfad zum Verzeichnis angeben, das das Dokument enthält. So laden Sie das Dokument hoch:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

## Schritt 3: Felder in Text umwandeln

Nachdem das Dokument nun geladen ist, können wir mit der Konvertierung der Textfelder in einfachen Text fortfahren. In diesem Beispiel zielen wir nur auf die Felder ab, die im letzten Absatz des Dokuments vorhanden sind. Hier ist der Code, der diese Konvertierung durchführt:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Dieser Code verwendet eine Kombination von LINQ-Methoden, um Felder im letzten Absatz des Dokuments herauszufiltern und sie dann durch Aufrufen von in einfachen Text umzuwandeln`Unlink()` Methode.

## Schritt 4: Speichern des geänderten Dokuments

 Sobald die Felder konvertiert wurden, können Sie das geänderte Dokument speichern. Benutzen Sie die`Save()` Methode hierfür. Hier ist ein Beispiel :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für die Sicherung angeben.

### Quellcodebeispiel für „Felder in Absatz konvertieren“ mit Aspose.Words für .NET

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument.
Document doc = new Document(dataDir + "Linked fields.docx");

// Konvertieren Sie IF-Felder im letzten Absatz des Dokuments in einfachen Text.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Speichern Sie das geänderte Dokument.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```
