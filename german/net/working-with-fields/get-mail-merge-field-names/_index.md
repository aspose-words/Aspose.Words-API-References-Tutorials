---
title: Rufen Sie die Namen der Serienbrieffelder ab
linktitle: Rufen Sie die Namen der Serienbrieffelder ab
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Serienbrieffeldnamen in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/get-mail-merge-field-names/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Get Merge Field Names“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden des Dokuments

Der erste Schritt besteht darin, das Dokument zu laden, in dem Sie die Zusammenführungsfeldnamen erhalten möchten.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Ersetzen Sie „IHRE DOKUMENTENDATEI“ unbedingt durch den Namen Ihrer eigenen Datei.

## Schritt 3: Rufen Sie die Namen der Zusammenführungsfelder ab

 Wir benutzen das`GetFieldNames()` -Methode, um ein Array mit den Namen der im Dokument vorhandenen Zusammenführungsfelder abzurufen.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 Der`fieldNames` Die Variable enthält jetzt die Namen der Zusammenführungsfelder.

### Quellcodebeispiel für „Get Merge Field Names“ mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Rufen Sie die Namen der Zusammenführungsfelder ab.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Zeigt die Anzahl der Zusammenführungsfelder an.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 In diesem Beispiel haben wir ein Dokument geladen und die Namen der Zusammenführungsfelder mithilfe von abgerufen`GetFieldNames()` Methode und zeigte die Anzahl der im Dokument vorhandenen Zusammenführungsfelder an.

Damit ist unser Leitfaden zur Verwendung der Funktion „Get Merge Field Names“ mit Aspose.Words für .NET abgeschlossen.