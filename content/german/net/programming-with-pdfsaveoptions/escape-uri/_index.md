---
title: Escape-URI im PDF-Dokument
linktitle: Escape-URI im PDF-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Escapen von URIs in PDF-Dokumenten mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/escape-uri/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zum Escapen von URIs in PDF-Dokumenten mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie Hyperlinks mit Escape-URIs in ein Dokument einfügen.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und einen DocumentBuilder

 Als nächstes müssen wir ein neues`Document` Objekt und ein`DocumentBuilder` Objekt, um das Dokument zu erstellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen von Hyperlinks mit Escape-URI

 Verwenden Sie die`InsertHyperlink` Methode der`DocumentBuilder` Objekt, um Hyperlinks in das Dokument einzufügen. URI muss mit dem`Uri.EscapeUriString` Funktion, um Formatfehler zu vermeiden.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## Schritt 4: Speichern Sie das Dokument als PDF

 Abschließend können wir das Dokument als PDF speichern mit dem`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateinamen an.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Das ist alles! Sie haben erfolgreich Hyperlinks mit Escape-URIs in ein Dokument mit Aspose.Words für .NET eingefügt.

### Beispielquellcode für Uri-Escape mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentverzeichnis.
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

In diesem Tutorial haben wir erläutert, wie Sie URIs in einem PDF-Dokument mit Aspose.Words für .NET maskieren. Durch das Maskieren von URIs können Sie Formatierungsfehler vermeiden und sicherstellen, dass Hyperlinks im PDF-Dokument richtig interpretiert und angezeigt werden. Befolgen Sie die beschriebenen Schritte, um Hyperlinks mit maskierten URIs in Ihr PDF-Dokument einzufügen. Achten Sie darauf, die Maskierung zu maskieren.

### Häufig gestellte Fragen

#### F: Was ist die Escape-URI in einem PDF-Dokument und warum ist sie wichtig?
A: Unter Escape-URI in einem PDF-Dokument versteht man die Methode, Sonderzeichen in einer URL in Escape-Sequenzen umzuwandeln, um Formatfehler zu vermeiden. Dies ist wichtig, da Sonderzeichen in einer URL die Struktur der URL stören und zu Fehlinterpretationen oder fehlerhafter Darstellung führen können. Durch das Escapen der Sonderzeichen garantieren wir, dass die URL im PDF-Dokument richtig interpretiert und angezeigt wird.

#### F: Wie kann ich Aspose.Words für .NET verwenden, um URIs in einem PDF-Dokument zu maskieren?
A: Um URIs in einem PDF-Dokument mit Aspose.Words für .NET zu escapen, folgen Sie diesen Schritten:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses.

 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`DocumentBuilder` Objekt, um das Dokument zu erstellen.

 Verwenden Sie die`InsertHyperlink` Methode der`DocumentBuilder` Objekt, um Hyperlinks in das Dokument einzufügen. Achten Sie darauf, die URI mit dem`Uri.EscapeUriString` Funktion, um Formatfehler zu vermeiden.

 Verwenden Sie die`Save` Methode der`Document` Objekt, um das Dokument im PDF-Format zu speichern, indem Sie den Namen der Ausgabedatei angeben.

#### F: Welche Vorteile bietet das Escapen von URIs in einem PDF-Dokument?
A: Die Vorteile der URI-Escape-Funktion in einem PDF-Dokument sind:

Vermeidung von Formatfehlern: Durch URI-Escaping werden durch Sonderzeichen in einer URL verursachte Formatfehler vermieden. So wird sichergestellt, dass die URL richtig interpretiert und im PDF-Dokument angezeigt wird.

Kompatibilität mit PDF-Readern: Escape-URIs werden von PDF-Readern im Allgemeinen gut unterstützt, was eine bessere Kompatibilität und ein konsistentes Benutzererlebnis gewährleistet.

#### F: Welche Sonderzeichen sollten in einer URI maskiert werden?
 A: Die Sonderzeichen, die in einer URI maskiert werden müssen, sind: Leerzeichen, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.