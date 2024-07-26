---
title: Lijst met opsommingstekens
linktitle: Lijst met opsommingstekens
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een lijst met opsommingstekens maakt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/bulleted-list/
---

In deze zelfstudie gaan we u vertellen hoe u een lijst met opsommingstekens kunt maken met Aspose.Words voor .NET. Een lijst met opsommingstekens wordt gebruikt om items weer te geven zonder nummering.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Een standaardlijst met opsommingstekens toepassen

 We kunnen een standaardlijst met opsommingstekens toepassen met behulp van de documentbuilder`ApplyBulletDefault` methode.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Stap 3: Het opsommingstekenformaat aanpassen

 We kunnen het opsommingstekenformaat aanpassen door toegang te krijgen tot de eigenschappen van`ListFormat.List.ListLevels[0]`. In dit voorbeeld gebruiken we het streepje "-" als opsommingsteken.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Stap 4: Items aan de lijst toevoegen

 Nu kunnen we items toevoegen aan de lijst met opsommingstekens met behulp van de documentbuilder`Writeln` methode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Stap 5: Inspringing uit de lijst verwijderen

 Als we een sublijst willen maken, kunnen we de inspringing vergroten met behulp van de`ListFormat.ListIndent()` methode. In dit voorbeeld voegen we een sublijst toe aan de items 2a en 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Voorbeeldbroncode voor Lijst met opsommingstekens met Aspose.Words voor .NET


```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Gefeliciteerd! U hebt nu geleerd hoe u een lijst met opsommingstekens kunt maken met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe maak ik een lijst met opsommingen in Markdown?

A: Om een lijst met opsommingen te maken in Markdown, begint u elk lijstitem met een opsommingsteken (`-`, `*` , of`+`), gevolgd door een spatie.

#### Vraag: Kun je lijsten met opsommingstekens nesten in Markdown?

A: Ja, het is mogelijk om lijsten met opsommingstekens in Markdown te nesten door vier spaties toe te voegen vóór elk genest lijstitem.

#### Vraag: Hoe kan ik opsommingstekens aanpassen?

A: In standaard Markdown zijn opsommingstekens vooraf gedefinieerd. Met sommige Markdown-editors kunt u ze echter aanpassen met specifieke extensies.

#### Vraag: Ondersteunen lijsten met opsommingstekens in Markdown inspringen?

A: Ja, lijsten met opsommingstekens in Markdown ondersteunen inspringen. U kunt een verschuiving naar links toevoegen met behulp van spaties of tabs.

#### Vraag: Kunnen links of inline tekst worden toegevoegd aan lijstitems?

A: Ja, u kunt links of inline tekst toevoegen aan lijstitems met behulp van de juiste Markdown-syntaxis.
