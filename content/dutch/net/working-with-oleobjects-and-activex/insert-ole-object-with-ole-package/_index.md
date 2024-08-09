---
title: Voeg Ole-object in Word in met Ole-pakket
linktitle: Voeg Ole-object in Word in met Ole-pakket
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u OLE-objecten in Word-documenten invoegt met Aspose.Words voor .NET. Volg onze gedetailleerde stapsgewijze handleiding om bestanden naadloos in te sluiten.
type: docs
weight: 10
url: /nl/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---
## Invoering

Als u ooit een bestand in een Word-document heeft willen insluiten, bent u hier aan het juiste adres. Of het nu een ZIP-bestand, een Excel-werkblad of een ander bestandstype is, het rechtstreeks insluiten in uw Word-document kan ongelooflijk handig zijn. Zie het als een geheim compartiment in uw document waarin u allerlei schatten kunt opbergen. En vandaag gaan we bekijken hoe u dit kunt doen met Aspose.Words voor .NET. Klaar om een Word-wizard te worden? Laten we erin duiken!

## Vereisten

Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1. Aspose.Words voor .NET: Als je dat nog niet hebt gedaan, download het dan van[hier](https://releases.aspose.com/words/net/).
2. Een ontwikkelomgeving: Visual Studio of een andere .NET-ontwikkelomgeving.
3. Basiskennis van C#: U hoeft geen expert te zijn, maar uw weg kennen in C# kan helpen.
4. Een Document Directory: Een map waarin u documenten kunt opslaan en ophalen.

## Naamruimten importeren

Laten we eerst en vooral onze naamruimten op orde brengen. U moet de volgende naamruimten in uw project opnemen:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Laten we dit opsplitsen in hapklare stappen, zodat het gemakkelijk te volgen is.

## Stap 1: Stel uw document in

Stel je voor dat je een kunstenaar bent met een leeg canvas. Ten eerste hebben we ons lege canvas nodig, ons Word-document. Zo stel je het in:

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Deze code initialiseert een nieuw Word-document en stelt een DocumentBuilder in, die we zullen gebruiken om inhoud in ons document in te voegen.

## Stap 2: Lees uw Ole-object

Laten we vervolgens het bestand lezen dat u wilt insluiten. Zie dit als het oppakken van de schat die je in je geheime compartiment wilt verstoppen:

```csharp
byte[] bs = File.ReadAllBytes(dataDir + "Zip file.zip");
```

Deze regel leest alle bytes uit uw ZIP-bestand en slaat ze op in een byte-array.

## Stap 3: Plaats het Ole-object

Nu komt het magische gedeelte. We gaan het bestand insluiten in ons Word-document:

```csharp
using (Stream stream = new MemoryStream(bs))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);
    OlePackage olePackage = shape.OleFormat.OlePackage;
    olePackage.FileName = "filename.zip";
    olePackage.DisplayName = "displayname.zip";
}
```

 Hier maken we een geheugenstroom van de byte-array en gebruiken we de`InsertOleObject` methode om het in het document in te sluiten. We stellen ook de bestandsnaam en weergavenaam voor het ingesloten object in.

## Stap 4: Bewaar uw document

Laten we tot slot ons meesterwerk redden:

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Hiermee wordt het document met uw ingesloten bestand in de opgegeven map opgeslagen.

## Conclusie

En daar heb je het! U hebt met succes een OLE-object in een Word-document ingesloten met behulp van Aspose.Words voor .NET. Het is alsof u een verborgen juweeltje in uw document toevoegt dat op elk moment kan worden onthuld. Deze techniek kan ongelooflijk nuttig zijn voor een verscheidenheid aan toepassingen, van technische documentatie tot dynamische rapporten. 

## Veelgestelde vragen

### Kan ik met deze methode andere bestandstypen insluiten?
Ja, u kunt verschillende bestandstypen insluiten, zoals Excel-werkbladen, pdf's en afbeeldingen.

### Heb ik een licentie nodig voor Aspose.Words?
 Ja, u heeft een geldige licentie nodig. Je kunt een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor evaluatie.

### Hoe kan ik de weergavenaam van het OLE-object aanpassen?
 U kunt de`DisplayName` eigendom van de`OlePackage` om het aan te passen.

### Is Aspose.Words compatibel met .NET Core?
Ja, Aspose.Words ondersteunt zowel .NET Framework als .NET Core.

### Kan ik het ingesloten OLE-object in het Word-document bewerken?
Nee, u kunt het OLE-object niet rechtstreeks in Word bewerken. U moet het openen in de oorspronkelijke toepassing.