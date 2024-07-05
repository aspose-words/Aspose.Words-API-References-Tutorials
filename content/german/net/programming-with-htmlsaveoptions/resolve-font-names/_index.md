---
title: Schriftnamen auflösen
linktitle: Schriftnamen auflösen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Beheben fehlender Schriftnamen bei der Konvertierung in HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/resolve-font-names/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um fehlende Schriftnamen mit Aspose.Words für .NET aufzulösen. Mit dieser Funktion können Sie fehlende Schriftnamen automatisch auflösen, wenn Sie ein Dokument in HTML konvertieren.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das zu verarbeitende Dokument. Verwenden Sie den folgenden Code, um das Dokument aus einem angegebenen Verzeichnis zu laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Dieser Code erstellt eine Instanz von`Document` durch Laden des Dokuments aus dem angegebenen Verzeichnis.

## Schritt 3: Konfigurieren der HTML-Sicherungsoptionen

Nun konfigurieren wir die HTML-Speicheroptionen, um fehlende Schriftnamen während der Konvertierung aufzulösen. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions`und setzt den`ResolveFontNames` Möglichkeit,`true`um fehlende Schriftnamen bei der Konvertierung in HTML zu beheben. Außerdem`PrettyFormat` ist auf`true` um schön formatierten HTML-Code zu erhalten.

## Schritt 4: Konvertieren und Speichern des Dokuments im HTML-Format

Zum Schluss konvertieren wir das Dokument in HTML, indem wir die zuvor konfigurierten HTML-Speicheroptionen verwenden. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML, indem er fehlende Schriftnamen automatisch auflöst und die konvertierte HTML-Datei im angegebenen Verzeichnis speichert.

### Beispielquellcode zum Auflösen von Schriftnamen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Achten Sie darauf, den korrekten Pfad zum Dokumentenverzeichnis im`dataDir` Variable.