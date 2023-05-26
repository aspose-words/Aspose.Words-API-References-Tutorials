---
title: Använd nodtyp
linktitle: Använd nodtyp
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder nodtyp för att komma åt dokumentspecifik information med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-node/use-node-type/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur du använder nodtypens funktionalitet med Aspose.Words för .NET.

## Steg 1: Importera nödvändiga referenser
Innan du börjar, se till att du har importerat de nödvändiga referenserna för att använda Aspose.Words för .NET i ditt projekt. Detta inkluderar att importera Aspose.Words-biblioteket och lägga till de nödvändiga namnområdena till din källfil.

```csharp
using Aspose.Words;
```

## Steg 2: Skapa ett nytt dokument
 I det här steget kommer vi att skapa ett nytt dokument med hjälp av`Document` klass.

```csharp
Document doc = new Document();
```

## Steg 3: Hämta Document Node Type
 För att få nodtypen för ett dokument använder vi`NodeType` fast egendom.

```csharp
NodeType type = doc.NodeType;
```

### Exempel på källkod för att använda nodtyp med Aspose.Words för .NET

```csharp
Document doc = new Document();

NodeType type = doc.NodeType;
```

Detta är ett komplett kodexempel för att använda nodtyp med Aspose.Words för .NET. Var noga med att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera denna kod i ditt projekt.

