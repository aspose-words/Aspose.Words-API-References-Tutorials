---
title: Tafel
linktitle: Tafel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel maakt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/table/
---


In dit voorbeeld laten we u zien hoe u een tabel maakt met Aspose.Words voor .NET. Een tabel is een gegevensstructuur die informatie in rijen en kolommen organiseert.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Stap 2: Voeg cellen en gegevens toe

 We zullen cellen en gegevens aan onze tabel toevoegen met behulp van de`InsertCell` methode en de`Writeln` methode van de documentgenerator.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Voorbeeldbroncode voor het maken van een tabel met Aspose.Words voor .NET

```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

// Voeg de eerste rij toe.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// Voeg de tweede rij toe.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

Gefeliciteerd! Je hebt nu geleerd hoe je een tabel kunt maken met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe maak ik een tabel in Markdown?

A: Om een tabel in Markdown te maken, gebruik je de syntaxis van pipelines (`|`om cellen en streepjes af te bakenen (`-`) om tabelkoppen te scheiden.

#### Vraag: Kunnen we het uiterlijk van een tabel in Markdown aanpassen?

A: Bij standaard Markdown zijn de opties voor het aanpassen van tabellen beperkt. Met sommige Markdown-editors kunt u echter CSS-stijlen aan tabellen toevoegen om hun uiterlijk aan te passen.

#### Vraag: Hoe kan ik cellen in een tabel samenvoegen in Markdown?

A: Het samenvoegen van cellen in een tabel in Markdown is afhankelijk van de gebruikte Markdown-editor. Sommige Markdown-editors ondersteunen het samenvoegen van cellen met behulp van een specifieke syntaxis.

#### Vraag: Ondersteunen tabellen in Markdown CSS-stijlen?

A: In standaard Markdown bieden tabellen geen directe ondersteuning voor CSS-stijlen. Met sommige Markdown-editors kunt u echter CSS-stijlen aan tabellen toevoegen om hun uiterlijk aan te passen.

#### Vraag: Kunnen we links of tekst in inline-indeling toevoegen aan de cellen van een tabel in Markdown?

A: Ja, u kunt koppelingen of inline tekst toevoegen aan tabelcellen in Markdown met behulp van de juiste Markdown-syntaxis.