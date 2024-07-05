---
title: Liste in jedem Abschnitt neu starten
linktitle: Liste in jedem Abschnitt neu starten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine nummerierte Liste auf jeden Abschnitt in einem Word-Dokument zurücksetzen.
type: docs
weight: 10
url: /de/net/working-with-list/restart-list-at-each-section/
---

In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET eine nummerierte Liste auf jeden Abschnitt in einem Word-Dokument zurücksetzen. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie von[[Originaltext von Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Erstellen des Dokuments und der Liste

Erstellen Sie zunächst ein neues Dokument und fügen Sie eine standardmäßige nummerierte Liste hinzu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Schritt 2: Elemente zur Liste hinzufügen

 Verwenden Sie dann ein`DocumentBuilder` um Elemente zur Liste hinzuzufügen. Sie können eine Schleife verwenden, um mehrere Elemente zur Liste hinzuzufügen:

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

So! Sie haben mit Aspose.Words für .NET erfolgreich eine nummerierte Liste auf jeden Abschnitt in einem Word-Dokument zurückgesetzt.

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

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und ihn Ihren spezifischen Anforderungen entsprechend ändern.

### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words in jedem Abschnitt eine Liste neu starten?

 A: Um eine Liste in jedem Abschnitt in Aspose.Words neu zu starten, müssen Sie eine Instanz des`List`Klasse und weisen Sie ihr eine nummerierte Liste zu. Anschließend können Sie mit dem`List.IsRestartAtEachSection` -Eigenschaft, um anzugeben, dass die Nummerierung in jedem Abschnitt neu gestartet werden soll. Sie können diese Liste mit einem oder mehreren Abschnitten Ihres Dokuments verknüpfen, sodass die Nummerierung in jedem Abschnitt korrekt neu gestartet wird.

#### F: Kann ich das Nummerierungsformat von Listen in Aspose.Words anpassen?

 A: Ja, Sie können das Nummerierungsformat von Listen in Aspose.Words anpassen. Die`List` bietet hierfür mehrere Eigenschaften an, wie zum Beispiel`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`usw. Mit diesen Eigenschaften können Sie den Listentyp (nummeriert, mit Aufzählungszeichen usw.), das Nummerierungsformat (arabische Ziffern, römische Ziffern, Buchstaben usw.) und andere Formatierungsoptionen für die Nummerierung festlegen.

#### F: Ist es möglich, einer nummerierten Liste in Aspose.Words zusätzliche Ebenen hinzuzufügen?

 A: Ja, es ist möglich, einer nummerierten Liste in Aspose.Words zusätzliche Ebenen hinzuzufügen.`ListLevel`Mit der Klasse können Sie Formatierungseigenschaften für jede Ebene der Liste festlegen. Sie können Optionen wie Präfix, Suffix, Ausrichtung, Einzug usw. festlegen. Auf diese Weise können Sie Listen mit mehreren Hierarchieebenen erstellen.