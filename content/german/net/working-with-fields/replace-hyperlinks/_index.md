---
title: Ersetzen Sie Hyperlinks
linktitle: Ersetzen Sie Hyperlinks
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Ersetzen Sie Hyperlinks in Word-Dokumenten mit Aspose.Words für .NET. Schritt-für-Schritt-Anleitung zum Ersetzen von Hyperlinks.
type: docs
weight: 10
url: /de/net/working-with-fields/replace-hyperlinks/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes zum Ersetzen von Hyperlinks mithilfe der Funktionalität von Aspose.Words für .NET. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek in Ihr Projekt eingebunden haben, bevor Sie diesen Code verwenden.

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Dokumentenverzeichnis angeben, das die enthält`Hyperlinks.docx` Datei.

## Schritt 2: Laden Sie das Dokument mit den Hyperlinks

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Hier erstellen wir eine Instanz von`Document` Klasse aus der angegebenen Datei.

## Schritt 3: Durchsuchen Sie die Felder, um Hyperlinks zu finden

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Einige Hyperlinks können lokal sein (Links zu Lesezeichen innerhalb des Dokuments), wir ignorieren sie.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Diese Schleife durchläuft alle Felder im Dokument und sucht nach Feldern dieses Typs`FieldType.FieldHyperlink` . Sobald ein Feld dieses Typs gefunden wird, prüfen wir, ob es sich um einen lokalen Link handelt, indem wir das überprüfen`SubAddress` Eigentum. Wenn nicht, ersetzen wir die Linkadresse durch`"http://www.aspose.com"` und das Ergebnis mit`"Aspose - The .NET & Java Component Editor"`.

## Schritt 4: Speichern Sie das geänderte Dokument

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Abschließend speichern wir das geänderte Dokument mit den ersetzten Hyperlinks in einer angegebenen Datei.

### Beispielquellcode zum Ersetzen von Hyperlinks durch Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Einige Hyperlinks können lokal sein (Links zu Lesezeichen innerhalb des Dokuments), wir ignorieren sie.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Dies ist ein Beispielquellcode zum Ersetzen von Hyperlinks in einem Dokument mithilfe von Aspose.Words für .NET.

### FAQs

#### F: Wie kann ich Hyperlinks in einem Word-Dokument mit Aspose.Words für .NET ersetzen?

 A: Um Hyperlinks in einem Word-Dokument mit Aspose.Words für .NET zu ersetzen, können Sie das verwenden`Document.Range.Replace`Methode, die den zu suchenden Text und den Ersatztext angibt. Stellen Sie sicher, dass Sie die entsprechenden Optionen zum Festlegen der Such- und Ersetzungsparameter verwenden.

#### F: Ist es möglich, nur bestimmte Hyperlinks in einem Word-Dokument durch Aspose.Words für .NET zu ersetzen?

A: Ja, es ist möglich, nur bestimmte Hyperlinks in einem Word-Dokument durch Aspose.Words für .NET zu ersetzen. Sie können die zu ersetzenden Hyperlinks nach bestimmten Kriterien filtern, z. B. nach Link-URL, Linktext oder anderen relevanten Eigenschaften. Dann können Sie die Ersetzung nur auf die passenden Hyperlinks anwenden.

#### F: Wie kann ich Hyperlinks in Kopf-, Fuß- oder Fußnoten ignorieren, wenn ich sie durch Aspose.Words für .NET ersetze?

A: Um Hyperlinks in Kopf-, Fuß- oder Fußnoten beim Ersetzen durch Aspose.Words für .NET zu ignorieren, können Sie die erweiterten Suchoptionen verwenden und entsprechende Suchgrenzen festlegen. Beispielsweise können Sie die Suche auf größere Abschnitte des Dokuments beschränken und Kopf- und Fußzeilen sowie Fußnoten ausschließen.

#### F: Ist es möglich, Hyperlinks durch interne Links zu anderen Teilen des Dokuments zu ersetzen?

 A: Ja, es ist möglich, mit Aspose.Words für .NET Hyperlinks durch interne Links zu anderen Teilen des Dokuments zu ersetzen. Sie können Anker oder Text-IDs verwenden, um interne Links zu erstellen und diese dann durch die zu ersetzen`Document.Range.Replace` Methode mit den entsprechenden Optionen.

#### F: Behält das Ersetzen von Hyperlinks durch Aspose.Words für .NET Linkeigenschaften wie Farben oder Stile bei?

A: Ja, beim Ersetzen von Hyperlinks durch Aspose.Words für .NET bleiben Linkeigenschaften wie Farben oder Stile erhalten. Sie können im Ersetzungstext dieselben Formatierungseigenschaften angeben, um ein konsistentes Ergebnis zu erzielen.