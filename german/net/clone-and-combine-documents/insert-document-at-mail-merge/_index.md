---
title: Dokument beim Seriendruck einfügen
linktitle: Dokument beim Seriendruck einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument beim Seriendruck in ein anderes einfügen.
type: docs
weight: 10
url: /de/net/clone-and-combine-documents/insert-document-at-mail-merge/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie beim Seriendruck mithilfe der Funktion „Dokument beim Seriendruck einfügen“ von Aspose.Words für .NET ein Dokument in ein anderes Dokument einfügen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und das Einfügen des Dokuments durchzuführen.

## Schritt 1: Laden des Hauptdokuments

Geben Sie zunächst das Verzeichnis für Ihre Dokumente an und laden Sie das Hauptdokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Schritt 2: Konfigurieren Sie den Serienbrief

Nun konfigurieren wir den Serienbrief und geben den Feld-Merge-Callback an, um ein Dokument in ein anderes Dokument einzufügen. Hier ist wie:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Schritt 3: Ausführen des Seriendrucks

Wir führen den Seriendruck durch, indem wir die Namen der Seriendruckfelder und die entsprechenden Daten angeben. Hier ist wie:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Beispielquellcode für „Dokument beim Seriendruck einfügen“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Dokument in Serienbrief einfügen“ von Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
//Das Hauptdokument enthält ein Zusammenführungsfeld namens „Document_1“.
// Die entsprechenden Daten für dieses Feld enthalten einen vollständig qualifizierten Pfad zum Dokument.
// Das sollte in dieses Feld eingefügt werden.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Mit diesem Code können Sie beim Seriendruck mit Aspose.Words für .NET ein Dokument in ein anderes Dokument einfügen. Das resultierende Dokument wird unter einem neuen Namen gespeichert



