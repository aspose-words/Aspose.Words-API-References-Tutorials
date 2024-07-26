---
title: Word-Dokument seitenweise aufteilen
linktitle: Word-Dokument seitenweise aufteilen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie ein Word-Dokument mit Aspose.Words für .NET in einzelne Seiten aufteilen. Diese leistungsstarke API vereinfacht das Aufteilen von Dokumenten und macht es effizient und bequem.
type: docs
weight: 10
url: /de/net/split-document/page-by-page/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie ein Word-Dokument mithilfe der Dokumentverarbeitungsfunktion von Aspose.Words für .NET in einzelne Seiten aufteilen. Befolgen Sie die nachstehenden Schritte, um den Quellcode zu verstehen und separate Dokumente für jede Seite zu erhalten.

## Schritt 1: Dokument einlegen

Geben Sie zunächst das Verzeichnis für Ihr Dokument an und laden Sie das Dokument in ein Dokumentobjekt. So geht's:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Schritt 2: Dokumentaufteilung nach Seiten

Jetzt durchlaufen wir jede Seite des Dokuments und teilen es in einzelne Seiten auf. So geht's:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Speichern Sie jede Seite als separates Dokument.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Beispielquellcode für Page By Page mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Page-by-Page-Funktion von Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Speichern Sie jede Seite als separates Dokument.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

Mit diesem Code können Sie ein Word-Dokument mithilfe von Aspose.Words für .NET in einzelne Seiten aufteilen. Bei Bedarf können Sie auch einzelne Dokumente zusammenführen.

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie ein Word-Dokument mithilfe der Funktion „Seite für Seite“ von Aspose.Words für .NET in einzelne Seiten aufteilen. Indem Sie dem bereitgestellten Quellcode folgen, können Sie jede Seite eines Dokuments extrahieren und als separate Dokumente speichern.

Das Aufteilen eines Dokuments nach Seiten kann nützlich sein, wenn Sie mit bestimmten Seiten arbeiten oder Inhalte granular verteilen müssen. Aspose.Words für .NET bietet eine leistungsstarke API, die das Aufteilen von Dokumenten vereinfacht und effizient und bequem macht.

Erkunden Sie die anderen von Aspose.Words für .NET angebotenen Funktionen, um Ihre Dokumentverarbeitungsfunktionen zu verbessern und Ihren Arbeitsablauf zu optimieren.

### FAQs

#### Wie kann ich ein Dokument mit Aspose.Words für .NET in mehrere Seiten aufteilen?

 Um ein Dokument in mehrere Seiten aufzuteilen, können Sie die`ExtractPages` Methode der Aspose.Words-API, um den Seitenbereich abzurufen. Indem Sie die Startseite und die Anzahl der zu extrahierenden Seiten angeben, können Sie für jede Seite separate Dokumente erstellen.

#### Kann ich das Ausgabeformat anpassen, wenn ich ein Dokument seitenweise aufteile?

Ja, Aspose.Words für .NET unterstützt verschiedene Ausgabeformate beim Aufteilen eines Dokuments nach Seiten. Sie können jede Seite als separates Dokument in Formaten wie DOCX, PDF, HTML und mehr speichern, je nach Ihren Anforderungen.

#### Kann ich ein Dokument nach einem bestimmten Seitenbereich aufteilen?

Absolut! Aspose.Words für .NET ermöglicht es Ihnen, ein Dokument nach einem bestimmten Seitenbereich aufzuteilen. Indem Sie die Startseite und die Anzahl der zu extrahierenden Seiten anpassen, können Sie den Seitenbereich für die Aufteilung des Dokuments genau definieren.

#### Ist es möglich, die aufgeteilten Dokumente wieder zu einem einzigen Dokument zusammenzuführen?

Ja, Sie können die geteilten Dokumente mithilfe der Zusammenführungsfunktion von Aspose.Words für .NET wieder zu einem einzigen Dokument zusammenführen. Durch die Kombination der einzelnen Dokumente können Sie das Originaldokument wiederherstellen oder je nach Bedarf ein neues Dokument mit einer anderen Struktur erstellen.