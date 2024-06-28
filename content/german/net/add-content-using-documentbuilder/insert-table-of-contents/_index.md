---
title: Inhaltsverzeichnis in Word-Dokument einfügen
linktitle: Inhaltsverzeichnis in Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Inhaltsverzeichnis in Word einfügen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Dokumentennavigation.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-table-of-contents/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET effizient ein Inhaltsverzeichnis (TOC) zu Ihren Word-Dokumenten hinzufügen. Diese Funktion ist für die Organisation und Navigation in langen Dokumenten unerlässlich, verbessert die Lesbarkeit und bietet einen schnellen Überblick über Dokumentabschnitte.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundlegendes Verständnis von C# und .NET Framework.
- Visual Studio ist auf Ihrem Computer installiert.
-  Aspose.Words für .NET-Bibliothek. Wenn Sie es noch nicht installiert haben, können Sie es hier herunterladen[Hier](https://releases.aspose.com/words/net/).

## Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces in Ihr C#-Projekt:

```csharp
using Aspose.Words;
using Aspose.Words.Builder;
using Aspose.Words.Fields;
using Aspose.Words.Tables;
```

Lassen Sie uns den Prozess in klare Schritte unterteilen:

## Schritt 1: Initialisieren Sie das Aspose.Words-Dokument und den DocumentBuilder

 Initialisieren Sie zunächst ein neues Aspose.Words`Document` Objekt und a`DocumentBuilder` arbeiten mit:

```csharp
// Initialisieren Sie Document und DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie das Inhaltsverzeichnis ein

 Fügen Sie nun das Inhaltsverzeichnis mit ein`InsertTableOfContents` Methode:

```csharp
// Inhaltsverzeichnis einfügen
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Schritt 3: Dokumentinhalt auf einer neuen Seite starten

Um eine ordnungsgemäße Formatierung sicherzustellen, beginnen Sie den eigentlichen Dokumentinhalt auf einer neuen Seite:

```csharp
// Fügen Sie einen Seitenumbruch ein
builder.InsertBreak(BreakType.PageBreak);
```

## Schritt 4: Strukturieren Sie Ihr Dokument mit Überschriften

Organisieren Sie den Inhalt Ihres Dokuments mithilfe geeigneter Überschriftenstile:

```csharp
// Überschriftenstile festlegen
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Schritt 5: Aktualisieren und füllen Sie das Inhaltsverzeichnis

Aktualisieren Sie das Inhaltsverzeichnis, um die Dokumentstruktur widerzuspiegeln:

```csharp
// Aktualisieren Sie die Felder des Inhaltsverzeichnisses
doc.UpdateFields();
```

## Schritt 6: Speichern Sie das Dokument

Speichern Sie abschließend Ihr Dokument in einem angegebenen Verzeichnis:

```csharp
// Speichern Sie das Dokument
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
doc.Save(dataDir + "InsertTableOfContentsUsingAsposeWords.docx");
```

## Abschluss

Das Hinzufügen eines Inhaltsverzeichnisses mit Aspose.Words für .NET ist unkompliziert und verbessert die Benutzerfreundlichkeit Ihrer Dokumente erheblich. Wenn Sie diese Schritte befolgen, können Sie komplexe Dokumente effizient organisieren und durch sie navigieren.

## FAQs

### Kann ich das Erscheinungsbild des Inhaltsverzeichnisses anpassen?
Ja, Sie können das Erscheinungsbild und Verhalten des Inhaltsverzeichnisses mithilfe von Aspose.Words für .NET-APIs anpassen.

### Unterstützt Aspose.Words die automatische Aktualisierung von Feldern?
Ja, mit Aspose.Words können Sie Felder wie das Inhaltsverzeichnis dynamisch basierend auf Dokumentänderungen aktualisieren.

### Kann ich mehrere Inhaltsverzeichnisse in einem einzigen Dokument erstellen?
Aspose.Words unterstützt die Generierung mehrerer Inhaltsverzeichnisse mit unterschiedlichen Einstellungen in einem einzigen Dokument.

### Ist Aspose.Words mit verschiedenen Versionen von Microsoft Word kompatibel?
Ja, Aspose.Words gewährleistet die Kompatibilität mit verschiedenen Versionen von Microsoft Word-Formaten.

### Wo finde ich weitere Hilfe und Unterstützung für Aspose.Words?
Weitere Unterstützung finden Sie unter[Aspose.Words-Forum](https://forum.aspose.com/c/words/8) oder schauen Sie sich die an[offizielle Dokumentation](https://reference.aspose.com/words/net/).