---
title: Skaffa Paragraph Style Separator
linktitle: Skaffa Paragraph Style Separator
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du får styckestilseparatorn med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/get-paragraph-style-separator/
---

I den här handledningen kommer vi att gå igenom hur du använder funktionen Get Paragraph Style Separator med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa ändringarna.

## Steg 1: Ladda dokumentet

För att komma igång, ange katalogen för dina dokument och ladda dokumentet i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Steg 2: Hitta styckestilseparatorer

Vi kommer nu att gå igenom alla stycken i dokumentet och kontrollera om ett stycke är en stilavgränsare. Här är hur:

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### Exempel på källkod för Get Paragraph Style Separator med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Get Paragraph Style Separator med Aspose.Words för .NET:

```csharp

            Document doc = new Document(MyDir + "Document.docx");

            foreach (Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
            {
                if (paragraph.BreakIsStyleSeparator)
                {
                    Console.WriteLine("Separator Found!");
                }
            }
        
```

Med den här koden kommer du att kunna hitta styckestilseparatorerna i ett dokument med Aspose.Words för .NET.

