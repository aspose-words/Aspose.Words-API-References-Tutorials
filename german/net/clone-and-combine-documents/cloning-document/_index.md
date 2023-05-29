---
title: Dokument klonen
linktitle: Dokument klonen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie ein Word-Dokument mit Aspose.Words für .NET klonen.
type: docs
weight: 10
url: /de/net/clone-and-combine-documents/cloning-document/
---

In diesem Tutorial erklären wir Ihnen, wie Sie ein Word-Dokument mithilfe der Klonfunktion von Aspose.Words für .NET klonen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und eine exakte Kopie eines vorhandenen Dokuments zu erstellen.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst Ihr Dokumentverzeichnis an und laden Sie das vorhandene Dokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Schritt 2: Klonen Sie das Dokument

Jetzt klonen wir das Dokument und erstellen eine exakte Kopie davon. Hier ist wie:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### Beispielquellcode zum Klonen von Dokumenten mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion zum Klonen von Aspose.Words-Dokumenten für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

Mit diesem Code können Sie Word-Dokumente mit Aspose.Words für .NET klonen. Die exakte Kopie des Dokuments wird unter einem neuen Dateinamen gespeichert.

