---
title: Skapa Vba-projekt
linktitle: Skapa Vba-projekt
second_title: Aspose.Words för .NET API Referens
description: I den här handledningen lär du dig hur du skapar ett VBA-projekt i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-vba-macros/create-vba-project/
---

den här handledningen kommer vi att berätta för dig hur du skapar ett VBA-projekt i ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Genom att skapa ett VBA-projekt kan du lägga till anpassad VBA-kod till ditt Word-dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa ett nytt VBA-dokument och projekt
 Därefter kommer vi att skapa ett nytt dokument genom att instansiera`Document` klass och ett tomt VBA-projekt genom att instansiera`VbaProject` klass.

```csharp
// Skapa ett nytt dokument
Document doc = new Document();

// Skapa ett nytt VBA-projekt
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## Steg 3: Skapa en ny modul och ange makrokällkod
 Vi kommer att skapa en ny modul genom att instansiera`VbaModule` klass och anger makronamn, typ (procedurmodul) och källkod.

```csharp
// Skapa en ny modul
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// Lägg till modulen i VBA-projektet
doc.VbaProject.Modules.Add(module);
```

## Steg 4: Spara dokumentet
Slutligen kommer vi att spara dokumentet med VBA-projektet skapat i en fil.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### Exempel på källkod för Skapa Vba-projekt med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// Skapa en ny modul och ange en makrokällkod.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// Lägg till modul till VBA-projektet.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## Slutsats
den här handledningen såg vi hur man skapar ett VBA-projekt i ett Word-dokument med Aspose.Words för .NET. Genom att skapa ett VBA-projekt kan du lägga till och anpassa VBA-kod i ditt Word-dokument. Använd gärna den här funktionen för att automatisera uppgifter eller lägga till anpassade funktioner i dina Word-dokument.
