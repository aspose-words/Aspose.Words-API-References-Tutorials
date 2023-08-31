---
title: Infoga kryssruta formulärfält i Word-dokument
linktitle: Infoga kryssruta formulärfält i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar kryssrutaformulär i Word-dokument med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-check-box-form-field/
---
I den här omfattande självstudien kommer du att lära dig hur du infogar ett formulärfält i en kryssruta i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna lägga till kryssrutaformulär med anpassningsbara egenskaper till dina dokument.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga ett kryssrutaformulärfält
Använd sedan metoden InsertCheckBox för klassen DocumentBuilder för att infoga ett formulärfält för kryssruta. Ange namn, markerat tillstånd, standardtillstånd och storleksparametrar som argument:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## Steg 3: Spara dokumentet
När du har infogat kryssrutans formulärfält, spara dokumentet i en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Exempel på källkod för Infoga kryssrutaformulärfält med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga ett kryssrutaformulär med Aspose.Words för .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", true, true, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

Kom ihåg att justera koden efter dina specifika krav och utöka den med ytterligare funktionalitet efter behov.

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du infogar ett kryssrutaformulär i ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du nu förbättra dina dokument med interaktiva kryssrutaformulär.

### FAQ's

#### F: Kan jag infoga flera kryssrutaformulär i ett enda dokument?

A: Absolut! Du kan infoga så många kryssrutaformulär som behövs i ett Word-dokument med Aspose.Words för .NET. Upprepa helt enkelt infogningsprocessen för att lägga till flera interaktiva kryssrutor.

#### F: Kan jag ställa in initialtillståndet (markerat eller avmarkerat) för kryssrutans formulärfält?

S: Ja, du har full kontroll över det ursprungliga tillståndet för kryssrutans formulärfält. Genom att ställa in den kontrollerade tillståndsparametern till sant eller falskt kan du definiera om kryssrutan initialt är markerad eller avmarkerad.

#### F: Är formulärfält i kryssrutorna kompatibla med andra filformat, som PDF?

S: Ja, kryssrutaformulär som infogats med Aspose.Words för .NET är kompatibla med olika filformat, inklusive DOCX och PDF. Detta gör att du kan exportera dina dokument i olika format samtidigt som du behåller de interaktiva kryssrutorna.

#### F: Kan jag justera storleken på kryssrutans formulärfält?

A: Visst! Du kan ange storleken på kryssrutans formulärfält med hjälp av storleksparametern i metoden InsertCheckBox. Detta gör att du kan styra måtten på kryssrutan enligt dina designpreferenser.

#### F: Är Aspose.Words för .NET lämpligt för både skrivbords- och webbapplikationer?

S: Ja, Aspose.Words för .NET är ett mångsidigt bibliotek som lämpar sig för både skrivbords- och webbapplikationer. Oavsett om du bygger en Windows-applikation eller ett webbaserat system, kan du integrera biblioteket utan ansträngning.