---
title: Escape-URI in PDF-document
linktitle: Escape-URI in PDF-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding URI in PDF-documenten ontsnappen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/escape-uri/
---

Dit artikel biedt een stapsgewijze handleiding voor het escapen van URI in een PDF-document met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze zelfstudie begrijpt u hoe u hyperlinks met ontsnapte Uri in een document kunt invoegen.

Zorg ervoor dat u, voordat u begint, de Aspose.Words voor .NET-bibliotheek in uw project hebt geïnstalleerd en geconfigureerd. U kunt de bibliotheek en installatie-instructies vinden op de Aspose-website.

## Stap 1: Definieer de documentmap

 Om te beginnen moet u het pad definiëren naar de map waar uw documenten zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een document en een DocumentBuilder

 Vervolgens moeten we een nieuwe maken`Document` voorwerp en een`DocumentBuilder` object om het document samen te stellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg hyperlinks in met ontsnapte Uri

 Gebruik de`InsertHyperlink` werkwijze van de`DocumentBuilder` object om hyperlinks in het document in te voegen. Uri moet worden geëscaped met behulp van de`Uri.EscapeUriString` functie om formaatfouten te voorkomen.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fde%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## Stap 4: Sla het document op als PDF

 Ten slotte kunnen we het document opslaan als PDF met behulp van de`Save` werkwijze van de`Document` voorwerp. Geef de naam van het uitvoerbestand op.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Dat is alles ! U hebt met succes hyperlinks met ontsnapte Uri's ingevoegd in een document met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor het ontsnappen van Uri met Aspose.Words voor .NET


```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fde%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## Conclusie

In deze zelfstudie hebben we besproken hoe u URI's in een PDF-document kunt escapen met Aspose.Words voor .NET. Door URI's te escapen, kunt u opmaakfouten voorkomen en ervoor zorgen dat hyperlinks correct worden geïnterpreteerd en weergegeven in het PDF-document. Volg de beschreven stappen om hyperlinks met ontsnapte URI's in uw PDF-document in te voegen. Zorg ervoor dat je ontsnapt.

### Veel Gestelde Vragen

#### Vraag: Wat is de escape-URI in een PDF-document en waarom is deze belangrijk?
A: Escape-URI in een PDF-document verwijst naar de methode voor het converteren van speciale tekens in een URL naar escape-reeksen om opmaakfouten te voorkomen. Dit is belangrijk omdat speciale tekens in een URL de structuur van de URL kunnen verstoren en tot verkeerde interpretaties of onjuiste weergave kunnen leiden. Door de speciale tekens te escapen, garanderen we dat de URL correct wordt geïnterpreteerd en weergegeven in het PDF-document.

#### Vraag: Hoe kan ik Aspose.Words voor .NET gebruiken om URI's in een PDF-document te escapen?
A: Volg deze stappen om URI's in een PDF-document te escapen met Aspose.Words voor .NET:

 Stel het mappad in waar uw documenten zich bevinden door te vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad van uw documentenmap.

 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder` object om het document samen te stellen.

 Gebruik de`InsertHyperlink` werkwijze van de`DocumentBuilder` object om hyperlinks in het document in te voegen. Zorg ervoor dat u de URI escapet met behulp van de`Uri.EscapeUriString` functie om formaatfouten te voorkomen.

 Gebruik de`Save` werkwijze van de`Document` object om het document in PDF-indeling op te slaan door de naam van het uitvoerbestand op te geven.

#### Vraag: Wat zijn de voordelen van het escapen van URI's in een PDF-document?
A: De voordelen van het ontsnappen van URI in een PDF-document zijn:

Voorkomen van opmaakfouten: URI-escaping helpt formaatfouten te voorkomen die worden veroorzaakt door speciale tekens in een URL, zodat de URL correct wordt geïnterpreteerd en weergegeven in het PDF-document.

Compatibiliteit met PDF-lezers: Escaped URI's worden over het algemeen goed ondersteund door PDF-lezers, wat een betere compatibiliteit en een consistente gebruikerservaring garandeert.

#### Vraag: Aan welke speciale tekens moet een escapeteken worden toegevoegd in een URI?
 A: De speciale tekens die in een URI moeten worden geëscaped zijn: spatie, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.