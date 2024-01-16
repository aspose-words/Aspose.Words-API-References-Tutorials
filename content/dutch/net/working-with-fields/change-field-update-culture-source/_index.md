---
title: Wijzig veldupdatecultuurbron
linktitle: Wijzig veldupdatecultuurbron
second_title: Aspose.Words-API voor documentverwerking
description: Wijzig veldupdate Cultuurbron, stapsgewijze handleiding voor het wijzigen van de cultuurbron in Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/change-field-update-culture-source/
---

In deze zelfstudie begeleiden we u bij het wijzigen van de veldupdatecultuurbron in Word-documenten met behulp van Aspose.Words voor .NET. Door de cultuurbron te wijzigen, kunt u de datumopmaak bepalen tijdens veldupdates en samenvoegbewerkingen. Wij voorzien u van de benodigde C#-broncode en stap-voor-stap instructies om dit te realiseren.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een document en DocumentBuilder
Maak om te beginnen een exemplaar van de klasse Document en een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg inhoud in met een specifieke landinstelling
Stel vervolgens de landinstelling in op Duits en voeg velden met datumnotatie in:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

In de bovenstaande code stellen we de landinstelling van het lettertype in op Duits (landinstelling-ID 1031) en voegen we twee velden in met specifieke datumnotatie.

## Stap 3: Wijzig de cultuurbron van de veldupdate
Om de bron van de veldupdatecultuur te wijzigen, gebruikt u de klasse FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

In dit voorbeeld stellen we in dat de cultuur die tijdens de veldupdate wordt gebruikt, wordt gekozen uit de cultuur die door het veld wordt gebruikt.

## Stap 4: Voer Afdruk samenvoegen uit
Voer een samenvoegbewerking uit en geef de datumwaarde op voor het veld 'Datum2':

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

In dit codefragment voeren we de samenvoegbewerking uit en geven we een DateTime-waarde op voor het veld 'Datum2'.

## Stap 5: Sla het document op
Sla het gewijzigde document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Voorbeeldbroncode voor het wijzigen van de cultuurbron voor veldupdates met Aspose.Words voor .NET
Hier is de volledige broncode voor het wijzigen van de veldupdatecultuurbron in Word-documenten met Aspose.Words voor .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u de veldupdatecultuurbron in Word-documenten kunt wijzigen met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu de cultuur beheren die wordt gebruikt voor datumopmaak tijdens veldupdates en samenvoegbewerkingen. Pas de cultuurbron aan uw vereisten aan om nauwkeurige en consistente gegevens te garanderen.

### Veelgestelde vragen

#### Vraag: Hoe kan ik de veldupdatecultuurbron in Aspose.Words voor .NET wijzigen?

 A: Om de cultuurbron voor veldupdates in Aspose.Words voor .NET te wijzigen, kunt u de`Document.FieldOptions.CultureSource` eigendom en stel de waarde ervan in`FieldCultureSource.FieldCode` of`FieldCultureSource.CurrentThread` . U kunt bijvoorbeeld gebruiken`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` om de cultuur te gebruiken die is gedefinieerd in de veldcode.

#### Vraag: Hoe kan ik een specifieke cultuur opgeven voor het bijwerken van velden in Aspose.Words voor .NET?

A: Om een specifieke cultuur te specificeren voor het bijwerken van velden in Aspose.Words voor .NET, kunt u de`Document.FieldOptions.FieldUpdateCultureInfo` eigendom en stel de`CultureInfo` object dat overeenkomt met de gewenste cultuur. U kunt bijvoorbeeld gebruiken`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` om de Franse (Frankrijk) cultuur te specificeren.

#### Vraag: Is het mogelijk om het automatisch bijwerken van velden in Aspose.Words voor .NET uit te schakelen?

 A: Ja, het is mogelijk om het automatisch bijwerken van velden in Aspose.Words voor .NET uit te schakelen. U kunt gebruik maken van de`Document.FieldOptions.UpdateFields` eigenschap en stel deze in`false` om te voorkomen dat velden automatisch worden bijgewerkt. Hierdoor kunt u het bijwerken van velden indien nodig handmatig regelen.

#### Vraag: Hoe kan ik documentvelden in Aspose.Words voor .NET handmatig bijwerken?

 A: Om velden in een document in Aspose.Words voor .NET handmatig bij te werken, kunt u de`Field.Update` methode voor elk veld afzonderlijk. U kunt bijvoorbeeld gebruiken`field.Update()` om het specifieke veld bij te werken.