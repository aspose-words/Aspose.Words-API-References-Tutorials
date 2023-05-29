---
title: Ersetzen Sie Hyperlinks
linktitle: Ersetzen Sie Hyperlinks
second_title: Aspose.Words für .NET API-Referenz
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

 Diese Schleife durchläuft alle Felder im Dokument und sucht nach Feldern dieses Typs`FieldType.FieldHyperlink` . Sobald ein Feld dieses Typs gefunden wird, prüfen wir, ob es sich um einen lokalen Link handelt, indem wir das überprüfen`SubAddress` Eigentum. Wenn nicht, ersetzen wir die Linkadresse durch`"http://www.aspose.com"`und das Ergebnis mit`"Aspose - The .NET & Java Component Editor"`.

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