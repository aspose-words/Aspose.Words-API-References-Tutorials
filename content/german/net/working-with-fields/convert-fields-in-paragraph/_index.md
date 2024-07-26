---
title: Felder im Absatz konvertieren
linktitle: Felder im Absatz konvertieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Konvertieren Sie IF-Felder mit Aspose.Words für .NET in einfachen Text in einem Absatz.
type: docs
weight: 10
url: /de/net/working-with-fields/convert-fields-in-paragraph/
---

Hier ist ein Tutorial, das zeigt, wie Sie die Funktion „Felder in Absätze konvertieren“ mit Aspose.Words für .NET verwenden. Dieser Code konvertiert alle IF-Felder im letzten Absatz eines Dokuments in einfachen Text. Befolgen Sie die nachstehenden Schritte, um diesen Code zu verstehen und auszuführen.

Stellen Sie sicher, dass Sie Aspose.Words für .NET installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen.

## Schritt 1: Referenzen importieren

Um Aspose.Words in Ihrem Projekt zu verwenden, müssen Sie die erforderlichen Referenzen hinzufügen. Stellen Sie sicher, dass Sie in Ihrem Projekt eine Referenz zur Aspose.Words-Bibliothek hinzugefügt haben.

## Schritt 2: Dokument einlegen

Bevor Sie Felder konvertieren können, müssen Sie das Dokument laden, das die zu konvertierenden Felder enthält. Achten Sie darauf, den richtigen Pfad zum Verzeichnis anzugeben, das das Dokument enthält. So laden Sie das Dokument hoch:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Legen Sie das Dokument ein.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Felder in Text umwandeln

Nachdem das Dokument nun geladen ist, können wir mit der Konvertierung der Typfelder in Klartext fortfahren. In diesem Beispiel zielen wir nur auf die Felder ab, die im letzten Absatz des Dokuments vorhanden sind. Hier ist der Code, der diese Konvertierung durchführt:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Dieser Code verwendet eine Kombination aus LINQ-Methoden, um Felder im letzten Absatz des Dokuments herauszufiltern und konvertiert sie dann in Klartext durch den Aufruf der`Unlink()` Methode.

## Schritt 4: Speichern des geänderten Dokuments

 Nach der Konvertierung der Felder können Sie das geänderte Dokument speichern. Verwenden Sie dazu die`Save()` Methode dafür. Hier ist ein Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für die Sicherung anzugeben.

### Quellcodebeispiel zum Konvertieren von Feldern in Absätze mit Aspose.Words für .NET

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Legen Sie das Dokument ein.
Document doc = new Document(dataDir + "Linked fields.docx");

// Wandeln Sie IF-Felder im letzten Absatz des Dokuments in einfachen Text um.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Speichern Sie das geänderte Dokument.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### Häufig gestellte Fragen

#### F: Was ist ein Konvertierungsfeld in Aspose.Words?

A: Ein Konvertierungsfeld in Aspose.Words ist ein Feldtyp, der einen Wert oder einen Ausdruck in ein anderes Format oder einen anderen Datentyp konvertiert. Sie können beispielsweise ein Konvertierungsfeld verwenden, um ein Datum in ein bestimmtes Format oder eine Zahl in Text umzuwandeln oder andere Arten von Konvertierungen durchzuführen.

#### F: Wie fügt man mit Aspose.Words ein Konvertierungsfeld in einen Absatz ein?

A: Um mit Aspose.Words ein Konvertierungsfeld in einen Absatz einzufügen, können Sie diese Schritte befolgen:

1. Importieren Sie die Document-Klasse aus dem Aspose.Words-Namespace.
2. Erstellen Sie eine Instanz von Document, indem Sie Ihr vorhandenes Dokument laden.
3. Holen Sie sich den Absatz, in den Sie das Konvertierungsfeld einfügen möchten.
4. Verwenden Sie die Methode InsertField, um das Konvertierungsfeld mit der richtigen Syntax einzufügen.

#### F: Welche Konvertierungsformate unterstützt Aspose.Words?

A: Aspose.Words unterstützt eine Vielzahl von Konvertierungsformaten in Feldern, darunter Datumsformate, Zahlenformate, Textformate, Währungsformate, Prozentformate und mehr. Eine vollständige Liste der verfügbaren Konvertierungsformate finden Sie in der Aspose.Words-Dokumentation.

#### F: Wie aktualisiere ich mit Aspose.Words ein Konvertierungsfeld in einem Word-Dokument?

A: Um ein Konvertierungsfeld in einem Word-Dokument mit Aspose.Words zu aktualisieren, können Sie die Methode UpdateFields verwenden. Diese Methode durchläuft das Dokument und aktualisiert alle Felder, einschließlich der Konvertierungsfelder, und berechnet die Werte basierend auf den aktuellen Daten neu.