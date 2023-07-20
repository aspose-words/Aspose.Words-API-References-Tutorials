---
title: Infoga dokument vid brevkoppling
linktitle: Infoga dokument vid brevkoppling
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar dokument i ett annat under sammankoppling med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
I den här självstudien kommer vi att gå igenom hur du infogar ett dokument i ett annat dokument under kopplingen med hjälp av funktionen Infoga dokument under koppling av brev i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och utföra dokumentinfogningen.

## Steg 1: Laddar huvuddokumentet

För att komma igång, ange katalogen för dina dokument och ladda huvuddokumentet i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Steg 2: Konfigurera Mail Merge

Låt oss nu konfigurera kopplingen och ange fältet kopplingsanrop för att infoga ett dokument i ett annat dokument. Här är hur:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Steg 3: Kör sammankopplingen av brev

Vi kör kopplingen genom att ange namnen på kopplingsfälten och motsvarande data. Här är hur:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Exempel på källkod för Insert Document At Mail Merge med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Infoga dokument i brevkoppling av Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Huvuddokumentet har ett sammanslagningsfält i sig som heter "Dokument_1".
// Motsvarande data för detta fält innehåller en fullständigt kvalificerad sökväg till dokumentet.
// Det ska infogas i det här fältet.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Med denna kod kommer du att kunna infoga ett dokument i ett annat dokument under sammanslagningen med Aspose.Words för .NET. Det resulterande dokumentet kommer att sparas under ett nytt namn


## Slutsats

den här självstudien undersökte vi hur man infogar ett dokument i ett annat dokument under sammankoppling med hjälp av funktionen Infoga dokument under sammankoppling av Aspose.Words för .NET. Genom att konfigurera kopplingen och tillhandahålla nödvändiga data kan du dynamiskt sammanställa dokument genom att slå samman olika dokumentmallar eller sektioner. Aspose.Words för .NET ger ett flexibelt och kraftfullt sätt att hantera komplexa dokumentgenereringsscenarier, vilket gör det till ett värdefullt verktyg för att automatisera dokumentskapande och manipuleringsuppgifter.

### FAQ's

#### F: Vad är syftet med att infoga ett dokument i ett annat dokument under sammankoppling?

S: Genom att infoga ett dokument i ett annat dokument under sammankopplingen kan du kombinera olika dokumentmallar eller avsnitt dynamiskt baserat på data som tillhandahålls under sammanfogningsprocessen. Den här funktionen är särskilt användbar när du vill sammanställa komplexa dokument genom att slå samman olika fördefinierade mallar eller avsnitt till ett slutligt dokument.

#### F: Hur infogar jag ett dokument i ett annat dokument under sammanslagningen med Aspose.Words för .NET?

S: För att infoga ett dokument i ett annat dokument under sammankoppling med Aspose.Words för .NET, följ dessa steg:
1. Ladda huvuddokumentet som kommer att fungera som bas i ett dokumentobjekt.
2. Konfigurera kopplingen och ange fältet kopplingsanrop för att hantera dokumentinfogning.
3. Kör kopplingen med namnen på kopplingsfälten och motsvarande data (sökväg till dokumentet som ska infogas).

#### F: Hur kan jag anpassa infogningsbeteendet under kopplingen?

S: För att anpassa infogningsbeteendet under sammankoppling av e-post kan du implementera en anpassad FieldMergingCallback genom att ärva från IFieldMergingCallback-gränssnittet. Detta låter dig styra hur dokumenten infogas och slås samman baserat på dina specifika krav.

#### F: Kan jag infoga flera dokument under sammanslagningen?

S: Ja, du kan infoga flera dokument under sammanslagningen genom att tillhandahålla lämplig information för varje sammanfogningsfält. För varje sammanslagningsfält som kräver dokumentinfogning, ange sökvägen till motsvarande dokument som data.


