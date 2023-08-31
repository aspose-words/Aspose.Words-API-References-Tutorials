---
title: Infoga dokument vid ersätt
linktitle: Infoga dokument vid ersätt
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett dokument vid ersättning med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/clone-and-combine-documents/insert-document-at-replace/
---
I den här handledningen går vi igenom hur du infogar ett dokument i ett annat dokument när du ersätter med hjälp av funktionen Infoga dokument vid ersättning i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och utföra dokumentinfogningen.

## Steg 1: Laddar huvuddokumentet

För att komma igång, ange katalogen för dina dokument och ladda huvuddokumentet i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Steg 2: Konfigurera sök- och ersättalternativ

Nu kommer vi att konfigurera sök- och ersätt-alternativen genom att ange sökriktningen och ersätt återuppringning för att infoga ett dokument i ett annat dokument. Här är hur:

```csharp
// Konfigurera sök- och ersättalternativ.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Steg 3: Anropa ersättningsmetoden

Vi kommer nu att anropa ersätt-metoden för att hitta och ersätta den angivna texten med en tom sträng, med hjälp av de konfigurerade alternativen. Här är hur:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Exempel på källkod för Insert Document At Replace med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Infoga dokument när du ersätter Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Ställ in alternativ för sök och ersätt.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Kalla ersättningsmetoden.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Slutsats

I den här handledningen undersökte vi hur man infogar ett dokument i ett annat dokument under ersättning med hjälp av funktionen Infoga dokument vid ersättning i Aspose.Words för .NET. Genom att konfigurera sök- och ersätt-alternativen och tillhandahålla nödvändiga data kan du dynamiskt sammanställa dokument genom att ersätta specifika platshållare med innehållet i andra dokumentmallar eller avsnitt. Aspose.Words för .NET erbjuder ett kraftfullt och flexibelt sätt att hantera komplexa dokumenthanteringsuppgifter, vilket gör det till ett värdefullt verktyg för att automatisera scenarier för att skapa dokument och infoga innehåll.

### FAQ's

#### F: Vad är syftet med att infoga ett dokument i ett annat dokument under ersättning?

S: Genom att infoga ett dokument i ett annat dokument under ersättning kan du dynamiskt ersätta en specifik platshållare med innehållet i ett separat dokument. Den här funktionen är särskilt användbar när du vill sätta ihop ett större dokument genom att kombinera olika fördefinierade dokumentmallar eller avsnitt till specifika platshållare.

#### F: Hur infogar jag ett dokument i ett annat dokument under ersättning med Aspose.Words för .NET?

S: För att infoga ett dokument i ett annat dokument under ersättning med Aspose.Words för .NET, följ dessa steg:
1. Ladda huvuddokumentet som innehåller platshållarna i ett dokumentobjekt.
2. Konfigurera sök- och ersätt-alternativen, inklusive sökriktningen och ersätt återuppringning för att hantera dokumentinfogningen.
3. Anropa ersätt-metoden med lämpligt sökmönster, ersätt platshållarna med en tom sträng med de konfigurerade alternativen.

#### F: Kan jag anpassa insättningsbeteendet under utbyte?

S: Ja, du kan anpassa insättningsbeteendet under ersättning genom att implementera en anpassad ErsättandeCallback. Genom att ärva från IReplacingCallback-gränssnittet kan du styra hur dokumenten infogas och slås samman baserat på dina specifika krav när du byter platshållare.

#### F: Kan jag ersätta flera platshållare med olika dokument?

S: Ja, du kan ersätta flera platshållare med olika dokument genom att ange lämpliga sökmönster för varje platshållare och tillhandahålla motsvarande dokument som ska infogas.