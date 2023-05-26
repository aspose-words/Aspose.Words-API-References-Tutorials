---
title: Felder löschen
linktitle: Felder löschen
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Löschen von Zusammenführungsfeldern in Ihren Word-Dokumenten mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/delete-fields/
---

Hier erfahren Sie, wie Sie die Funktion „Felder löschen“ in Aspose verwenden. Words für .NET haben wir unten eine Schritt-für-Schritt-Anleitung erstellt. 

Es ist wichtig, jeden Schritt genau zu befolgen, um die gewünschten Ergebnisse zu erzielen. 

## Schritt 1: Erstellen eines neuen Dokuments

In diesem Codeausschnitt erstellen wir zunächst ein neues leeres Dokument mit der folgenden Zeile: 

```csharp
Document doc = new Document();
```

## Schritt 2: Zusammenführungsfelder entfernen

 Um alle im Dokument vorhandenen Zusammenführungsfelder zu entfernen, verwenden wir die`DeleteFields()` Funktion. 

Dies ist besonders nützlich, wenn Sie nur den statischen Inhalt behalten und alle Zusammenführungsinformationen entfernen möchten. 

### Quellcode-Beispiel zum Löschen von Feldern mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vorhandenes Dokument laden.
Document doc = new Document(dataDir + "YourDocument.docx");

// Zusammenführungsfelder entfernen.
doc.MailMerge.DeleteFields();

// Speichern Sie das geänderte Dokument.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 In unserem Beispiel laden wir vor dem Aufruf zunächst ein bestehendes Dokument`DeleteFields()`. Abschließend speichern wir das geänderte Dokument unter einem neuen Dateinamen. 

Um Zusammenführungsfelder mithilfe der Funktion „Felder entfernen“ von Aspose.Words für .NET effektiv aus einem Dokument zu entfernen, können Sie sich an diesem Beispiel orientieren. 

Denken Sie immer daran, „IHR DOKUMENTENVERZEICHNIS“ durch Ihren spezifischen Verzeichnispfad zu ersetzen. 

Unser Leitfaden zur Implementierung der Funktion „Felder löschen“ über Aspose.Words für .NET ist damit abgeschlossen.