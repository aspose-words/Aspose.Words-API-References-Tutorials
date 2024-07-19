---
title: Texteingabe-Formularfeld als Text exportieren
linktitle: Texteingabe-Formularfeld als Text exportieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Exportieren von Text-Eingabeformularfeldern als Klartext mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Texteingabeformularfelder mit Aspose.Words für .NET als einfachen Text zu exportieren. Mit dieser Funktion können Sie Texteingabeformularfelder als lesbaren Text exportieren, anstatt sie als HTML-Eingabeelemente zu exportieren.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das zu exportierende Dokument. Verwenden Sie den folgenden Code, um das Dokument aus einem angegebenen Verzeichnis zu laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Dieser Code erstellt eine Instanz von`Document` durch Laden des Dokuments aus dem angegebenen Verzeichnis.

## Schritt 3: Konfigurieren der HTML-Sicherungsoptionen

Nun konfigurieren wir die HTML-Speicheroptionen, um Texteingabeformularfelder als einfachen Text zu exportieren. Verwenden Sie den folgenden Code:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// Der angegebene Ordner muss vorhanden und leer sein.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions` und setzt den`ExportTextInputFormFieldAsText` Möglichkeit,`true` um Texteingabeformularfelder als einfachen Text zu exportieren. Darüber hinaus gibt es den Ordner an, in dem die extrahierten Bilder gespeichert werden.

## Schritt 4: Konvertieren und Speichern des Dokuments im HTML-Format

Zum Schluss konvertieren wir das Dokument in HTML, indem wir die zuvor konfigurierten HTML-Speicheroptionen verwenden. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML, indem er Texteingabeformularfelder als einfachen Text exportiert und die exportierte HTML-Datei im angegebenen Verzeichnis speichert.

### Beispielquellcode zum Exportieren von Texteingabeformularfeldern als Text mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// Der angegebene Ordner muss vorhanden sein und sollte leer sein.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Legen Sie eine Option fest, um Formularfelder als einfachen Text und nicht als HTML-Eingabeelemente zu exportieren.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Achten Sie darauf, den korrekten Pfad zum Dokumentenverzeichnis im`dataDir` Variable.