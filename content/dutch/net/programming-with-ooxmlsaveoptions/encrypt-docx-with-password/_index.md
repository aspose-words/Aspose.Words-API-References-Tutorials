---
title: Versleutel Docx met wachtwoord
linktitle: Versleutel Docx met wachtwoord
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een DOCX-bestand met een wachtwoord codeert met Aspose.Words voor .NET. Volledige tutorial voor documentbeveiliging.
type: docs
weight: 10
url: /nl/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
In deze zelfstudie verkennen we de meegeleverde C#-broncode om een DOCX-bestand met een wachtwoord te coderen met Aspose.Words voor .NET. Met deze functie kunt u uw document beschermen door het alleen toegankelijk te maken met een opgegeven wachtwoord.

## Stap 1: De omgeving instellen

Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld met Aspose.Words voor .NET. Zorg ervoor dat u de benodigde referenties hebt toegevoegd en de juiste naamruimten hebt geïmporteerd.

## Stap 2: Het document laden

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In deze stap laden we het document met behulp van de`Document` methode en geef het pad door naar het DOCX-bestand dat moet worden geladen.

## Stap 3: OOXML-back-upopties configureren

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

 In deze stap configureren we de OOXML-opslagopties door een nieuw`OoxmlSaveOptions` voorwerp. We specificeren het gewenste wachtwoord om het document te coderen door de`Password` eigendom toe aan uw aangepaste wachtwoord.

## Stap 4: Het document coderen met een wachtwoord

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 In deze laatste stap slaan we het document op met behulp van de`Save` methode en geef het pad door naar het uitvoerbestand met de`.docx` extensie, samen met de opgegeven opslagopties.

Nu kunt u de broncode uitvoeren om uw DOCX-document met een wachtwoord te coderen. Het resulterende bestand wordt opgeslagen in de opgegeven map met de naam "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx". Zorg ervoor dat u uw wachtwoord veilig bewaart, aangezien dit nodig is om het gecodeerde document te openen.

### Voorbeeldbroncode voor het versleutelen van Docx met wachtwoord met Aspose.Words voor .NET 

```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Conclusie

In deze zelfstudie hebben we de functionaliteit onderzocht van het coderen van een DOCX-bestand met een wachtwoord met Aspose.Words voor .NET. We hebben geleerd hoe we onze documenten kunnen beschermen door ze alleen toegankelijk te maken met een opgegeven wachtwoord.

Documentencryptie is een essentiële beveiligingsmaatregel om gevoelige informatie te beschermen. Dankzij Aspose.Words voor .NET kunnen we deze functionaliteit eenvoudig aan onze applicaties toevoegen.

Door de gegeven stappen te volgen, kunt u wachtwoordversleuteling integreren in uw Aspose.Words voor .NET-projecten en de vertrouwelijkheid van uw documenten garanderen.

Experimenteer gerust met andere functies van Aspose.Words voor .NET om uw toepassingen te verrijken met geavanceerde functies voor documentmanipulatie.
