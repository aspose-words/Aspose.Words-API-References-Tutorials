---
title: Word-Dokument nach Überschriften aufteilen HTML
linktitle: Nach Überschriften HTML
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes des Split-Word-Dokuments By Heading HTML-Funktion von Aspose.Words für .NET
type: docs
weight: 10
url: /de/net/split-document/by-headings-html/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie ein Word-Dokument mithilfe der Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET in kleinere Teile aufteilen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und separate HTML-Dokumente basierend auf der Überschrift zu generieren.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst das Verzeichnis für Ihr Dokument an und laden Sie das Dokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Schritt 2: Unterteilen des Dokuments nach Überschrift im HTML-Format

Jetzt legen wir die Speicheroptionen fest, um das Dokument basierend auf der Überschrift im HTML-Format in kleinere Teile aufzuteilen. Hier ist wie:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Teilen Sie das Dokument in kleinere Teile auf, in diesem Fall nach Titel.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Beispielquellcode für By Headings HTML mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Teilen Sie ein Dokument in kleinere Teile auf, in diesem Fall nach Überschrift.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Mit diesem Code können Sie ein Word-Dokument mithilfe von Aspose.Words für .NET basierend auf Überschriften in kleinere Teile aufteilen. Anschließend können Sie für jeden Teil separate HTML-Dokumente generieren.

## Abschluss

 In diesem Tutorial haben wir gelernt, wie man ein Word-Dokument mithilfe der Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET in kleinere Teile aufteilt. Durch die Angabe der`DocumentSplitCriteria` als`HeadingParagraph` im`HtmlSaveOptions`konnten wir separate HTML-Dokumente basierend auf den im Originaldokument vorhandenen Überschriften generieren.

Das Aufteilen eines Dokuments nach Überschriften kann zum Organisieren und Verwalten von Inhalten nützlich sein, insbesondere bei großen Dokumenten mit mehreren Abschnitten. Aspose.Words für .NET bietet eine zuverlässige und effiziente Lösung für die Dokumentenaufteilung und die Generierung von Ausgaben in verschiedenen Formaten.

Erkunden Sie gerne die zusätzlichen Funktionen und Optionen von Aspose.Words für .NET, um Ihre Dokumentverarbeitungsfähigkeiten weiter zu verbessern und Ihren Arbeitsablauf zu optimieren.

### FAQs

#### Wie kann ich mit Aspose.Words für .NET ein Word-Dokument basierend auf Überschriften in kleinere Teile aufteilen?

 Um ein Word-Dokument anhand von Überschriften aufzuteilen, können Sie die Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET verwenden. Folgen Sie dem bereitgestellten Quellcode und legen Sie fest`DocumentSplitCriteria` Zu`HeadingParagraph` im`HtmlSaveOptions` Objekt. Dadurch wird das Dokument an jeder Überschrift in kleinere Teile aufgeteilt.

#### In welche Formate kann ich das Word-Dokument aufteilen?

Der bereitgestellte Quellcode demonstriert die Aufteilung des Word-Dokuments in kleinere Teile im HTML-Format. Aspose.Words für .NET unterstützt jedoch verschiedene Ausgabeformate, darunter DOCX, PDF, EPUB und mehr. Sie können den Code ändern und das gewünschte Ausgabeformat im angeben`HtmlSaveOptions` entsprechend widersprechen.

#### Kann ich ein anderes Kriterium für die Aufteilung des Dokuments wählen?

 Ja, Sie können je nach Ihren Anforderungen ein anderes Kriterium für die Aufteilung des Dokuments auswählen. Aspose.Words für .NET bietet mehrere Kriterienoptionen, wie z`HeadingParagraph`, `Page`, `Section` , und mehr. Modifiziere den`DocumentSplitCriteria` Eigentum in der`HtmlSaveOptions` Objekt, um die geeigneten Kriterien für die Aufteilung auszuwählen.

#### Wie kann ich den Ausgabe-HTML für die geteilten Teile anpassen?

 Mit Aspose.Words für .NET können Sie den Ausgabe-HTML für die geteilten Teile anpassen, indem Sie zusätzliche Optionen in angeben`HtmlSaveOptions` Objekt. Sie können verschiedene Aspekte wie CSS-Stile, Bilder, Schriftarten und mehr steuern. Weitere Informationen zum Anpassen der HTML-Ausgabe finden Sie in der Aspose.Words-Dokumentation.

#### Kann ich das Dokument nach mehreren Kriterien aufteilen?

 Ja, Sie können das Dokument anhand mehrerer Kriterien aufteilen, indem Sie die Kriterienoptionen entsprechend kombinieren. Beispielsweise können Sie das Dokument sowohl nach Überschrift als auch nach Seite aufteilen, indem Sie festlegen`DocumentSplitCriteria`Eigentum zu`HeadingParagraph | Page`. Dadurch wird das Dokument an jeder Überschrift und an jeder Seite aufgeteilt, sodass kleinere Teile entstehen, die auf beiden Kriterien basieren.