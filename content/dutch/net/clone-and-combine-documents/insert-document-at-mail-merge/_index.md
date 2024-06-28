---
title: Document invoegen bij samenvoegen
linktitle: Document invoegen bij samenvoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u documenten invoegt in samenvoegvelden met Aspose.Words voor .NET in deze uitgebreide, stapsgewijze zelfstudie.
type: docs
weight: 10
url: /nl/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## Invoering

Welkom in de wereld van documentautomatisering met Aspose.Words voor .NET! Heeft u zich ooit afgevraagd hoe u tijdens een samenvoegbewerking documenten dynamisch in specifieke velden in een hoofddocument kunt invoegen? Nou, je bent op de juiste plek. Deze zelfstudie leidt u stap voor stap door het proces van het invoegen van documenten in samenvoegvelden met behulp van Aspose.Words voor .NET. Het is alsof je een puzzel in elkaar puzzelt, waarbij elk stukje perfect op zijn plaats valt. Dus laten we erin duiken!

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

1.  Aspose.Words voor .NET: dat kan[download hier de nieuwste versie](https://releases.aspose.com/words/net/) . Als u een licentie moet aanschaffen, kunt u dat doen[hier](https://purchase.aspose.com/buy) . Als alternatief kunt u een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) of probeer het eens met een[gratis proefperiode](https://releases.aspose.com/).
2. Ontwikkelomgeving: Visual Studio of een andere C# IDE.
3. Basiskennis van C#: Bekendheid met programmeren in C# maakt deze tutorial een fluitje van een cent.

## Naamruimten importeren

Allereerst moet u de benodigde naamruimten importeren. Dit zijn een soort bouwstenen van uw project.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Laten we het proces opsplitsen in beheersbare stappen. Elke stap bouwt voort op de vorige en leidt u naar een complete oplossing.

## Stap 1: Uw directory instellen

Voordat u documenten kunt invoegen, moet u het pad naar uw documentenmap definiëren. Hier worden uw documenten opgeslagen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Het hoofddocument laden

Vervolgens laadt u het hoofddocument. Dit document bevat de samenvoegvelden waarin andere documenten worden ingevoegd.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## Stap 3: Instellen van het terugbellen bij veldsamenvoeging

Om het samenvoegproces af te handelen, moet u een callback-functie instellen. Deze functie is verantwoordelijk voor het invoegen van documenten in de opgegeven samenvoegvelden.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Stap 4: De samenvoegbewerking uitvoeren

Nu is het tijd om de samenvoegbewerking uit te voeren. Dit is waar de magie gebeurt. U specificeert het samenvoegveld en het document dat in dit veld moet worden ingevoegd.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Stap 5: Het document opslaan

Nadat het samenvoegen is voltooid, slaat u het gewijzigde document op. Dit nieuwe document heeft de ingevoegde inhoud precies waar u deze wilt hebben.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Stap 6: De callback-handler maken

De callback-handler is een klasse die speciale verwerking voor het samenvoegveld uitvoert. Het laadt het document dat is opgegeven in de veldwaarde en voegt het in het huidige samenvoegveld in.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## Stap 7: Het document invoegen

Deze methode voegt het opgegeven document in de huidige alinea of tabelcel in.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## Conclusie

En daar heb je het! U hebt met succes documenten in specifieke velden ingevoegd tijdens een samenvoegbewerking met Aspose.Words voor .NET. Deze krachtige functie kan u veel tijd en moeite besparen, vooral als u met grote hoeveelheden documenten werkt. Zie het als een persoonlijke assistent die al het zware werk voor u doet. Dus ga je gang en probeer het eens. Veel codeerplezier!

## Veelgestelde vragen

### Kan ik meerdere documenten in verschillende samenvoegvelden invoegen?
 Ja, dat kan. Geef eenvoudigweg de juiste samenvoegvelden en bijbehorende documentpaden op in het`MailMerge.Execute` methode.

### Is het mogelijk om het ingevoegde document anders op te maken dan het hoofddocument?
 Absoluut! U kunt gebruik maken van de`ImportFormatMode` parameters in de`NodeImporter` om de opmaak te controleren.

### Wat moet ik doen als de samenvoegveldnaam dynamisch is?
U kunt dynamische samenvoegveldnamen afhandelen door ze als parameters door te geven aan de callback-handler.

### Kan ik deze methode gebruiken met verschillende bestandsformaten?
Ja, Aspose.Words ondersteunt verschillende bestandsindelingen, waaronder DOCX, PDF en meer.

### Hoe ga ik om met fouten tijdens het documentinvoegproces?
Implementeer foutafhandeling in uw callback-handler om eventuele uitzonderingen te beheren.