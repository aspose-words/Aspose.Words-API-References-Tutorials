---
title: Texteingabeformularfeld als Text exportieren
linktitle: Texteingabeformularfeld als Text exportieren
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Exportieren von Texteingabeformularfeldern als Nur-Text mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Texteingabeformularfelder mit Aspose.Words für .NET als einfachen Text zu exportieren. Mit dieser Funktion können Sie Texteingabeformularfelder als lesbaren Text exportieren, anstatt sie als HTML-Eingabeelemente zu exportieren.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das zu exportierende Dokument. Verwenden Sie den folgenden Code, um das Dokument aus einem angegebenen Verzeichnis zu laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Dieser Code erstellt eine Instanz von`Document` durch Laden des Dokuments aus dem angegebenen Verzeichnis.

## Schritt 3: Konfigurieren der HTML-Backup-Optionen

Jetzt konfigurieren wir die HTML-Speicheroptionen, um Texteingabeformularfelder als einfachen Text zu exportieren. Verwenden Sie den folgenden Code:

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

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions`und legt die fest`ExportTextInputFormFieldAsText` Option zu`true`um Texteingabeformularfelder als einfachen Text zu exportieren. Darüber hinaus gibt es den Ordner an, in dem die extrahierten Bilder gespeichert werden.

## Schritt 4: Konvertieren und Speichern des Dokuments in HTML

Abschließend konvertieren wir das Dokument mithilfe der zuvor konfigurierten HTML-Speicheroptionen in HTML. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML, indem er Texteingabeformularfelder als einfachen Text exportiert und die exportierte HTML-Datei im angegebenen Verzeichnis speichert.

### Beispielquellcode für „Texteingabeformularfeld als Text exportieren“ mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
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

 Stellen Sie sicher, dass Sie den richtigen Pfad zum Dokumentenverzeichnis im angeben`dataDir` Variable.