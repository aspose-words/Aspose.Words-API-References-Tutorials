---
title: Vetgedrukte tekst
linktitle: Vetgedrukte tekst
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tekst vetgedrukt maakt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/bold-text/
---

In dit voorbeeld gaan we u vertellen hoe u tekst vetgedrukt kunt maken met Aspose.Words voor .NET. Door tekst vetgedrukt te maken, wordt deze beter zichtbaar en krijgt deze meer aandacht.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Vetgedrukte tekst

 We kunnen de tekst vetgedrukt maken door de documentbuilder in te stellen`Font.Bold`eigendom aan`true`.

```csharp
builder.Font.Bold = true;
```

## Stap 3: Voeg inhoud toe aan het document

 Nu kunnen we inhoud aan het document toevoegen met behulp van de documentbuilder-methoden, zoals`Writeln`, waarmee een regel tekst wordt toegevoegd.

```csharp
builder.Writeln("This text will be bold");
```

## Voorbeeldbroncode voor vetgedrukte tekst met Aspose.Words voor .NET


```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

// Maak de tekst vetgedrukt.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Gefeliciteerd! U hebt nu geleerd hoe u tekst vetgedrukt kunt maken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Hoe kan ik tekst vetgedrukt maken in Aspose.Words?

 A: Om tekst vetgedrukt te maken in Aspose.Words, kunt u de`Font.Bold` eigendom van de`Run`voorwerp. U kunt deze eigenschap instellen op`true` om specifieke tekst vet te maken. U kunt bijvoorbeeld gebruiken`run.Font.Bold=true` om de tekst binnenin vet te maken`Run` voorwerp.

#### Vraag: Is het mogelijk om meerdere stukken tekst in dezelfde alinea vet te maken?

 A: Ja, u kunt meerdere stukken tekst in één alinea vetgedrukt maken door er meerdere te gebruiken`Run` voorwerpen. Je kunt er meerdere maken`Run` objecten en stel de in`Font.Bold`eigendom aan`true` voor elk object om de gewenste delen van de tekst vet te maken. Vervolgens kunt u ze aan de alinea toevoegen met behulp van de`Paragraph.AppendChild(run)` methode.

#### Vraag: Kan ik tekst in een tabel of cel in Aspose.Words vetgedrukt maken?

 A: Ja, u kunt tekst in een tabel of cel in Aspose.Words vetgedrukt maken. U kunt met behulp van de juiste methoden naar de gewenste cel of alinea navigeren en vervolgens de vetgedrukte opmaak toepassen met behulp van de`Font.Bold` eigendom van de`Run` of`Paragraph` voorwerp.