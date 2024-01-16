---
title: Doorhalen
linktitle: Doorhalen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de doorgehaalde tekststijl toepast met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/strikethrough/
---


In dit voorbeeld laten we u zien hoe u de doorgehaalde tekststijl kunt toepassen met Aspose.Words voor .NET. Doorgestreepte tekst wordt gebruikt om aan te geven dat de tekst is verwijderd of niet langer geldig is.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Pas doorgestreepte tekststijl toe

We zullen de doorgehaalde tekststijl inschakelen door de`StrikeThrough` eigendom van de`Font` bezwaar tegen`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Stap 3: Voeg doorgehaalde tekst toe

 We kunnen nu doorgehaalde tekst toevoegen met behulp van de documentgenerator`Writeln` methode.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Voorbeeldbroncode voor doorgehaalde tekst met Aspose.Words voor .NET

```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

// Maak de tekst doorgehaald.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Gefeliciteerd! U hebt nu geleerd hoe u de doorgehaalde tekststijl kunt toepassen met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe kan ik de doorgehaalde tekst toevoegen in Aspose.Words?

 A: Om de doorgehaalde tekst in Aspose.Words toe te voegen, kunt u de`Font.StrikeThrough` eigendom van de`Run` voorwerp. U kunt deze eigenschap instellen op`true` om doorgehaalde tekst toe te voegen aan specifieke tekst. U kunt bijvoorbeeld gebruiken`run.Font.StrikeThrough=true` om de doorgestreepte tekst toe te voegen aan het`Run` voorwerp.

#### Vraag: Is het mogelijk om de doorgestreepte tekst toe te voegen aan verschillende stukken tekst in dezelfde alinea?

 A: Ja, u kunt doorgestreepte tekst toevoegen aan meerdere tekstdelen in één alinea door er meerdere te gebruiken`Run` voorwerpen. Je kunt er meerdere maken`Run` objecten en stel de in`Font.StrikeThrough`eigendom aan`true` voor elk object om de doorgestreepte tekst aan de gewenste tekstdelen toe te voegen. Vervolgens kunt u ze aan de alinea toevoegen met behulp van de`Paragraph.AppendChild(run)` methode.

#### Vraag: Kan ik doorgehaalde tekst toevoegen aan tekst die in een tabel of cel in Aspose.Words staat?

 A: Ja, u kunt doorgehaalde tekst toevoegen aan tekst in een tabel of cel in Aspose.Words. U kunt met de juiste methoden naar de gewenste cel of alinea springen en vervolgens de doorgestreepte tekstopmaak toepassen met behulp van de`Font.StrikeThrough` eigendom van de`Run` of`Paragraph` voorwerp.