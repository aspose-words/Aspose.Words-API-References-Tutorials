---
title: Opschoningsopties gebruiken in Aspose.Words voor Java
linktitle: Opschoningsopties gebruiken
second_title: Aspose.Words Java-documentverwerkings-API
description: Verbeter de duidelijkheid van documenten met Aspose.Words voor Java Cleanup-opties. Leer hoe u lege alinea's, ongebruikte gebieden en meer verwijdert.
type: docs
weight: 10
url: /nl/java/document-manipulation/using-cleanup-options/
---

## Inleiding tot het gebruik van opruimopties in Aspose.Words voor Java

In deze zelfstudie onderzoeken we hoe u opruimopties in Aspose.Words voor Java kunt gebruiken om documenten te manipuleren en op te ruimen tijdens het samenvoegproces. Met opschoningsopties kunt u verschillende aspecten van het opschonen van documenten beheren, zoals het verwijderen van lege alinea's, ongebruikte gebieden en meer.

## Vereisten

 Voordat we beginnen, moet u ervoor zorgen dat de Aspose.Words voor Java-bibliotheek in uw project is geïntegreerd. Je kunt het downloaden van[hier](https://releases.aspose.com/words/java/).

## Stap 1: Lege alinea's verwijderen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg samenvoegvelden in
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Opruimopties instellen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Schakel opschoningsparagrafen met leestekens in
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Voer een samenvoegbewerking uit
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// Bewaar het document
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

In dit voorbeeld maken we een nieuw document, voegen samenvoegvelden in en stellen de opruimopties zo in dat lege alinea's worden verwijderd. Bovendien maken we het verwijderen van alinea's met leestekens mogelijk. Na het uitvoeren van de samenvoegbewerking wordt het document opgeslagen met de opgegeven opschoning toegepast.

## Stap 2: Niet-samengevoegde regio's verwijderen

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Stel opschoonopties in om ongebruikte regio's te verwijderen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Voer samenvoeging met regio's uit
doc.getMailMerge().executeWithRegions(data);

// Bewaar het document
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

In dit voorbeeld openen we een bestaand document met samenvoeggebieden, stellen we de opschoonopties in om ongebruikte regio's te verwijderen en voeren we vervolgens de samenvoegbewerking uit met lege gegevens. Dit proces verwijdert automatisch de ongebruikte gebieden uit het document.

## Stap 3: Lege velden verwijderen

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Stel opruimopties in om lege velden te verwijderen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Voer een samenvoegbewerking uit
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Bewaar het document
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

In dit voorbeeld openen we een document met samenvoegvelden, stellen we de opschoonopties zo in dat lege velden worden verwijderd en voeren we de samenvoeging met gegevens uit. Na het samenvoegen worden eventuele lege velden uit het document verwijderd.

## Stap 4: Ongebruikte velden verwijderen

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Stel opruimopties in om ongebruikte velden te verwijderen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Voer een samenvoegbewerking uit
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Bewaar het document
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

In dit voorbeeld openen we een document met samenvoegvelden, stellen we de opschoonopties in om ongebruikte velden te verwijderen en voeren we de samenvoeging met gegevens uit. Na het samenvoegen worden alle ongebruikte velden uit het document verwijderd.

## Stap 5: Bevattende velden verwijderen

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Stel opschoonopties in om de bevattende velden te verwijderen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Voer een samenvoegbewerking uit
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Bewaar het document
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

In dit voorbeeld openen we een document met samenvoegvelden, stellen we de opschoonopties in om de bevattende velden te verwijderen en voeren we de samenvoeging met gegevens uit. Na het samenvoegen worden de velden zelf uit het document verwijderd.

## Stap 6: Lege tabelrijen verwijderen

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Stel opschoonopties in om lege tabelrijen te verwijderen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Voer een samenvoegbewerking uit
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Bewaar het document
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

In dit voorbeeld openen we een document met een tabel en samenvoegvelden, stellen we de opschoonopties in om lege tabelrijen te verwijderen en voeren we de samenvoeging met gegevens uit. Na het samenvoegen worden eventuele lege tabelrijen uit het document verwijderd.

## Conclusie

In deze zelfstudie hebt u geleerd hoe u opruimopties in Aspose.Words voor Java kunt gebruiken om documenten te manipuleren en op te ruimen tijdens het samenvoegproces. Deze opties bieden een fijnmazige controle over het opschonen van documenten, waardoor u eenvoudig gepolijste en aangepaste documenten kunt maken.

## Veelgestelde vragen

### Wat zijn opruimopties in Aspose.Words voor Java?

Opruimopties in Aspose.Words voor Java zijn instellingen waarmee u verschillende aspecten van het opschonen van documenten tijdens het samenvoegproces kunt beheren. Ze stellen u in staat onnodige elementen zoals lege alinea's, ongebruikte gebieden en meer te verwijderen, zodat uw uiteindelijke document goed gestructureerd en gepolijst is.

### Hoe kan ik lege alinea's uit mijn document verwijderen?

 Om lege alinea's uit uw document te verwijderen met Aspose.Words voor Java, kunt u de`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` optie naar waar. Hierdoor worden automatisch paragrafen verwijderd die geen inhoud hebben, wat resulteert in een netter document.

###  Wat is het doel van de`REMOVE_UNUSED_REGIONS` cleanup option?

 De`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` De optie wordt gebruikt om regio's in een document te verwijderen die geen overeenkomstige gegevens bevatten tijdens het samenvoegproces. Het helpt uw document netjes te houden door ongebruikte tijdelijke aanduidingen te verwijderen.

### Kan ik lege tabelrijen uit een document verwijderen met Aspose.Words voor Java?

 Ja, u kunt lege tabelrijen uit een document verwijderen door de`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`opschoningsoptie op waar. Hierdoor worden automatisch alle tabelrijen verwijderd die geen gegevens bevatten, waardoor u verzekerd bent van een goed gestructureerde tabel in uw document.

###  Wat gebeurt er als ik de`REMOVE_CONTAINING_FIELDS` option?

 Het instellen van de`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` Met deze optie wordt het volledige samenvoegveld, inclusief de alinea die het bevat, uit het document verwijderd tijdens het samenvoegproces. Dit is handig als u samenvoegvelden en de bijbehorende tekst wilt verwijderen.

### Hoe kan ik ongebruikte samenvoegvelden uit mijn document verwijderen?

 Om ongebruikte samenvoegvelden uit een document te verwijderen, kunt u de`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` optie naar waar. Hierdoor worden samenvoegvelden die tijdens het samenvoegen niet zijn ingevuld automatisch verwijderd, wat resulteert in een schoner document.

###  Wat is het verschil tussen`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 De`REMOVE_EMPTY_FIELDS` optie verwijdert samenvoegvelden die geen gegevens bevatten of leeg zijn tijdens het samenvoegproces. Aan de andere kant, de`REMOVE_UNUSED_FIELDS`optie verwijdert samenvoegvelden die tijdens het samenvoegen niet met gegevens zijn gevuld. De keuze hiertussen hangt af van of u velden zonder inhoud wilt verwijderen of velden die ongebruikt zijn in de specifieke samenvoegbewerking.

### Hoe kan ik het verwijderen van alinea's met leestekens inschakelen?

 Om het verwijderen van alinea's met leestekens mogelijk te maken, kunt u de`cleanupParagraphsWithPunctuationMarks` optie op true en specificeer de leestekens die in aanmerking komen voor opschoning. Hierdoor kunt u een verfijnder document maken door onnodige alinea's met alleen interpunctie te verwijderen.

### Kan ik de opschoonopties in Aspose.Words voor Java aanpassen?

Ja, u kunt de opruimopties aanpassen aan uw specifieke behoeften. U kunt kiezen welke opschoonopties u wilt toepassen en deze configureren volgens uw vereisten voor het opschonen van documenten, zodat uw uiteindelijke document aan de door u gewenste normen voldoet.