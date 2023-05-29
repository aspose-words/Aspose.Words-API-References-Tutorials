---
title: Infoga formulärfält för kombinationsruta
linktitle: Infoga formulärfält för kombinationsruta
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar kombinationsrutaformulär i Word-dokument med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-combo-box-form-field/
---

det här omfattande exemplet kommer du att lära dig hur du infogar ett formulärfält med kombinationsruta i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna lägga till kombinationsrutaformulär med anpassningsbara egenskaper till dina dokument.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Definiera Combo Box-objekt
Definiera sedan en uppsättning objekt för kombinationsrutans formulärfält:

```csharp
string[] items = { "One", "Two", "Three" };
```

## Steg 3: Infoga ett formulärfält för kombinationsruta
Använd metoden InsertComboBox i klassen DocumentBuilder för att infoga ett formulärfält med kombinationsruta. Ange namn, array av objekt och valt index som parametrar:

```csharp
builder.InsertComboBox("DropDown", items, 0);
```

## Steg 4: Spara dokumentet
När du har infogat formulärfältet för kombinationsrutan, spara dokumentet i en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

### Exempel på källkod för Insert Combo Box Form Field med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga ett formulärfält med kombinationsruta med Aspose.Words för .NET:

```csharp
string[] items = { "One", "Two", "Three" };

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertComboBox("DropDown", items, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

Kom ihåg att justera koden efter dina specifika krav och utöka den med ytterligare funktionalitet efter behov.

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du infogar ett formulärfält med kombinationsruta i ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du nu förbättra dina dokument med interaktiva kombinationsrutaformulär.
