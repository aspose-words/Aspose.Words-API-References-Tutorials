---
title: Feldcode
linktitle: Feldcode
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Abrufen von Feldcode und Feldergebnis in Ihren Word-Dokumenten mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/field-code/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Get Field Code“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden des Dokuments

Der erste Schritt besteht darin, das Dokument dort hochzuladen, wo Sie die Feldcodes erhalten möchten.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Ersetzen Sie „Hyperlinks.docx“ unbedingt durch den Namen Ihrer eigenen Datei.

## Schritt 3: Dokumentfelder durchsuchen

 Wir benutzen ein`foreach` Schleife, um alle im Dokument vorhandenen Felder zu durchlaufen.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 Bei jeder Iteration der Schleife erhalten wir den Feldcode mithilfe von`GetFieldCode()` Methode. Wir speichern auch das Ergebnis des Feldes in einer Variablen.

### Quellcode-Beispiel für Get Field Code mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Dokumentfelder durchlaufen.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Machen Sie etwas mit dem Code und dem Ergebnis des Feldes.
}
```

In diesem Beispiel haben wir ein Dokument geladen und dann alle im Dokument vorhandenen Felder durchlaufen. Bei jeder Iteration erhielten wir den Code und das Ergebnis des Feldes. Sie können Ihre eigene Logik hinzufügen, um die Code- und Ergebnisfelder nach Bedarf zu verarbeiten.

Damit ist unser Leitfaden zur Verwendung der Funktion „Get Field Code“ mit Aspose.Words für .NET abgeschlossen.

### FAQs

#### F: Wie kann ich mit Aspose.Words für .NET ein Feld in ein Word-Dokument einfügen?

 A: Um mit Aspose.Words für .NET ein Feld in ein Word-Dokument einzufügen, können Sie das verwenden`DocumentBuilder.InsertField` Methode, die den entsprechenden Feldcode angibt. Sie können zum Beispiel verwenden`builder.InsertField("MERGEFIELD CustomerName")` um ein Zusammenführungsfeld in das Dokument einzufügen.

#### F: Wie kann ich Felder in einem Dokument mit Aspose.Words für .NET aktualisieren?

 A: Um Dokumentfelder mit Aspose.Words für .NET zu aktualisieren, können Sie das verwenden`Document.UpdateFields` Methode. Dadurch werden alle im Dokument vorhandenen Felder aktualisiert, z. B. Zusammenführungsfelder, Datumsfelder usw.

#### F: Wie kann ich den Wert eines bestimmten Felds in Aspose.Words für .NET abrufen?

 A: Um den Wert eines bestimmten Felds in Aspose.Words für .NET abzurufen, können Sie Folgendes verwenden`Field.GetResult` Methode durch Angabe des Index des Feldes in der`Document.Range.Fields` Sammlung. Sie können zum Beispiel verwenden`string value = document.Range.Fields[0].GetResult()` um den Wert des ersten Felds im Dokument abzurufen.

#### F: Wie kann ich mit Aspose.Words für .NET ein Feld aus einem Dokument entfernen?

 A: Um ein Feld mit Aspose.Words für .NET aus einem Dokument zu entfernen, können Sie Folgendes verwenden`Field.Remove` Methode, die die angibt`Field` Objekt, das Sie entfernen möchten. Dadurch wird das Feld aus dem Dokument entfernt.