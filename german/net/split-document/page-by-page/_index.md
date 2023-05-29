---
title: Seite für Seite
linktitle: Seite für Seite
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der Aspose.Words Page by Page-Funktion für .NET
type: docs
weight: 10
url: /de/net/split-document/page-by-page/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie ein Word-Dokument mithilfe der Seite-für-Seite-Funktion von Aspose.Words für .NET in einzelne Seiten aufteilen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und separate Dokumente für jede Seite zu erhalten.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst das Verzeichnis für Ihr Dokument an und laden Sie das Dokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Schritt 2: Teilen Sie das Dokument nach Seiten auf

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

## Schritt 3: Dokumente zusammenführen

Sobald Sie für jede Seite separate Dokumente haben, können Sie diese bei Bedarf zusammenführen. Hier ist wie:

```csharp
MergeDocuments();
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


MergeDocuments();
```

Mit diesem Code können Sie ein Word-Dokument mit Aspose.Words für .NET in einzelne Seiten aufteilen. Bei Bedarf können Sie auch einzelne Dokumente zusammenführen.

