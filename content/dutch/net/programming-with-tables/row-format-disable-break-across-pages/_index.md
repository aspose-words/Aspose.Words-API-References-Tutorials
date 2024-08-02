---
title: Rijopmaak Schakel het verdelen over pagina's uit
linktitle: Rijopmaak Schakel het verdelen over pagina's uit
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u rijeinden op pagina's in Word-documenten kunt uitschakelen met Aspose.Words voor .NET om de leesbaarheid en opmaak van tabellen te behouden.
type: docs
weight: 10
url: /nl/net/programming-with-tables/row-format-disable-break-across-pages/
---
## Invoering

Wanneer u met tabellen in Word-documenten werkt, wilt u er wellicht voor zorgen dat rijen niet over pagina's heen lopen, wat essentieel kan zijn voor het behoud van de leesbaarheid en opmaak van uw documenten. Aspose.Words voor .NET biedt een eenvoudige manier om rij-einden op pagina's uit te schakelen.

In deze zelfstudie leiden we u door het proces van het uitschakelen van rij-einden op pagina's in een Word-document met behulp van Aspose.Words voor .NET.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Een Word-document met een tabel die meerdere pagina's beslaat.

## Naamruimten importeren

Importeer eerst de benodigde naamruimten in uw project:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Stap 1: Laad het document

Laad het document met de tabel die meerdere pagina's beslaat.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Stap 2: Toegang tot de tabel

Toegang tot de eerste tabel in het document. Hierbij wordt ervan uitgegaan dat de tabel die u wilt wijzigen de eerste tabel in het document is.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Stap 3: Schakel het doorbreken van pagina's voor alle rijen uit

 Loop door elke rij in de tabel en stel de in`AllowBreakAcrossPages`eigendom aan`false`. Dit zorgt ervoor dat rijen niet over pagina's heen breken.

```csharp
// Schakel het opsplitsen van pagina's uit voor alle rijen in de tabel.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Stap 4: Sla het document op

Sla het gewijzigde document op in de door u opgegeven map.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusie

In deze zelfstudie hebben we gedemonstreerd hoe u rijeinden op pagina's in een Word-document kunt uitschakelen met behulp van Aspose.Words voor .NET. Door de hierboven beschreven stappen te volgen, kunt u ervoor zorgen dat uw tabelrijen intact blijven en niet over pagina's worden gesplitst, waardoor de leesbaarheid en opmaak van het document behouden blijven.

## Veelgestelde vragen

### Kan ik rij-einden op pagina's uitschakelen voor een specifieke rij in plaats van voor alle rijen?  
 Ja, u kunt rij-einden voor specifieke rijen uitschakelen door naar de gewenste rij te gaan en deze in te stellen`AllowBreakAcrossPages`eigendom aan`false`.

### Werkt deze methode voor tabellen met samengevoegde cellen?  
 Ja, deze methode werkt voor tabellen met samengevoegde cellen. Het eigendom`AllowBreakAcrossPages` is van toepassing op de hele rij, ongeacht het samenvoegen van cellen.

### Werkt deze methode als de tabel in een andere tabel is genest?  
Ja, u kunt geneste tabellen op dezelfde manier openen en wijzigen. Zorg ervoor dat u op de juiste manier naar de geneste tabel verwijst via de index of andere eigenschappen.

### Hoe kan ik controleren of een rij over pagina's heen kan worden verdeeld?  
 U kunt controleren of een rij het mogelijk maakt om over pagina's heen te breken door naar het`AllowBreakAcrossPages` eigendom van de`RowFormat` en de waarde ervan controleren.

### Is er een manier om deze instelling op alle tabellen in een document toe te passen?  
Ja, u kunt alle tabellen in het document doorlopen en deze instelling op elke tabel toepassen.