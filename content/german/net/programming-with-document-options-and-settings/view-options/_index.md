---
title: Optionen anzeigen
linktitle: Optionen anzeigen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Konfigurieren von Dokumentanzeigeoptionen mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/view-options/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Anzeigeoptionen mit Aspose.Words für .NET zu konfigurieren. Mit dieser Funktion können Sie den Ansichtsmodus und die Zoomstufe in einem Dokument anpassen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, für das wir die Anzeigeoptionen konfigurieren möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Anzeigeoptionen konfigurieren

Nun konfigurieren wir die Anzeigeoptionen für das Dokument. Verwenden Sie den folgenden Code, um den Anzeigemodus und die Zoomstufe festzulegen:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Dieser Code setzt den Ansichtsmodus auf „PageLayout“ und die Zoomstufe auf 50 %.

### Beispielquellcode für Ansichtsoptionen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben nun gelernt, wie Sie Dokumentanzeigeoptionen mit Aspose.Words für .NET konfigurieren. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie die Anzeige Ihrer eigenen Dokumente ganz einfach anpassen.