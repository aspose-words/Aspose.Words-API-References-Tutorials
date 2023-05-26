---
title: Text in der Fußzeile ersetzen
linktitle: Text in der Fußzeile ersetzen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text in der Fußzeile von Word-Dokumenten ersetzen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/replace-text-in-footer/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Text in Fußzeile ersetzen“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie bestimmten Text in den Fußzeilen von Word-Dokumenten suchen und ersetzen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Laden Sie das Dokument

Bevor wir mit der Textersetzung in der Fußzeile beginnen, müssen wir das Dokument in Aspose.Words für .NET laden. Dies kann mit der erfolgen`Document` Klasse und Angabe des Dokumentdateipfads:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

## Schritt 2: Greifen Sie auf die Fußzeile zu

 Sobald das Dokument geladen ist, müssen wir auf die Fußzeile zugreifen, um die Textersetzung durchzuführen. In unserem Beispiel verwenden wir die`HeadersFooters` Eigenschaft des ersten Abschnitts des Dokuments, um die Sammlung von Kopf-/Fußzeilen abzurufen. Als nächstes wählen wir die Hauptfußzeile mit aus`HeaderFooterType.FooterPrimary` Index:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

## Schritt 3: Such- und Ersetzungsoptionen konfigurieren

 Jetzt konfigurieren wir die Such- und Ersetzungsoptionen mithilfe von a`FindReplaceOptions` Objekt. In unserem Beispiel setzen wir`MatchCase` Zu`false` Groß-/Kleinschreibung bei der Suche ignorieren und`FindWholeWordsOnly` Zu`false` um das Suchen und Ersetzen von Wortteilen zu ermöglichen:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

## Schritt 4: Ersetzen Sie den Text in der Fußzeile

 Wir benutzen das`Range.Replace` Methode zum Durchführen einer Textersetzung in der Fußzeile. In unserem Beispiel ersetzen wir den Ausdruck „(C) 2006 Aspose Pty Ltd.“ durch „Copyright (C) 2020 by Aspose Pty Ltd.“ :

```csharp
footer

.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

## Schritt 5: Speichern Sie das bearbeitete Dokument

 Abschließend speichern wir das geänderte Dokument mithilfe von in einem angegebenen Verzeichnis`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
```

### Beispielquellcode für Text in Fußzeile ersetzen mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung der Fußzeilentextersetzung mit Aspose.Words für .NET zu demonstrieren:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Footer.docx");

	HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
	HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

	FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };

	footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
            
        
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text in Fußzeile ersetzen“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um ein Dokument zu laden, auf die Fußzeile zuzugreifen, Such- und Ersetzungsoptionen zu konfigurieren, Textersetzungen durchzuführen und das bearbeitete Dokument zu speichern.
