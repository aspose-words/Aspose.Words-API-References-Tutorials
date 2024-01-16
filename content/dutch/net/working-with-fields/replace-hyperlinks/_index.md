---
title: Hyperlinks vervangen
linktitle: Hyperlinks vervangen
second_title: Aspose.Words-API voor documentverwerking
description: Vervang hyperlinks in Word-documenten met Aspose.Words voor .NET. Stapsgewijze instructies voor het vervangen van hyperlinks.
type: docs
weight: 10
url: /nl/net/working-with-fields/replace-hyperlinks/
---

Hier is een stapsgewijze handleiding waarin de volgende C#-broncode wordt uitgelegd voor het vervangen van hyperlinks met behulp van Aspose.Words voor .NET-functionaliteit. Zorg ervoor dat u de Aspose.Words-bibliotheek in uw project hebt opgenomen voordat u deze code gebruikt.

## Stap 1: Stel het documentmappad in

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Zorg ervoor dat u het juiste pad opgeeft naar uw documentenmap met de`Hyperlinks.docx` bestand.

## Stap 2: Laad het document met de hyperlinks

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Hier maken we een exemplaar van de`Document` klasse uit het opgegeven bestand.

## Stap 3: Blader door velden om hyperlinks te vinden

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Sommige hyperlinks kunnen lokaal zijn (links naar bladwijzers in het document), we negeren ze.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Deze lus doorloopt alle velden in het document op zoek naar velden van het type`FieldType.FieldHyperlink` . Zodra een veld van dit type is gevonden, controleren we of het een lokale link is door de`SubAddress` eigendom. Als dit niet het geval is, vervangen we het linkadres door`"http://www.aspose.com"` en het resultaat met`"Aspose - The .NET & Java Component Editor"`.

## Stap 4: Sla het gewijzigde document op

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Ten slotte slaan we het gewijzigde document op met de vervangen hyperlinks naar een opgegeven bestand.

### Voorbeeldbroncode om hyperlinks te vervangen door Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Sommige hyperlinks kunnen lokaal zijn (links naar bladwijzers in het document), we negeren ze.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Dit is een voorbeeldbroncode om hyperlinks in een document te vervangen met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe kan ik hyperlinks in een Word-document vervangen met Aspose.Words voor .NET?

 A: Om hyperlinks in een Word-document te vervangen met Aspose.Words voor .NET, kunt u de`Document.Range.Replace`methode die de te zoeken tekst en de vervangende tekst specificeert. Zorg ervoor dat u de juiste opties gebruikt om zoek- en vervangparameters in te stellen.

#### Vraag: Is het mogelijk om alleen bepaalde hyperlinks in een Word-document te vervangen door Aspose.Words voor .NET?

A: Ja, het is mogelijk om alleen bepaalde hyperlinks in een Word-document te vervangen door Aspose.Words voor .NET. U kunt de te vervangen hyperlinks filteren met behulp van specifieke criteria, zoals de link-URL, linktekst of een andere relevante eigenschap. Dan kunt u de vervanging alleen toepassen op de overeenkomende hyperlinks.

#### Vraag: Hoe kan ik hyperlinks in kop-, voetteksten of voetnoten negeren wanneer ik deze vervang door Aspose.Words voor .NET?

A: Als u hyperlinks in kop-, voetteksten of voetnoten wilt negeren bij het vervangen door Aspose.Words voor .NET, kunt u de geavanceerde zoekopties gebruiken en de juiste zoeklimieten opgeven. U kunt de zoekopdracht bijvoorbeeld beperken tot de belangrijkste secties van het document en kop-, voetteksten of voetnoten uitsluiten.

#### Vraag: Is het mogelijk om hyperlinks te vervangen door interne links naar andere delen van het document?

 A: Ja, het is mogelijk om hyperlinks te vervangen door interne links naar andere delen van het document met Aspose.Words voor .NET. U kunt ankers of tekst-ID's gebruiken om interne links te maken en deze vervolgens te vervangen met behulp van de`Document.Range.Replace` methode met de juiste opties.

#### Vraag: Blijven bij het vervangen van hyperlinks door Aspose.Words voor .NET de linkeigenschappen, zoals kleuren of stijlen, behouden?

A: Ja, bij het vervangen van hyperlinks door Aspose.Words voor .NET blijven linkeigenschappen zoals kleuren of stijlen behouden. U kunt dezelfde opmaakeigenschappen in de vervangende tekst opgeven om een consistent resultaat te bereiken.