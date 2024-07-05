---
title: Dokumentseiten-Setup
linktitle: Dokumentseiten-Setup
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Einrichten eines Dokumentlayouts mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/document-page-setup/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um das Dokumentlayout mit Aspose.Words für .NET zu konfigurieren. Mit dieser Funktion können Sie den Layoutmodus, die Anzahl der Zeichen pro Zeile und die Anzahl der Zeilen pro Seite festlegen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, das wir konfigurieren möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Einrichten des Layouts

Konfigurieren wir nun das Dokumentlayout. Verwenden Sie den folgenden Code, um den Layoutmodus, die Anzahl der Zeichen pro Zeile und die Anzahl der Zeilen pro Seite festzulegen:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Dieser Code setzt den Layoutmodus auf „Raster“ und gibt anschließend die Anzahl der Zeichen pro Zeile und die Anzahl der Zeilen pro Seite an.

### Beispielquellcode für die Dokumentseiteneinrichtung mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Legen Sie den Layoutmodus für einen Abschnitt fest, um das Rasterverhalten des Dokuments zu definieren.
	// Beachten Sie, dass die Registerkarte „Dokumentraster“ im Dialogfeld „Seite einrichten“ von MS Word sichtbar wird.
	// wenn eine beliebige asiatische Sprache als Bearbeitungssprache definiert ist.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben nun gelernt, wie Sie das Layout eines Dokuments mit Aspose.Words für .NET konfigurieren. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie das Layout Ihrer eigenen Dokumente ganz einfach anpassen.