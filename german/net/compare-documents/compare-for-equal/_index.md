---
title: Vergleichen Sie für gleich
linktitle: Vergleichen Sie für gleich
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der Funktion „Compare for Equals“ mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/compare-documents/compare-for-equal/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Funktion „Vergleichen auf Gleichheit“ mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

## Schritt 1: Dokumentenvergleich

 Laden Sie zunächst zwei Dokumente zum Vergleichen. In diesem Beispiel verwenden wir die`Clone()` Methode zum Erstellen einer Kopie des Originaldokuments. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## Schritt 2: Dokumentenvergleich

 Wir werden jetzt das verwenden`Compare()` Methode zum Vergleichen der beiden Dokumente. Diese Methode markiert die Änderungen im Originaldokument. Hier ist wie:

```csharp
// Vergleichen Sie die Dokumente
docA.Compare(docB, "user", DateTime.Now);

// Prüfen Sie, ob die Dokumente gleich sind
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Beispielquellcode für Compare For Equal mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Compare for Equals“ mit Aspose.Words für .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA enthält nun Änderungen als Revisionen.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Mit diesem Code können Sie mit Aspose.Words für .NET zwei Dokumente vergleichen und feststellen, ob sie identisch sind.

