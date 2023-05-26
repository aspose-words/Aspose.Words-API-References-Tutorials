---
title: Legen Sie die Seiteneinrichtung und die Abschnittsformatierung fest
linktitle: Legen Sie die Seiteneinrichtung und die Abschnittsformatierung fest
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Einrichten des Layouts und der Abschnittsformatierung eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um das Layout und die Abschnittsformatierung mit Aspose.Words für .NET einzurichten. Mit dieser Funktion können Sie die Seitenausrichtung, die Ränder und das Papierformat festlegen.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Erstellen des Dokuments

In diesem Schritt erstellen wir ein neues Dokument. Verwenden Sie den folgenden Code, um das Dokument zu erstellen und den Konstruktor zu initialisieren:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem Sie das Dokument speichern möchten.

## Schritt 3: Layout einrichten und Dokument speichern

Jetzt konfigurieren wir das Dokumentlayout. Verwenden Sie den folgenden Code, um Ausrichtung, Ränder und Papiergröße festzulegen:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Dieser Code stellt die Seitenausrichtung auf Querformat, den linken Rand auf 50 und die Papiergröße auf 10 x 14 ein.

### Beispielquellcode zum Festlegen der Seiteneinrichtung und Abschnittsformatierung mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu dem Verzeichnis angeben, in dem Sie das Dokument speichern möchten`dataDir` Variable.

Sie haben jetzt erfahren, wie Sie das Layout und die Abschnittsformatierung eines Dokuments mit Aspose.Words für .NET konfigurieren. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie das Layout und die Formatierung Ihrer eigenen Dokumente ganz einfach anpassen.