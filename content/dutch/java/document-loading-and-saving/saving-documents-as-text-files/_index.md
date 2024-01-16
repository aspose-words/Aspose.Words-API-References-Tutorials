---
title: Documenten opslaan als tekstbestanden in Aspose.Words voor Java
linktitle: Documenten opslaan als tekstbestanden
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u documenten opslaat als tekstbestanden in Aspose.Words voor Java. Volg onze stapsgewijze handleiding met Java-codevoorbeelden.
type: docs
weight: 24
url: /nl/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Inleiding tot het opslaan van documenten als tekstbestanden in Aspose.Words voor Java

In deze zelfstudie onderzoeken we hoe u documenten als tekstbestanden kunt opslaan met behulp van de Aspose.Words voor Java-bibliotheek. Aspose.Words is een krachtige Java API voor het werken met Word-documenten en biedt verschillende opties voor het opslaan van documenten in verschillende formaten, inclusief platte tekst. We bespreken de stappen om dit te bereiken en geven onderweg voorbeeld-Java-code.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Words voor Java-bibliotheek geïntegreerd in uw project. Je kunt het downloaden van[hier](https://releases.aspose.com/words/java/).
- Basiskennis van Java-programmeren.

## Stap 1: Maak een document

Om een document als tekstbestand op te slaan, moeten we eerst een document maken met Aspose.Words. Hier is een eenvoudig Java-codefragment om een document met wat inhoud te maken:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

In deze code maken we een nieuw document en voegen er wat tekst aan toe, inclusief tekst in verschillende talen.

## Stap 2: Definieer opties voor tekstopslag

Vervolgens moeten we de opties voor tekstopslag definiëren die specificeren hoe het document als tekstbestand moet worden opgeslagen. We kunnen verschillende instellingen configureren, zoals het toevoegen van bidi-markeringen, het inspringen van lijsten en meer. Laten we twee voorbeelden bekijken:

### Voorbeeld 1: Bidi-markeringen toevoegen

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 In dit voorbeeld maken we een`TxtSaveOptions` bezwaar maken en instellen`AddBidiMarks`eigendom aan`true` om bidi-markeringen op te nemen in de tekstuitvoer.

### Voorbeeld 2: Tabteken gebruiken voor lijstinspringing

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Hier configureren we de opslagopties om een tabteken te gebruiken voor het inspringen van de lijst met een telling van 1.

## Stap 3: Sla het document op als tekst

Nu we de opties voor het opslaan van tekst hebben gedefinieerd, kunnen we het document opslaan als een tekstbestand. De volgende code laat zien hoe u dit doet:

```java
doc.save("output.txt", saveOptions);
```

 Vervangen`"output.txt"` met het gewenste bestandspad waar u het tekstbestand wilt opslaan.

## Volledige broncode voor het opslaan van documenten als tekstbestanden in Aspose.Words voor Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Maak een lijst met drie inspringingsniveaus.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Maak een lijst met drie inspringingsniveaus.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u documenten kunt opslaan als tekstbestanden in Aspose.Words voor Java. We hebben de stappen besproken om een document te maken, opties voor het opslaan van tekst te definiëren en het document in tekstformaat op te slaan. Aspose.Words biedt uitgebreide flexibiliteit als het gaat om het opslaan van documenten, waardoor u de uitvoer kunt afstemmen op uw specifieke vereisten.

## Veelgestelde vragen

### Hoe voeg ik bidi-markeringen toe aan de tekstuitvoer?

 Om bidi-markeringen aan de tekstuitvoer toe te voegen, stelt u de`AddBidiMarks` eigendom van`TxtSaveOptions` naar`true`. Bijvoorbeeld:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### Kan ik het inspringteken van de lijst aanpassen?

 Ja, u kunt het inspringingsteken voor de lijst aanpassen door het`ListIndentation` eigendom van`TxtSaveOptions`. Als u bijvoorbeeld een tabteken wilt gebruiken voor het inspringen van een lijst, kunt u het volgende doen:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Is Aspose.Words voor Java geschikt voor het verwerken van meertalige tekst?

Ja, Aspose.Words voor Java is geschikt voor het verwerken van meertalige tekst. Het ondersteunt verschillende talen en tekencoderingen, waardoor het een veelzijdige keuze is voor het werken met documenten in verschillende talen.

### Hoe krijg ik toegang tot meer documentatie en bronnen voor Aspose.Words voor Java?

 Uitgebreide documentatie en bronnen voor Aspose.Words voor Java vindt u op de documentatiewebsite van Aspose:[Aspose.Words voor Java-documentatie](https://reference.aspose.com/words/java/).

### Waar kan ik Aspose.Words voor Java downloaden?

 U kunt de Aspose.Words voor Java-bibliotheek downloaden van de Aspose-website:[Download Aspose.Words voor Java](https://releases.aspose.com/words/java/).