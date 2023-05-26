---
title: Roundtrip-Informationen exportieren
linktitle: Roundtrip-Informationen exportieren
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Exportieren von Roundtrip-Informationen beim Speichern eines Dokuments als HTML mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Roundtrip-Informationen aus einem Dokument mit Aspose.Words für .NET zu exportieren. Mit dieser Funktion können Sie Roundtrip-Informationen in die exportierte HTML-Datei einschließen, wodurch es einfacher wird, am Originaldokument vorgenommene Änderungen abzurufen.

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

Jetzt konfigurieren wir die HTML-Speicheroptionen, um die Roundtrip-Informationen des Dokuments zu exportieren. Verwenden Sie den folgenden Code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Dieser Code erstellt eine Instanz von`HtmlSaveOptions`und legt die fest`ExportRoundtripInformation` Option zu`true` um beim Exportieren Roundtrip-Informationen einzubeziehen.

## Schritt 4: Konvertieren und Speichern des Dokuments in HTML

Abschließend konvertieren wir das Dokument mithilfe der zuvor konfigurierten HTML-Speicheroptionen in HTML. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Dieser Code konvertiert das Dokument einschließlich der Roundtrip-Informationen in HTML und speichert die exportierte HTML-Datei im angegebenen Verzeichnis.

### Beispielquellcode für den Export von Roundtrip-Informationen mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Stellen Sie sicher, dass Sie den richtigen Pfad zum Dokumentenverzeichnis im angeben`dataDir` Variable.