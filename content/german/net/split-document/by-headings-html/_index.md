---
title: Word-Dokument nach Überschriften aufteilen (HTML)
linktitle: Nach Überschriften HTML
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes des geteilten Word-Dokuments anhand der HTML-Überschriftfunktion von Aspose.Words für .NET
type: docs
weight: 10
url: /de/net/split-document/by-headings-html/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie ein Word-Dokument mithilfe der Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET in kleinere Teile aufteilen. Befolgen Sie die nachstehenden Schritte, um den Quellcode zu verstehen und separate HTML-Dokumente basierend auf Überschriften zu erstellen.

## Schritt 1: Dokument einlegen

Geben Sie zunächst das Verzeichnis für Ihr Dokument an und laden Sie das Dokument in ein Dokumentobjekt. So geht's:

```csharp
//Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Schritt 2: Aufteilen des Dokuments nach Überschriften im HTML-Format

Jetzt legen wir Speicheroptionen fest, um das Dokument basierend auf der Überschrift im HTML-Format in kleinere Teile aufzuteilen. So geht's:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Teilen Sie das Dokument in kleinere Teile auf, in diesem Fall trennen Sie es nach Titel.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Beispielquellcode für By Headings HTML mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Teilen Sie ein Dokument in kleinere Teile auf, in diesem Fall nach Überschrift.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Mit diesem Code können Sie ein Word-Dokument mit Aspose.Words für .NET basierend auf Überschriften in kleinere Teile aufteilen. Sie können dann für jeden Teil separate HTML-Dokumente generieren.

## Abschluss

 In diesem Tutorial haben wir gelernt, wie man ein Word-Dokument mithilfe der Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET in kleinere Teile aufteilt. Durch Angabe der`DocumentSplitCriteria` als`HeadingParagraph` im`HtmlSaveOptions`konnten wir separate HTML-Dokumente basierend auf den im Originaldokument vorhandenen Überschriften generieren.

Das Aufteilen eines Dokuments nach Überschriften kann für die Organisation und Verwaltung von Inhalten nützlich sein, insbesondere bei großen Dokumenten mit mehreren Abschnitten. Aspose.Words für .NET bietet eine zuverlässige und effiziente Lösung für die Handhabung des Dokumentaufteilens und die Generierung von Ausgaben in verschiedenen Formaten.

Erkunden Sie die zusätzlichen Funktionen und Optionen von Aspose.Words für .NET, um Ihre Dokumentverarbeitungsfunktionen weiter zu verbessern und Ihren Arbeitsablauf zu optimieren.

### FAQs

#### Wie kann ich mit Aspose.Words für .NET ein Word-Dokument basierend auf Überschriften in kleinere Teile aufteilen?

 Um ein Word-Dokument anhand von Überschriften aufzuteilen, können Sie die Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET verwenden. Folgen Sie dem bereitgestellten Quellcode und setzen Sie die`DocumentSplitCriteria` Zu`HeadingParagraph` im`HtmlSaveOptions` Objekt. Dadurch wird das Dokument bei jeder Überschrift in kleinere Teile aufgeteilt.

#### In welche Formate kann ich das Word-Dokument aufteilen?

 Der bereitgestellte Quellcode demonstriert das Aufteilen des Word-Dokuments in kleinere Teile im HTML-Format. Aspose.Words für .NET unterstützt jedoch verschiedene Ausgabeformate, darunter DOCX, PDF, EPUB und mehr. Sie können den Code ändern und das gewünschte Ausgabeformat im`HtmlSaveOptions` Objekt entsprechend.

#### Kann ich zum Aufteilen des Dokuments andere Kriterien auswählen?

Ja, Sie können je nach Ihren Anforderungen ein anderes Kriterium für die Aufteilung des Dokuments auswählen. Aspose.Words für .NET bietet mehrere Kriterienoptionen, wie z. B.`HeadingParagraph`, `Page`, `Section` und mehr. Ändern Sie die`DocumentSplitCriteria` Eigentum in der`HtmlSaveOptions` Objekt, um die entsprechenden Kriterien für die Aufteilung auszuwählen.

#### Wie kann ich das Ausgabe-HTML für die aufgeteilten Teile anpassen?

 Mit Aspose.Words für .NET können Sie die Ausgabe-HTML für die geteilten Teile anpassen, indem Sie zusätzliche Optionen in der`HtmlSaveOptions` Objekt. Sie können verschiedene Aspekte wie CSS-Stile, Bilder, Schriftarten und mehr steuern. Weitere Informationen zum Anpassen der HTML-Ausgabe finden Sie in der Aspose.Words-Dokumentation.

#### Kann ich das Dokument nach mehreren Kriterien aufteilen?

 Ja, Sie können das Dokument anhand mehrerer Kriterien aufteilen, indem Sie die Kriterienoptionen entsprechend kombinieren. Sie können das Dokument beispielsweise sowohl nach Überschrift als auch nach Seite aufteilen, indem Sie die`DocumentSplitCriteria`Eigentum an`HeadingParagraph | Page`. Dadurch wird das Dokument an jeder Überschrift und jeder Seite aufgeteilt, wobei basierend auf beiden Kriterien kleinere Teile erstellt werden.