---
title: Autolänk
linktitle: Autolänk
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar autolänk med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/autolink/
---

I det här exemplet kommer vi att förklara hur man använder funktionen "Autolink" med Aspose.Words för .NET. Den här funktionen låter dig infoga hyperlänkar i ditt dokument automatiskt.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Infoga en hyperlänk

 Vi kan infoga en hyperlänk med hjälp av`InsertHyperlink` dokumentgeneratorns metod. Vi anger webbadressen och texten som ska visas för länken.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## Steg 3: Infoga en e-postadress som en länk

Vi kan också infoga en e-postadress som en länk med prefixet "mailto:". Detta gör att användare kan klicka på länken för att öppna sin standard e-postklient.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Steg 4: Spara dokumentet

Slutligen kan vi spara dokumentet i önskat format.

### Exempel på källkod för autolänk med Aspose.Words för .NET


```csharp
// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder();

// Infoga hyperlänk.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Grattis! Du har nu lärt dig hur du använder "Autolink"-funktionen med Aspose.Words för .NET.


### FAQ's

#### F: Hur skapar jag en automatisk länk till en URL-adress i Aspose.Words?

 S: För att skapa en automatisk länk till en URL-adress i Aspose.Words kan du använda`<a>` tagga med`href` attribut som innehåller URL-adressen. Du kan till exempel använda`<a href="https://www.aspose.com">https://www.aspose.com</a>` för att automatiskt länka till "https: //www.aspose.com".

#### F: Är det möjligt att anpassa visningstexten för en automatisk länk i Aspose.Words?

 S: Ja, du kan anpassa visningstexten för en automatisk länk i Aspose.Words. Istället för att använda URL-adressen som visningstext kan du använda vilken annan text som helst genom att ersätta innehållet mellan`<a>` taggar. Du kan till exempel använda`<a href="https://www.aspose.com">Click here</a>` för att visa texten "Klicka här" som en automatisk länk.

#### F: Hur kan jag lägga till ytterligare attribut till en autolänk i Aspose.Words?

S: För att lägga till ytterligare attribut till en automatisk länk i Aspose.Words kan du använda ytterligare HTML-attribut i`<a>` märka. Du kan till exempel använda`<a href="https://www.aspose.com" target="_blank">Link</a>` för att öppna länken i ett nytt fönster eller flik med hjälp av` attribute target="_blank"`.