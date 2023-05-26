---
title: Starten Sie die Liste in jedem Abschnitt neu
linktitle: Starten Sie die Liste in jedem Abschnitt neu
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine nummerierte Liste für jeden Abschnitt in einem Word-Dokument zurücksetzen.
type: docs
weight: 10
url: /de/net/working-with-list/restart-list-at-each-section/
---

In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET eine nummerierte Liste für jeden Abschnitt in einem Word-Dokument zurücksetzen. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie es noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Dokument und Liste erstellen

Erstellen Sie zunächst ein neues Dokument und fügen Sie eine standardmäßig nummerierte Liste hinzu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Schritt 2: Elemente zur Liste hinzufügen

 Dann verwenden Sie a`DocumentBuilder` um Elemente zur Liste hinzuzufügen. Sie können eine Schleife verwenden, um mehrere Elemente zur Liste hinzuzufügen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

In diesem Beispiel fügen wir nach dem 15. Listenelement einen Abschnittsumbruch ein, um die Neunummerierung zu veranschaulichen.

## Schritt 3: Speichern Sie das geänderte Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

So ! Sie haben mit Aspose.Words für .NET erfolgreich eine nummerierte Liste für jeden Abschnitt in einem Word-Dokument zurückgesetzt.

### Beispielquellcode zum Zurücksetzen der Liste in jedem Abschnitt

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und an Ihre spezifischen Bedürfnisse anpassen.
