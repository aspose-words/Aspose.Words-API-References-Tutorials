---
title: Feldcode
linktitle: Feldcode
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Erhalten von Feldcode und Feldergebnis in Ihren Word-Dokumenten mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/field-code/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes unten, der die Funktion „Feldcode abrufen“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Dokument einlegen

Der erste Schritt besteht darin, das Dokument hochzuladen, aus dem Sie die Feldcodes erhalten möchten.

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

 Bei jeder Iteration der Schleife erhalten wir den Feldcode mithilfe der`GetFieldCode()` Methode. Wir speichern das Ergebnis des Feldes auch in einer Variablen.

### Quellcodebeispiel für „Get Field Code“ mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Legen Sie das Dokument ein.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Durchlaufen Sie die Dokumentfelder.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Machen Sie etwas mit dem Code und dem Ergebnis des Felds.
}
```

In diesem Beispiel haben wir ein Dokument geladen und dann alle im Dokument vorhandenen Felder durchlaufen. Bei jeder Iteration haben wir den Code und das Ergebnis des Felds erhalten. Sie können Ihre eigene Logik hinzufügen, um den Code und die Ergebnisfelder nach Bedarf zu verarbeiten.

Damit schließen wir unsere Anleitung zur Verwendung der Funktion „Feldcode abrufen“ mit Aspose.Words für .NET ab.

### Häufig gestellte Fragen

#### F: Wie kann ich mit Aspose.Words für .NET ein Feld in ein Word-Dokument einfügen?

 A: Um ein Feld in ein Word-Dokument mit Aspose.Words für .NET einzufügen, können Sie den`DocumentBuilder.InsertField` Methode, die den entsprechenden Feldcode angibt. Sie können beispielsweise`builder.InsertField("MERGEFIELD CustomerName")` , um ein Seriendruckfeld in das Dokument einzufügen.

#### F: Wie kann ich mit Aspose.Words für .NET Felder in einem Dokument aktualisieren?

 A: Um Dokumentfelder mit Aspose.Words für .NET zu aktualisieren, können Sie das`Document.UpdateFields`Methode. Dadurch werden alle im Dokument vorhandenen Felder aktualisiert, z. B. Seriendruckfelder, Datumsfelder usw.

#### F: Wie kann ich den Wert eines bestimmten Felds in Aspose.Words für .NET abrufen?

 A: Um den Wert eines bestimmten Felds in Aspose.Words für .NET abzurufen, können Sie den`Field.GetResult` Methode durch Angabe des Index des Felds in der`Document.Range.Fields` Sammlung. Sie können beispielsweise`string value = document.Range.Fields[0].GetResult()` um den Wert des ersten Felds im Dokument abzurufen.

#### F: Wie kann ich mit Aspose.Words für .NET ein Feld aus einem Dokument entfernen?

 A: Um ein Feld aus einem Dokument mit Aspose.Words für .NET zu entfernen, können Sie den`Field.Remove` Methode zur Angabe der`Field` Objekt, das Sie entfernen möchten. Dadurch wird das Feld aus dem Dokument entfernt.