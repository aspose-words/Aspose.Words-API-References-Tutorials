---
title: Escape-URI im PDF-Dokument
linktitle: Escape-URI im PDF-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Escapen von URIs in PDF-Dokumenten mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/escape-uri/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zum Escapen von URIs in PDF-Dokumenten mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie Hyperlinks mit maskierten URI in ein Dokument einfügen.

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

 Benutzen Sie die`InsertHyperlink` Methode der`DocumentBuilder` Objekt zum Einfügen von Hyperlinks in das Dokument. Uri muss mit dem maskiert werden`Uri.EscapeUriString` Funktion zur Vermeidung von Formatfehlern.

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

## Abschluss

In diesem Tutorial haben wir behandelt, wie man URIs in einem PDF-Dokument mit Aspose.Words für .NET maskiert. Durch das Escapen von URIs können Sie Formatierungsfehler vermeiden und sicherstellen, dass Hyperlinks korrekt interpretiert und im PDF-Dokument angezeigt werden. Befolgen Sie die beschriebenen Schritte, um Hyperlinks mit maskierten URIs in Ihr PDF-Dokument einzufügen. Entkommen Sie unbedingt.

### Häufig gestellte Fragen

#### F: Was ist der Escape-URI in einem PDF-Dokument und warum ist er wichtig?
A: Escape-URI in einem PDF-Dokument bezieht sich auf die Methode, Sonderzeichen in einer URL in Escape-Sequenzen umzuwandeln, um Formatfehler zu vermeiden. Dies ist wichtig, da Sonderzeichen in einer URL die Struktur der URL stören und zu Fehlinterpretationen oder fehlerhafter Darstellung führen können. Durch das Escapen der Sonderzeichen garantieren wir, dass die URL korrekt interpretiert und im PDF-Dokument angezeigt wird.

#### F: Wie kann ich Aspose.Words für .NET verwenden, um URIs in einem PDF-Dokument zu maskieren?
A: Um URIs in einem PDF-Dokument mit Aspose.Words für .NET zu maskieren, führen Sie die folgenden Schritte aus:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses.

 Erstellen Sie eine neue Instanz von`Document` Klasse und a`DocumentBuilder` Objekt zum Erstellen des Dokuments.

 Benutzen Sie die`InsertHyperlink` Methode der`DocumentBuilder` Objekt zum Einfügen von Hyperlinks in das Dokument. Stellen Sie sicher, dass Sie den URI mit maskieren`Uri.EscapeUriString` Funktion zur Vermeidung von Formatfehlern.

 Benutzen Sie die`Save` Methode der`Document` -Objekt, um das Dokument im PDF-Format zu speichern, indem Sie den Namen der Ausgabedatei angeben.

#### F: Welche Vorteile bietet das Escapen von URIs in einem PDF-Dokument?
A: Die Vorteile der URI-Escape-Funktion in einem PDF-Dokument sind:

Verhinderung von Formatfehlern: URI-Escape hilft, Formatfehler zu verhindern, die durch Sonderzeichen in einer URL verursacht werden, und stellt sicher, dass die URL korrekt interpretiert und im PDF-Dokument angezeigt wird.

Kompatibilität mit PDF-Readern: Escaped-URIs werden von PDF-Readern im Allgemeinen gut unterstützt, was eine bessere Kompatibilität und ein konsistentes Benutzererlebnis gewährleistet.

#### F: Welche Sonderzeichen sollten in einem URI maskiert werden?
 A: Die Sonderzeichen, die in einem URI maskiert werden müssen, sind: Leerzeichen, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.