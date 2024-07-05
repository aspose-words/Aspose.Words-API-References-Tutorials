---
title: Seriendruckfelder umbenennen
linktitle: Seriendruckfelder umbenennen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Seriendruckfelder in einem Dokument umbenennen.
type: docs
weight: 10
url: /de/net/working-with-fields/rename-merge-fields/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erklärung des C#-Quellcodes unten, der die Funktion zum Umbenennen von Seriendruckfeldern von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und Einfügen der Seriendruckfelder

Wir beginnen mit der Erstellung eines neuen Dokuments und verwenden ein`DocumentBuilder` , um die Seriendruckfelder einzufügen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Schritt 3: Seriendruckfelder umbenennen

Wir durchlaufen jedes Feld im Dokumentbereich und wenn es sich um ein Seriendruckfeld handelt, benennen wir das Feld um, indem wir den "_Suffix „Umbenannt“.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Schritt 4: Speichern des Dokuments

 Schließlich nennen wir die`Save()` Methode zum Speichern des geänderten Dokuments.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Quellcodebeispiel zum Umbenennen von Seriendruckfeldern mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und fügen Sie die Seriendruckfelder ein.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Seriendruckfelder umbenennen.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Speichern Sie das Dokument.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Befolgen Sie diese Schritte, um Seriendruckfelder in Ihrem Dokument mit Aspose.Words für .NET umzubenennen.

### Häufig gestellte Fragen

#### F: Wie kann ich mit Aspose.Words für .NET zusammengeführte Felder in einem Word-Dokument umbenennen?

 A: Um zusammengeführte Felder in einem Word-Dokument mit Aspose.Words für .NET umzubenennen, können Sie die Felder im Dokument mit dem`FieldMergingArgs` Klasse und verwenden Sie die`FieldMergingArgs.FieldName` Methode zum Umbenennen des Felds.

#### F: Ist es mit Aspose.Words für .NET möglich, nur bestimmte zusammengeführte Felder in einem Word-Dokument umzubenennen?

A: Ja, es ist möglich, nur bestimmte zusammengeführte Felder in einem Word-Dokument mit Aspose.Words für .NET umzubenennen. Sie können filtern, welche Felder umbenannt werden sollen, indem Sie bestimmte Kriterien verwenden, wie z. B. Feldname oder andere relevante Eigenschaften. Anschließend können Sie die entsprechenden Felder mit dem`FieldMergingArgs.FieldName` Methode.

#### F: Wie kann ich überprüfen, ob ein Seriendruckfeld in einem Word-Dokument mit Aspose.Words für .NET erfolgreich umbenannt wurde?

 A: Um zu überprüfen, ob ein Seriendruckfeld in einem Word-Dokument mit Aspose.Words für .NET erfolgreich umbenannt wurde, können Sie den`FieldMergedArgs` Klasse und Zugriff auf die`FieldMergedArgs.IsMerged` -Eigenschaft, um zu bestimmen, ob das Feld mit Treffer umbenannt wurde.

#### F: Welche Konsequenzen hat die Umbenennung eines Seriendruckfelds in einem Word-Dokument mit Aspose.Words für .NET?

A: Wenn Sie ein Seriendruckfeld in einem Word-Dokument mit Aspose.Words für .NET umbenennen, ändert sich der Name des Felds im Dokument, was sich auf andere Funktionen oder Prozesse auswirken kann, die vom Feldnamen abhängen. Denken Sie unbedingt an diese möglichen Konsequenzen, bevor Sie Seriendruckfelder umbenennen.

#### F: Ist es möglich, den ursprünglichen Namen eines zusammengeführten Felds wiederherzustellen, nachdem es mit Aspose.Words für .NET umbenannt wurde?

A: Ja, es ist möglich, den ursprünglichen Namen eines zusammengeführten Felds wiederherzustellen, nachdem es mit Aspose.Words für .NET umbenannt wurde. Sie können den ursprünglichen Namen des Felds in einer Variablen oder Liste speichern und diese Informationen dann verwenden, um den ursprünglichen Namen bei Bedarf wiederherzustellen.