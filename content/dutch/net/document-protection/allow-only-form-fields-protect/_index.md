---
title: Sta alleen formuliervelden toe in Word-document
linktitle: Sta alleen formuliervelden toe in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Word-documenten kunt beveiligen, zodat alleen formuliervelden kunnen worden bewerkt met Aspose.Words voor .NET. Volg onze gids om ervoor te zorgen dat uw documenten veilig en gemakkelijk te bewerken zijn.
type: docs
weight: 10
url: /nl/net/document-protection/allow-only-form-fields-protect/
---
## Invoering

Hallo daar! Heeft u ooit specifieke delen van een Word-document moeten beschermen terwijl andere delen bewerkbaar moesten blijven? Aspose.Words voor .NET maakt dit supergemakkelijk. In deze zelfstudie gaan we dieper in op de manier waarop u in een Word-document alleen bescherming van formuliervelden kunt toestaan. Aan het einde van deze handleiding beschikt u over een gedegen kennis van documentbeveiliging met Aspose.Words voor .NET. Klaar? Laten we erin springen!

## Vereisten

Voordat we ingaan op het codeergedeelte, zorgen we ervoor dat je alles hebt wat je nodig hebt:

1.  Aspose.Words voor .NET-bibliotheek: u kunt het downloaden van[hier](https://releases.aspose.com/words/net/).
2. Visual Studio: Elke recente versie werkt prima.
3. Basiskennis van C#: Als u de basisbeginselen begrijpt, kunt u de tutorial volgen.

## Naamruimten importeren

Allereerst moeten we de benodigde naamruimten importeren. Hiermee wordt onze omgeving ingesteld op het gebruik van Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Stap 1: Stel uw project in

Maak een nieuw project in Visual Studio  
Open Visual Studio en maak een nieuw Console App-project (.NET Core). Noem het iets betekenisvols, zoals "AsposeWordsProtection".

## Stap 2: Installeer Aspose.Words voor .NET

Installeer via NuGet Package Manager  
Klik met de rechtermuisknop op uw project in de Solution Explorer, selecteer "NuGet-pakketten beheren" en zoek naar`Aspose.Words`. Installeer het.

## Stap 3: Initialiseer het document

Maak een nieuw Document-object  
Laten we beginnen met het maken van een nieuw document en een documentbouwer om wat tekst toe te voegen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialiseer een nieuw document en DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

 Hier maken we een nieuwe`Document`En`DocumentBuilder` voorbeeld. De`DocumentBuilder` stelt ons in staat tekst aan ons document toe te voegen.

## Stap 4: Bescherm het document

Pas beveiliging toe waardoor alleen formuliervelden kunnen worden bewerkt  
Laten we nu de bescherming aan ons document toevoegen.

```csharp
// Beveilig het document, zodat alleen formuliervelden kunnen worden bewerkt
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Deze coderegel beschermt het document en staat alleen toe dat formuliervelden worden bewerkt. Het wachtwoord "wachtwoord" wordt gebruikt om de beveiliging af te dwingen.

## Stap 5: Sla het document op

Sla het beveiligde document op  
Laten we ten slotte ons document opslaan in de opgegeven map.

```csharp
// Sla het beveiligde document op
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Hierdoor wordt het document opgeslagen met de toegepaste beveiliging.

## Conclusie

En daar heb je het! U hebt zojuist geleerd hoe u een Word-document kunt beveiligen, zodat alleen formuliervelden kunnen worden bewerkt met Aspose.Words voor .NET. Dit is een handige functie als u ervoor wilt zorgen dat bepaalde delen van uw document ongewijzigd blijven terwijl specifieke velden kunnen worden ingevuld.

## Veelgestelde vragen

###	 Hoe kan ik de beveiliging van een document verwijderen?  
 Om de bescherming te verwijderen, gebruikt u de`doc.Unprotect("password")` methode, waarbij "wachtwoord" het wachtwoord is dat wordt gebruikt om het document te beveiligen.

###	 Kan ik verschillende soorten beveiliging toepassen met Aspose.Words voor .NET?  
 Ja, Aspose.Words ondersteunt verschillende soorten bescherming, zoals`ReadOnly`, `NoProtection` , En`AllowOnlyRevisions`.

###	 Is het mogelijk om voor verschillende secties een ander wachtwoord te gebruiken?  
Nee, de beveiliging op documentniveau in Aspose.Words is van toepassing op het gehele document. U kunt geen verschillende wachtwoorden toewijzen aan verschillende secties.

###	 Wat gebeurt er als het onjuiste wachtwoord wordt gebruikt?  
Als er een onjuist wachtwoord wordt gebruikt, blijft het document beveiligd en worden de opgegeven wijzigingen niet toegepast.

###	 Kan ik programmatisch controleren of een document beveiligd is?  
 Ja, u kunt gebruik maken van de`doc.ProtectionType` eigenschap om de beveiligingsstatus van een document te controleren.
