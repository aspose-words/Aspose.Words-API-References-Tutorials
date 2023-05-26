---
title: Entkomme Uri
linktitle: Entkomme Uri
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Entkommen von Uri mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/escape-uri/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Uri-Escape-Funktion mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie Hyperlinks mit maskierten URI in ein Dokument einfügen.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und einen DocumentBuilder

 Als nächstes müssen wir ein neues erstellen`Document` Objekt und a`DocumentBuilder` Objekt zum Erstellen des Dokuments.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Fügen Sie Hyperlinks mit maskiertem Uri ein

 Benutzen Sie die`InsertHyperlink` Methode der`DocumentBuilder`Objekt zum Einfügen von Hyperlinks in das Dokument. Uri muss mit dem maskiert werden`Uri.EscapeUriString` Funktion zur Vermeidung von Formatfehlern.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## Schritt 4: Speichern Sie das Dokument als PDF

 Schließlich können wir das Dokument mit dem als PDF speichern`Save` Methode der`Document` Objekt. Geben Sie den Namen der Ausgabedatei an.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Das ist alles ! Sie haben mit Aspose.Words für .NET erfolgreich Hyperlinks mit maskierten URIs in ein Dokument eingefügt.

### Beispielquellcode für Uri-Escape mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```
