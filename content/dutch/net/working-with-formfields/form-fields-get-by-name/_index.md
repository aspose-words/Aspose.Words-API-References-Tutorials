---
title: Formuliervelden krijgen op naam
linktitle: Formuliervelden krijgen op naam
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u formuliervelden op naam kunt ophalen en wijzigen in Word-documenten met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-formfields/form-fields-get-by-name/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u Aspose.Words voor .NET kunt gebruiken om formuliervelden op naam op te halen uit een Word-document. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Om aan de slag te gaan, moet u ervoor zorgen dat Aspose.Words voor .NET is geïnstalleerd en ingesteld in uw ontwikkelomgeving. Als u dit nog niet hebt gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Het documentobject initialiseren

 Initialiseer eerst de`Document` object door het pad op te geven naar uw brondocument met formuliervelden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Stap 2: Formuliervelden ophalen

 Ga vervolgens naar de`FormFields` eigendom van de`Range` object in het document om alle formuliervelden op te halen:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

U kunt formuliervelden ophalen op index of op naam. In dit voorbeeld halen we een formulierveld op met behulp van beide methoden:

```csharp
FormField formField1 = documentFormFields[3]; // Ophalen via index
FormField formField2 = documentFormFields["Text2"]; // Ophalen op naam
```

## Stap 3: Formulierveldeigenschappen wijzigen

Nadat u de formuliervelden heeft opgehaald, kunt u de eigenschappen ervan indien nodig wijzigen. In dit voorbeeld wijzigen we de lettergrootte van`formField1` tot 20 en de letterkleur van`formField2` naar rood:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Stap 4: Het document opslaan

Sla ten slotte het gewijzigde document op:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Dat is het! U hebt met succes formuliervelden op naam opgehaald en hun eigenschappen in een Word-document gewijzigd met Aspose.Words voor .NET.

### Voorbeeldbroncode voor formuliervelden Get By Name met Aspose.Words voor .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke vereisten.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een formulierveld op naam krijgen in Aspose.Words?

 A: Om een formulierveld op naam te krijgen in Aspose.Words, kunt u de`Document.Range.FormFields[name]` methode. Deze methode retourneert het formulierveld dat overeenkomt met de opgegeven naam.

#### Vraag: Wat moet ik doen als het formulierveld met de opgegeven naam niet in het document voorkomt?

 A: Als het formulierveld met de opgegeven naam niet in het document voorkomt, wordt het`Document.Range.FormFields[name]` methode zal terugkeren`null`. U kunt dit resultaat controleren om gevallen af te handelen waarin het formulierveld niet wordt gevonden.

#### Vraag: Hoe kan ik de eigenschappen van een gevonden formulierveld wijzigen?

A: Zodra u een formulierveld op naam krijgt, kunt u de afzonderlijke eigenschappen ervan openen om deze te bewerken. U kunt bijvoorbeeld de waarde van het veld wijzigen, de zichtbaarheid ervan in- of uitschakelen, of indien nodig andere eigenschappen wijzigen.

#### Vraag: Kan ik meerdere formuliervelden met dezelfde naam in een document krijgen?

 A: Ja, het is mogelijk om meerdere formuliervelden met dezelfde naam in een document te hebben. In dit geval is de`Document.Range.FormFields[name]` methode retourneert het eerste gevonden formulierveld met de opgegeven naam. Als u meerdere formuliervelden met dezelfde naam heeft, moet u hiermee rekening houden bij het manipuleren van de velden.

#### Vraag: Hoe kan ik alle formuliervelden in een document doorlopen?

 A: Om alle formuliervelden in een document te herhalen, kunt u een`foreach` lus op de`Document.Range.FormFields` verzameling. Hierdoor kunt u elk formulierveld afzonderlijk openen en op elk veld bewerkingen uitvoeren.