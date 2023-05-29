---
title: Dokument beim Ersetzen einfügen
linktitle: Dokument beim Ersetzen einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument beim Ersetzen einfügen.
type: docs
weight: 10
url: /de/net/clone-and-combine-documents/insert-document-at-replace/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie beim Ersetzen mithilfe der Funktion „Dokument beim Ersetzen einfügen“ von Aspose.Words für .NET ein Dokument in ein anderes Dokument einfügen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und das Einfügen des Dokuments durchzuführen.

## Schritt 1: Laden des Hauptdokuments

Geben Sie zunächst das Verzeichnis für Ihre Dokumente an und laden Sie das Hauptdokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Schritt 2: Such- und Ersetzungsoptionen konfigurieren

Jetzt konfigurieren wir die Such- und Ersetzungsoptionen, indem wir die Suchrichtung und den Ersetzungsrückruf angeben, um ein Dokument in ein anderes Dokument einzufügen. Hier ist wie:

```csharp
//Konfigurieren Sie Such- und Ersetzungsoptionen.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Schritt 3: Aufruf der Ersetzungsmethode

Wir rufen nun die Methode „replace“ auf, um mithilfe der konfigurierten Optionen den angegebenen Text zu suchen und durch eine leere Zeichenfolge zu ersetzen. Hier ist wie:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Beispielquellcode für „Dokument beim Ersetzen einfügen“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Dokument einfügen“ beim Ersetzen von Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Legen Sie Such- und Ersetzungsoptionen fest.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Rufen Sie die Ersetzungsmethode auf.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```