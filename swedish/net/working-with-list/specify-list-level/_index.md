---
title: Ange listnivå
linktitle: Ange listnivå
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du anger listnivån i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-list/specify-list-level/
---

I denna steg-för-steg handledning kommer vi att visa dig hur du anger listnivån i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte redan har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Skapa dokument- och dokumentgeneratorn

Skapa först ett nytt dokument och en tillhörande dokumentgenerator:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Skapa och tillämpa en numrerad lista

Skapa sedan en numrerad lista baserad på en av Microsoft Words listmallar och tillämpa den på det aktuella stycket i dokumentbyggaren:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Steg 3: Listnivåspecifikation

 Använd dokumentbyggarens`ListLevelNumber` egenskap för att ange listnivån och lägga till text till stycket:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Upprepa dessa steg för att ange listnivåer och lägga till text på varje nivå.

## Steg 4: Skapa och tillämpa en punktlista

Du kan också skapa och använda en punktlista med hjälp av en av Microsoft Words listmallar:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Steg 5: Lägga till text till nivåer med punktlista

 Använd`ListLevelNumber` egenskapen igen för att ange nivån på punktlistan och lägga till text:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Steg 6: Sluta formatera listan

 För att stoppa listformateringen, ställ in`null` till`List` egenskapen för dokumentgeneratorn:

```csharp
builder. ListFormat. List = null;
```

## Steg 7: Spara det ändrade dokumentet

Spara det ändrade dokumentet:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Så ! Du har angett listnivån i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för att ange listnivå

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//Skapa en numrerad lista baserad på en av Microsoft Word-listmallarna
// och tillämpa den på dokumentbyggarens nuvarande stycke.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Det finns nio nivåer i den här listan, låt oss prova dem alla.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Skapa en punktlista baserad på en av Microsoft Word-listmallarna
// och tillämpa den på dokumentbyggarens nuvarande stycke.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Detta är ett sätt att stoppa listformatering.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### FAQ's

#### F: Hur kan jag ange listnivå i Aspose.Words?

 S: För att ange listnivån i Aspose.Words måste du skapa en instans av`List` klass och ge den en numrerad lista. Då kan du använda`Paragraph.ListFormat.ListLevelNumber` egenskap för att ange nivån för varje listobjekt. Du kan associera denna lista med en del av ditt dokument så att listobjekten har önskad nivå.

#### F: Är det möjligt att ändra numreringsformatet för listobjekt i Aspose.Words?

 S: Ja, du kan ändra numreringsformatet för listobjekt i Aspose.Words. De`ListLevel` klass erbjuder flera fastigheter för detta, som t.ex`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, etc. Du kan använda dessa egenskaper för att ställa in numreringsformatet för listobjekt, som arabiska siffror, romerska siffror, bokstäver osv.

#### F: Kan jag lägga till ytterligare nivåer till en numrerad lista i Aspose.Words?

 S: Ja, det är möjligt att lägga till ytterligare nivåer till en numrerad lista i Aspose.Words. De`ListLevel` class låter dig ställa in formateringsegenskaper för varje nivå i listan. Du kan ställa in alternativ som prefix, suffix, justering, indrag, etc. Detta låter dig skapa listor med flera nivåer av hierarki.


