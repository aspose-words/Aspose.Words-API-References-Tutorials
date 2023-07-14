---
title: Erweitertes Feld ohne Document Builder einfügen
linktitle: Erweitertes Feld ohne Document Builder einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

 Wir benutzen das`AppendField()` Methode zum Einfügen eines erweiterten Felds in den Absatz.

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

### FAQs

#### F: Was ist ein erweitertes Feld in Aspose.Words?

A: Ein erweitertes Feld in Aspose.Words ist ein spezieller Feldtyp, mit dem Sie Berechnungen durchführen, Bedingungen einschließen und komplexe Vorgänge in einem Word-Dokument ausführen können. Es bietet große Flexibilität beim Erstellen dynamischer und benutzerdefinierter Felder.

#### F: Wie füge ich ein erweitertes Feld in ein Word-Dokument ein, ohne den Document Builder in Aspose.Words zu verwenden?

A: Um ein erweitertes Feld in ein Word-Dokument einzufügen, ohne den Document Builder in Aspose.Words zu verwenden, können Sie die folgenden Schritte ausführen:

1. Importieren Sie die Dokument- und Feldklasse aus dem Aspose.Words.Fields-Namespace.
2. Erstellen Sie eine Instanz von Document, indem Sie Ihr vorhandenes Dokument laden.
3. Verwenden Sie die InsertField-Methode, um ein erweitertes Feld einzufügen, indem Sie den erweiterten Feldcode angeben.
4. Speichern Sie das Dokument.

#### F: Wie erhalte ich das Ergebnis eines erweiterten Felds in einem Word-Dokument?

A: Um das Ergebnis eines erweiterten Felds in einem Word-Dokument abzurufen, können Sie die in der Field-Klasse verfügbare Result-Eigenschaft verwenden. Diese Eigenschaft gibt das berechnete Ergebnis des Feldes zurück.

#### F: Kann ich die Formel eines erweiterten Felds ändern, nachdem ich es in ein Word-Dokument eingefügt habe?

A: Ja, Sie können die Formel eines erweiterten Felds bearbeiten, nachdem Sie es in ein Word-Dokument eingefügt haben. Sie können dies tun, indem Sie auf die FieldCode-Eigenschaft der Field-Klasse zugreifen und die Formel aktualisieren, indem Sie den Formeltext ändern.