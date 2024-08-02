---
title: benadrukt
linktitle: benadrukt
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u accenten (vet en cursief) gebruikt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/emphases/
---

In dit voorbeeld leggen we uit hoe u accenten kunt gebruiken met Aspose.Words voor .NET. nadruk wordt gebruikt om bepaalde delen van de tekst te benadrukken, zoals vet en cursief.

## Stap 1: Documentinitialisatie

 Eerst initialiseren we het document door een exemplaar van de`Document` klas.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Stap 2: Een documentgenerator gebruiken

Vervolgens gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg tekst toe met accenten

We kunnen nadruktekst toevoegen door de lettertype-eigenschappen van de documentgenerator te wijzigen. In dit voorbeeld gebruiken we vet en cursief om verschillende delen van de tekst te benadrukken.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Stap 4: Het document opslaan

 Ten slotte kunnen we het document in het gewenste formaat opslaan. In dit voorbeeld gebruiken we de`.md` extensie voor een Markdown-formaat.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Gefeliciteerd! Je hebt nu geleerd hoe je accenten kunt gebruiken met Aspose.Words voor .NET.

### Voorbeeldbroncode voor Emphases met Aspose.Words voor .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### Veelgestelde vragen

#### Vraag: Hoe markeer ik tekst met Markdown?

 A: Om tekst te markeren met Markdown, omringt u de tekst eenvoudigweg met de juiste symbolen. Gebruik`*` of`_` voor cursief,`**` of`__` voor vetgedrukt, en`~~` voor doorhalen.

#### Vraag: Kunnen we verschillende hoogtepunten in dezelfde tekst combineren?

 A: Ja, het is mogelijk om verschillende highlights in dezelfde tekst te combineren. U kunt een woord bijvoorbeeld vet en cursief maken door beide te gebruiken`**`En`*` over de hele wereld.

#### Vraag: Welke markeringsopties zijn beschikbaar in Markdown?

A: De markeringsopties die beschikbaar zijn in Markdown zijn cursief (`*` of`_`), vetgedrukt (`**` of`__`), en doorhalen (`~~`).

#### Vraag: Hoe ga ik om met gevallen waarin de tekst speciale tekens bevat die door Markdown worden gebruikt om te markeren?

 A: Als uw tekst speciale tekens bevat die door Markdown worden gebruikt voor het markeren, kunt u hieraan ontsnappen door er een a voor te zetten`\` . Bijvoorbeeld,`\*` wordt een letterlijk asterisk weergegeven.

#### Vraag: Kunnen we het uiterlijk van de markering aanpassen met CSS?

A: Markering in Markdown wordt meestal weergegeven met de standaardstijlen van de browser. Als u uw Markdown naar HTML converteert, kunt u de weergave van de markering aanpassen met behulp van CSS-regels.