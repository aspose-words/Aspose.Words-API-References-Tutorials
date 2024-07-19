---
title: Voorkeursbesturingstype in Word-document
linktitle: Voorkeursbesturingstype in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het opgeven van het gewenste besturingstype in een Word-document bij het laden van een HTML-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlloadoptions/preferred-control-type/
---
Dit artikel biedt een stapsgewijze handleiding voor het gebruik van de functie van het voorkeursbesturingstype met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze tutorial zult u begrijpen hoe u het gewenste besturingstype kunt opgeven bij het laden van een HTML-document.

Zorg ervoor dat u, voordat u begint, de Aspose.Words voor .NET-bibliotheek in uw project hebt geïnstalleerd en geconfigureerd. U kunt de bibliotheek en installatie-instructies vinden op de Aspose-website.

## Stap 1: Definieer de HTML-code

 Om te beginnen moet u de HTML-code definiëren die u als document wilt laden. In dit voorbeeld hebben we een gedefinieerd`html` variabele die de HTML-code van een selector met opties bevat.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Stap 2: Stel HTML-laadopties in

 Vervolgens maken we een`HtmlLoadOptions` bezwaar maken en instellen`PreferredControlType`eigendom aan`HtmlControlType.StructuredDocumentTag`. Dit vertelt Aspose.Words om StructuredDocumentTags te gebruiken om HTML weer te geven tijdens het laden.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Stap 3: Laad het document en sla het op

 Wij gebruiken de`Document` class om HTML-code uit een geheugenstroom te laden met de eerder gedefinieerde laadopties. Vervolgens slaan we het document op in de opgegeven map met de extensie`.docx`bestandsformaat.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Voorbeeldbroncode voor het voorkeursbesturingstype met Aspose.Words voor .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Dat is alles ! U hebt met succes het gewenste besturingstype opgegeven bij het laden van een HTML-document met Aspose.Words voor .NET.

## Conclusie

 Door deze stapsgewijze handleiding te volgen, heeft u geleerd hoe u de functie "Voorkeursbesturingstype" in Aspose.Words voor .NET kunt gebruiken om het gewenste besturingstype op te geven bij het laden van een HTML-document. Het instellen van de`PreferredControlType`eigendom aan`HtmlControlType.StructuredDocumentTag` staat Aspose.Words toe om StructuredDocumentTags (SDT) te gebruiken voor een betere weergave en verwerking van HTML-inhoud. U kunt ook andere soorten besturingselementen verkennen, afhankelijk van uw specifieke vereisten. Het gebruik van deze functie zorgt voor een nauwkeurige en efficiënte verwerking van HTML-documenten in uw C#-toepassing met Aspose.Words.

### Veelgestelde vragen over het gewenste besturingstype in een Word-document

#### Vraag: Wat is de functie "Voorkeursbesturingstype" in Aspose.Words voor .NET?

A: Met de functie "Voorkeurstype besturingselement" kunt u het voorkeurstype besturingselement specificeren om HTML-elementen weer te geven bij het laden van een HTML-document. Het helpt bij het selecteren van het juiste besturingstype voor een betere weergave en verwerking van de HTML-inhoud.

#### Vraag: Hoe stel ik het gewenste besturingstype in bij het laden van een HTML-document?

 A: Om het gewenste besturingstype in te stellen, moet u een`HtmlLoadOptions` object en stel het in`PreferredControlType` eigendom naar wens`HtmlControlType` . In het gegeven voorbeeld,`HtmlControlType.StructuredDocumentTag` is gebruikt.

#### Vraag: Wat is de betekenis van het gebruik van StructuredDocumentTags (SDT) als het voorkeursbesturingstype?

A: StructuredDocumentTags (SDT) zijn op XML gebaseerde elementen die kunnen worden gebruikt om complexe inhoud en besturingselementen in een Word-document weer te geven. Het gebruik van SDT's als voorkeursbesturingstype kan zorgen voor een betere compatibiliteit en weergave van HTML-inhoud.

#### Vraag: Hoe kan ik ervoor zorgen dat Aspose.Words het gewenste besturingstype gebruikt bij het laden van het HTML-document?

 A: Door het instellen van de`PreferredControlType`eigendom aan`HtmlControlType.StructuredDocumentTag`zoals weergegeven in de voorbeeldbroncode, gebruikt Aspose.Words SDT's om HTML-elementen weer te geven bij het laden van het document.

#### Vraag: Kan ik andere soorten besturingselementen als voorkeursoptie gebruiken?

 A: Ja, behalve`HtmlControlType.StructuredDocumentTag` , Aspose.Words voor .NET ondersteunt andere besturingstypen, zoals`HtmlControlType.ContentControl`En`HtmlControlType.CustomXmlMarkup`.