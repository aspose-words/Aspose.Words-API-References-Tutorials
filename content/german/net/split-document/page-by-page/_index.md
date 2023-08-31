---
title: Word-Dokument nach Seite aufteilen
linktitle: Word-Dokument nach Seite aufteilen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Word-Dokument in einzelne Seiten aufteilen. Diese leistungsstarke API vereinfacht das Aufteilen von Dokumenten und macht es effizient und bequem.
type: docs
weight: 10
url: /de/net/split-document/page-by-page/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie ein Word-Dokument mithilfe der Dokumentverarbeitungsfunktion von Aspose.Words für .NET in einzelne Seiten aufteilen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und separate Dokumente für jede Seite zu erhalten.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst das Verzeichnis für Ihr Dokument an und laden Sie das Dokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Schritt 2: Aufteilen des Dokuments nach Seiten

Jetzt durchlaufen wir jede Seite des Dokuments und teilen das Dokument in einzelne Seiten auf. Hier ist wie:

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
// Der Pfad zum Dokumentenverzeichnis.
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

Mit diesem Code können Sie ein Word-Dokument mit Aspose.Words für .NET in einzelne Seiten aufteilen. Bei Bedarf können Sie auch einzelne Dokumente zusammenführen.

## Abschluss

Glückwunsch! Sie haben gelernt, wie Sie ein Word-Dokument mithilfe der Seite-für-Seite-Funktion von Aspose.Words für .NET in einzelne Seiten aufteilen. Indem Sie dem bereitgestellten Quellcode folgen, können Sie jede Seite eines Dokuments extrahieren und als separate Dokumente speichern.

Das Aufteilen eines Dokuments nach Seiten kann nützlich sein, wenn Sie mit bestimmten Seiten arbeiten oder Inhalte granular verteilen müssen. Aspose.Words für .NET bietet eine leistungsstarke API, die das Aufteilen von Dokumenten vereinfacht und so effizient und bequem macht.

Entdecken Sie gerne weitere Funktionen von Aspose.Words für .NET, um Ihre Dokumentverarbeitungsmöglichkeiten zu verbessern und Ihren Arbeitsablauf zu optimieren.

### FAQs

#### Wie kann ich ein Dokument mit Aspose.Words für .NET in mehrere Seiten aufteilen?

 Um ein Dokument in mehrere Seiten aufzuteilen, können Sie die verwenden`ExtractPages` Methode der Aspose.Words-API, um den Seitenbereich abzurufen. Durch Angabe der Startseite und der Anzahl der zu extrahierenden Seiten können Sie für jede Seite separate Dokumente erstellen.

#### Kann ich das Ausgabeformat anpassen, wenn ich ein Dokument nach Seiten aufteile?

Ja, Aspose.Words für .NET unterstützt verschiedene Ausgabeformate beim Teilen eines Dokuments nach Seiten. Sie können jede Seite je nach Ihren Anforderungen als separates Dokument in Formaten wie DOCX, PDF, HTML usw. speichern.

#### Kann ich ein Dokument nach einem bestimmten Seitenbereich aufteilen?

Absolut! Mit Aspose.Words für .NET können Sie ein Dokument nach einem bestimmten Seitenbereich aufteilen. Durch Anpassen der Startseite und der Anzahl der zu extrahierenden Seiten können Sie den Seitenbereich für die Aufteilung des Dokuments genau definieren.

#### Ist es möglich, die aufgeteilten Dokumente wieder in einem einzigen Dokument zusammenzuführen?

Ja, Sie können die geteilten Dokumente mithilfe der von Aspose.Words für .NET bereitgestellten Zusammenführungsfunktion wieder zu einem einzigen Dokument zusammenführen. Durch die Kombination der einzelnen Dokumente können Sie je nach Bedarf das Originaldokument neu erstellen oder ein neues Dokument mit einer anderen Struktur erstellen.