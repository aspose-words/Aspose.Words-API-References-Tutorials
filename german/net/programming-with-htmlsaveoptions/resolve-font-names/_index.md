---
title: Schriftartnamen auflösen
linktitle: Schriftartnamen auflösen
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Beheben fehlender Schriftartnamen bei der Konvertierung in HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/resolve-font-names/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um fehlende Schriftartnamen mit Aspose.Words für .NET aufzulösen. Mit dieser Funktion können Sie fehlende Schriftartnamen automatisch auflösen, wenn Sie ein Dokument in HTML konvertieren.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das zu verarbeitende Dokument. Verwenden Sie den folgenden Code, um das Dokument aus einem angegebenen Verzeichnis zu laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Dieser Code erstellt eine Instanz von`Document` durch Laden des Dokuments aus dem angegebenen Verzeichnis.

## Schritt 3: Konfigurieren der HTML-Backup-Optionen

Jetzt konfigurieren wir die HTML-Speicheroptionen, um fehlende Schriftartennamen während der Konvertierung aufzulösen. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions`und legt die fest`ResolveFontNames` Option zu`true` um fehlende Schriftartnamen bei der Konvertierung in HTML aufzulösen. Auch der`PrettyFormat` Option ist auf eingestellt`true` um schön formatierten HTML-Code zu erhalten.

## Schritt 4: Konvertieren und Speichern des Dokuments in HTML

Abschließend konvertieren wir das Dokument mithilfe der zuvor konfigurierten HTML-Speicheroptionen in HTML. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Dieser Code konvertiert das Dokument in HTML, indem er fehlende Schriftartnamen automatisch auflöst und die konvertierte HTML-Datei im angegebenen Verzeichnis speichert.

### Beispielquellcode für das Auflösen von Schriftartnamen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Stellen Sie sicher, dass Sie den richtigen Pfad zum Dokumentenverzeichnis im angeben`dataDir` Variable.