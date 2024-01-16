---
title: Ga naar tabelcel in Word-document
linktitle: Ga naar tabelcel in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het gebruik van Verplaatsen naar tabelcel in de Word-documentfunctie van Aspose.Words voor .NET
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/move-to-table-cell/
---
In dit voorbeeld laten we u stap voor stap zien hoe u de functie Verplaatsen naar tabelcel in Word-documenten van Aspose.Words voor .NET kunt gebruiken met behulp van de meegeleverde C#-broncode. Met deze functie kunt u door specifieke cellen in een tabel in een Word-document navigeren en deze manipuleren. Volg onderstaande stappen om deze functionaliteit in uw applicatie te integreren.

## Stap 1: Laad het document met de tabel

Eerst moeten we het document laden dat de tabel bevat waarnaar we de cel willen verplaatsen. Gebruik de volgende code om deze stap uit te voeren:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Deze code laadt het opgegeven document (vervang "MyDir +"Tables.docx"" met het daadwerkelijke pad van uw document dat de tabel bevat).

## Stap 2: Verplaats de DocumentBuilder naar een specifieke tabelcel

Vervolgens verplaatsen we de DocumentBuilder naar een specifieke tabelcel. Gebruik de volgende code om deze stap uit te voeren:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

Deze code maakt een DocumentBuilder van het bestaande document en verplaatst vervolgens de cursor van de DocumentBuilder naar de opgegeven tabelcel. Ten slotte voegt het inhoud aan die cel toe met behulp van DocumentBuilder`Write()` methode.

## Stap 3: Controleer het resultaat

U kunt nu verifiëren dat de verplaatsing naar de tabelcel is gelukt. Gebruik de volgende code om deze stap uit te voeren:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Deze code verifieert dat de opgegeven cel inderdaad de huidige cel van DocumentBuilder is. Het controleert ook of de door DocumentBuilder toegevoegde inhoud correct is opgeslagen in de tabelcel.

Dat is alles ! U hebt nu begrepen hoe u de functionaliteit voor verplaatsen naar tabelcellen van Aspose.Words voor .NET kunt gebruiken met behulp van de meegeleverde broncode. U kunt deze functionaliteit nu in uw eigen applicatie integreren en specifieke tabelcellen in Word-documenten manipuleren.


### Voorbeeldbroncode voor het verplaatsen naar een tabelcel met Aspose.Words voor .NET


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Verplaats de bouwer naar rij 3, cel 4 van de eerste tabel.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## Conclusie

In dit voorbeeld hebben we de functie Verplaatsen naar tabelcel van Aspose.Words voor .NET onderzocht. We hebben geleerd hoe we een document met een tabel kunnen laden, de DocumentBuilder naar een specifieke tabelcel kunnen verplaatsen en inhoud aan die cel kunnen toevoegen. Deze functie biedt ontwikkelaars krachtige tools om programmatisch door specifieke cellen in Word-documenttabellen te navigeren en deze te manipuleren met behulp van Aspose.Words voor .NET. Het kan een waardevolle aanvulling zijn op uw toepassing voor dynamische Word-documentverwerking en tabelinhoudbeheer.

### Veelgestelde vragen over het verplaatsen naar een tabelcel in een Word-document

#### Vraag: Wat is het doel van de functie Verplaatsen naar tabelcel in Aspose.Words voor .NET?

A: Met de functie Verplaatsen naar tabelcel in Aspose.Words voor .NET kunnen ontwikkelaars programmatisch naar specifieke cellen in een tabel in een Word-document navigeren en deze manipuleren. Het biedt de mogelijkheid om inhoud in een bepaalde cel in te voegen, te wijzigen of te verwijderen.

#### Vraag: Hoe verplaats ik de DocumentBuilder naar een specifieke tabelcel in een Word-document?

A: Om DocumentBuilder naar een specifieke tabelcel in een Word-document te verplaatsen, kunt u de MoveToCell-methode van de DocumentBuilder-klasse gebruiken. Deze methode neemt de indices van de doelrij en -cel in de tabel als parameters en plaatst de cursor aan het begin van die cel.

#### Vraag: Kan ik inhoud toevoegen of wijzigen nadat ik naar een specifieke tabelcel ben gegaan met behulp van de functie Verplaatsen naar tabelcel?

A: Ja, zodra DocumentBuilder met MoveToCell in de gewenste tabelcel is geplaatst, kunt u verschillende methoden van de klasse DocumentBuilder gebruiken, zoals Write, Writeln of InsertHtml, om de inhoud van die cel toe te voegen of te wijzigen.

#### Vraag: Hoe kan ik controleren of de verplaatsing naar de tabelcel is gelukt?

A: U kunt de succesvolle verplaatsing naar de tabelcel verifiëren door de positie van de DocumentBuilder-cursor te controleren. U kunt bijvoorbeeld het huidige knooppunt van DocumentBuilder vergelijken met de cel waarnaar u wilt verplaatsen en controleren of de door DocumentBuilder toegevoegde inhoud correct is opgeslagen in de tabelcel.