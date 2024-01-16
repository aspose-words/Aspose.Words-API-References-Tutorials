---
title: Documenten opslaan als OOXML-indeling in Aspose.Words voor Java
linktitle: Documenten opslaan als OOXML-indeling
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u documenten in OOXML-indeling kunt opslaan met Aspose.Words voor Java. Beveilig, optimaliseer en pas uw bestanden moeiteloos aan.
type: docs
weight: 20
url: /nl/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Inleiding tot het opslaan van documenten als OOXML-indeling in Aspose.Words voor Java

In deze handleiding onderzoeken we hoe u documenten in OOXML-indeling kunt opslaan met Aspose.Words voor Java. OOXML (Office Open XML) is een bestandsformaat dat wordt gebruikt door Microsoft Word en andere kantoortoepassingen. We bespreken verschillende opties en instellingen voor het opslaan van documenten in OOXML-indeling.

## Vereisten

Voordat we beginnen, moet u ervoor zorgen dat de Aspose.Words voor Java-bibliotheek in uw project is ingesteld.

## Een document opslaan met wachtwoordcodering

kunt uw document coderen met een wachtwoord terwijl u het opslaat in OOXML-indeling. Hier ziet u hoe u het kunt doen:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Laad het document
Document doc = new Document("Document.docx");

// Maak OoxmlSaveOptions en stel het wachtwoord in
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// Sla het document versleuteld op
doc.save("EncryptedDoc.docx", saveOptions);
```

## OOXML-compliance instellen

U kunt het OOXML-nalevingsniveau opgeven wanneer u het document opslaat. U kunt dit bijvoorbeeld instellen op ISO 29500:2008 (Strikt). Hier is hoe:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// Laad het document
Document doc = new Document("Document.docx");

// Optimaliseren voor Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// Maak OoxmlSaveOptions en stel het nalevingsniveau in
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// Sla het document op met de compliance-instelling
doc.save("ComplianceDoc.docx", saveOptions);
```

## Laatste opgeslagen tijd-eigenschap bijwerken

U kunt ervoor kiezen om de eigenschap "Laatst opgeslagen tijd" van het document bij te werken wanneer u het opslaat. Hier is hoe:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Laad het document
Document doc = new Document("Document.docx");

// Maak OoxmlSaveOptions en schakel het bijwerken van de eigenschap Laatst opgeslagen tijd in
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// Sla het document op met de bijgewerkte eigenschap
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## Legacy-controlekarakters behouden

Als uw document oudere stuurtekens bevat, kunt u ervoor kiezen deze tijdens het opslaan te behouden. Hier is hoe:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// Laad een document met oudere stuurtekens
Document doc = new Document("LegacyControlChars.doc");

//Maak OoxmlSaveOptions met het FLAT_OPC-formaat en schakel het behouden van oudere stuurtekens in
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// Sla het document op met oudere stuurtekens
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## Compressieniveau instellen

U kunt het compressieniveau aanpassen wanneer u het document opslaat. U kunt dit bijvoorbeeld instellen op SUPER_FAST voor minimale compressie. Hier is hoe:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// Laad het document
Document doc = new Document("Document.docx");

// Maak OoxmlSaveOptions en stel het compressieniveau in
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// Sla het document op met het opgegeven compressieniveau
doc.save("FastCompressionDoc.docx", saveOptions);
```

Dit zijn enkele van de belangrijkste opties en instellingen die u kunt gebruiken bij het opslaan van documenten in OOXML-indeling met Aspose.Words voor Java. Ontdek gerust meer opties en pas uw documentopslagproces indien nodig aan.

## Volledige broncode voor het opslaan van documenten als OOXML-indeling in Aspose.Words voor Java

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## Conclusie

In deze uitgebreide handleiding hebben we onderzocht hoe u documenten in OOXML-indeling kunt opslaan met Aspose.Words voor Java. Of u nu uw documenten met wachtwoorden wilt coderen, naleving van specifieke OOXML-standaarden wilt garanderen, documenteigenschappen wilt bijwerken, verouderde stuurtekens wilt behouden of compressieniveaus wilt aanpassen, Aspose.Words biedt een veelzijdige set tools om aan uw vereisten te voldoen.

## Veelgestelde vragen

### Hoe verwijder ik de wachtwoordbeveiliging van een met een wachtwoord beveiligd document?

Om de wachtwoordbeveiliging van een met een wachtwoord beveiligd document te verwijderen, kunt u het document met het juiste wachtwoord openen en het vervolgens opslaan zonder een wachtwoord op te geven in de opslagopties. Hierdoor wordt het document opgeslagen zonder wachtwoordbeveiliging.

### Kan ik aangepaste eigenschappen instellen bij het opslaan van een document in OOXML-indeling?

 Ja, u kunt aangepaste eigenschappen voor een document instellen voordat u het in OOXML-indeling opslaat. Gebruik de`BuiltInDocumentProperties` En`CustomDocumentProperties` klassen om verschillende eigenschappen in te stellen, zoals auteur, titel, trefwoorden en aangepaste eigenschappen.

### Wat is het standaardcompressieniveau bij het opslaan van een document in OOXML-indeling?

 Het standaardcompressieniveau bij het opslaan van een document in OOXML-indeling met Aspose.Words voor Java is`NORMAL` . U kunt het compressieniveau wijzigen in`SUPER_FAST` of`MAXIMUM` indien nodig.