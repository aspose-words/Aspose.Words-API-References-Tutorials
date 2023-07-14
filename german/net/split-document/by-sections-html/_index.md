---
title: Word-Dokument nach HTML-Abschnitten aufteilen
linktitle: Nach Abschnitten HTML
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie anhand eines vollständigen Codebeispiels, wie Sie ein Word-Dokument mit Aspose.Words für .NET in HTML-Abschnitte aufteilen.
type: docs
weight: 10
url: /de/net/split-document/by-sections-html/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie ein Word-Dokument mithilfe der Funktion „Nach HTML-Abschnitten“ von Aspose.Words für .NET in separate Abschnitte im HTML-Format aufteilen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und für jeden Abschnitt separate HTML-Dokumente zu generieren.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst das Verzeichnis für Ihr Dokument an und laden Sie das Dokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Schritt 2: Unterteilen des Dokuments in Abschnitte im HTML-Format

Jetzt legen wir die Speicheroptionen fest, um das Dokument im HTML-Format in Abschnitte zu unterteilen. So geht's:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Beispielquellcode für By Sections HTML mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Nach HTML-Abschnitten“ von Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

Mit diesem Code können Sie ein Word-Dokument mit Aspose.Words für .NET in separate Abschnitte im HTML-Format aufteilen.

Jetzt können Sie für jeden Abschnitt des Ausgangsdokuments separate HTML-Dokumente generieren.

## Abschluss

In diesem Tutorial haben wir gelernt, wie man ein Word-Dokument mithilfe der Funktion „Nach HTML-Abschnitten“ von Aspose.Words für .NET in separate Abschnitte im HTML-Format aufteilt. Indem Sie dem bereitgestellten Quellcode folgen, können Sie für jeden Abschnitt des Originaldokuments individuelle HTML-Dokumente generieren.

Das Unterteilen eines Dokuments in Abschnitte kann für verschiedene Zwecke nützlich sein, z. B. zum Erstellen von Webseiten, zum Extrahieren bestimmter Inhalte oder zum Organisieren von Informationen. Aspose.Words für .NET bietet eine leistungsstarke API, mit der Sie Word-Dokumente entsprechend Ihren Anforderungen bearbeiten und anpassen können.

Entdecken Sie die zusätzlichen Funktionen von Aspose.Words für .NET, um Ihre Möglichkeiten zur Dokumentenverarbeitung weiter zu verbessern und Ihren Arbeitsablauf zu verbessern.

### FAQs

#### Wie kann ich das HTML-Ausgabeformat anpassen?

Aspose.Words für .NET bietet verschiedene Optionen zum Anpassen des HTML-Ausgabeformats. Sie können den Stil, die Schriftarteinstellungen, die Bildauflösung und viele andere Aspekte des HTML-Dokuments ändern, indem Sie die Speicheroptionen anpassen. Ausführliche Informationen zu den verfügbaren Optionen und deren Verwendung finden Sie in der Dokumentation zu Aspose.Words für .NET.

#### Kann ich das Dokument nach anderen Kriterien aufteilen?

Ja, neben der Verwendung von Abschnittsumbrüchen als Aufteilungskriterium bietet Aspose.Words für .NET weitere Optionen wie Absatzumbrüche, Überschriftenstile oder bestimmte Inhalte als Kriterien für die Aufteilung des Dokuments. Sie können anhand Ihrer Anforderungen die am besten geeigneten Kriterien auswählen und den Code entsprechend anpassen.

#### Ist es möglich, das Dokument in andere Formate als HTML aufzuteilen?

Ja, Aspose.Words für .NET unterstützt die Aufteilung eines Dokuments in verschiedene Formate, einschließlich PDF, Nur-Text, Bilder und mehr. Sie können die Speicheroptionen ändern, um das gewünschte Ausgabeformat zu generieren. Weitere Informationen zu den verfügbaren Formaten und deren Angabe in den Speicheroptionen finden Sie in der Dokumentation zu Aspose.Words für .NET.

#### Kann ich mehrere Dokumente gleichzeitig teilen?

Ja, Sie können den Aufteilungsprozess auf mehrere Dokumente gleichzeitig anwenden, indem Sie eine Sammlung von Dokumenten durchlaufen und den Aufteilungscode für jedes Dokument einzeln ausführen. Dadurch können Sie mehrere Dokumente effizient verarbeiten und für jedes einzelne separate Abschnitte erstellen.

#### Wie kann ich die Abschnitte wieder in einem einzigen Dokument zusammenführen?

Aspose.Words für .NET bietet auch Methoden zum Zusammenführen mehrerer Dokumente oder Abschnitte wieder in einem einzigen Dokument. Mithilfe dieser Zusammenführungsfunktionen können Sie die separat generierten Abschnitte kombinieren und ein einheitliches Dokument erstellen. Weitere Informationen zum Zusammenführen von Dokumenten oder Abschnitten finden Sie in der Dokumentation zu Aspose.Words für .NET.


