---
title: OLE-objecten en ActiveX-besturingselementen gebruiken in Aspose.Words voor Java
linktitle: OLE-objecten en ActiveX-besturingselementen gebruiken
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer OLE-objecten en ActiveX-besturingselementen gebruiken in Aspose.Words voor Java. Creëer eenvoudig interactieve documenten. Begin nu!
type: docs
weight: 21
url: /nl/java/using-document-elements/using-ole-objects-and-activex/
---
In deze zelfstudie onderzoeken we hoe u kunt werken met OLE-objecten (Object Linking and Embedding) en ActiveX-besturingselementen in Aspose.Words voor Java. OLE-objecten en ActiveX-besturingselementen zijn krachtige hulpmiddelen waarmee u uw documenten kunt verbeteren door externe inhoud, zoals spreadsheets, multimediabestanden of interactieve besturingselementen, in te sluiten of te koppelen. Volg mee terwijl we ons verdiepen in de codevoorbeelden en leren hoe u deze functies effectief kunt gebruiken.

### Vereisten

Voordat we aan de slag gaan, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Aspose.Words voor Java: Zorg ervoor dat de Aspose.Words-bibliotheek in uw Java-project is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/words/java/).

2. Java-ontwikkelomgeving: er moet een werkende Java-ontwikkelomgeving op uw systeem zijn geïnstalleerd.

### Een OLE-object invoegen

Laten we beginnen met het invoegen van een OLE-object in een Word-document. We maken een eenvoudig Word-document en voegen vervolgens een OLE-object in dat een webpagina vertegenwoordigt.

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com", "htmlfile", waar, waar, null);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

In deze code maken we een nieuw document en voegen we een OLE-object in dat de Aspose-website weergeeft. U kunt de URL vervangen door de gewenste inhoud.

### Een OLE-object invoegen met OlePackage

Laten we vervolgens onderzoeken hoe u een OLE-object kunt invoegen met behulp van een OlePackage. Hierdoor kunt u externe bestanden als OLE-objecten in uw document insluiten.

```java
@Test
public void insertOleObjectWithOlePackage() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    byte[] bs = FileUtils.readFileToByteArray(new File("Your Directory Path" + "Zip file.zip"));
    try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
    {
        Shape shape = builder.insertOleObject(stream, "Package", true, null);
        OlePackage olePackage = shape.getOleFormat().getOlePackage();
        olePackage.setFileName("filename.zip");
        olePackage.setDisplayName("displayname.zip");
        doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
    }
}
```

In dit voorbeeld voegen we een OLE-object in met behulp van een OlePackage, waardoor u externe bestanden als ingesloten objecten kunt opnemen.

### Een OLE-object invoegen als een pictogram

Laten we nu kijken hoe we een OLE-object als pictogram kunnen invoegen. Dit is handig als u een pictogram wilt weergeven dat een ingesloten bestand vertegenwoordigt.

```java
@Test
public void insertOleObjectAsIcon() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObjectAsIcon("Your Directory Path" + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico", "My embedded file");
    doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
}
```

In deze code voegen we een OLE-object in als pictogram, waardoor een visueel aantrekkelijkere weergave van de ingesloten inhoud ontstaat.

### Eigenschappen van ActiveX-besturingselement lezen

Laten we nu onze focus verleggen naar ActiveX-besturingselementen. We zullen leren hoe u de eigenschappen van ActiveX-besturingselementen in een Word-document kunt lezen.

```java
@Test
public void readActiveXControlProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "ActiveX controls.docx");
    String properties = "";
    for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
    {
        if (shape.getOleFormat() == null) break;
        OleControl oleControl = shape.getOleFormat().getOleControl();
        if (oleControl.isForms2OleControl())
        {
            Forms2OleControl checkBox = (Forms2OleControl) oleControl;
            properties = properties + "\nCaption: " + checkBox.getCaption();
            properties = properties + "\nValue: " + checkBox.getValue();
            properties = properties + "\nEnabled: " + checkBox.getEnabled();
            properties = properties + "\nType: " + checkBox.getType();
            if (checkBox.getChildNodes() != null)
            {
                properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
            }
            properties += "\n";
        }
    }
    properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
    System.out.println("\n" + properties);
}
```

In deze code doorlopen we de vormen in een Word-document, identificeren we ActiveX-besturingselementen en halen we hun eigenschappen op.

### Conclusie

Gefeliciteerd! U hebt geleerd hoe u met OLE-objecten en ActiveX-besturingselementen kunt werken in Aspose.Words voor Java. Deze functies openen een wereld aan mogelijkheden voor het creëren van dynamische en interactieve documenten.

### Veelgestelde vragen

### Wat is het doel van OLE-objecten in een Word-document? 
   - Met OLE-objecten kunt u externe inhoud, zoals bestanden of webpagina's, insluiten of koppelen in een Word-document.

### Kan ik de weergave van OLE-objecten in mijn document aanpassen? 
   - Ja, u kunt het uiterlijk van OLE-objecten aanpassen, inclusief het instellen van pictogrammen en bestandsnamen.

### Wat zijn ActiveX-besturingselementen en hoe kunnen ze mijn documenten verbeteren? 
   - ActiveX-besturingselementen zijn interactieve elementen die functionaliteit aan uw Word-documenten kunnen toevoegen, zoals formulierbesturingselementen of multimediaspelers.

### Is Aspose.Words voor Java geschikt voor documentautomatisering op ondernemingsniveau? 
   - Ja, Aspose.Words voor Java is een krachtige bibliotheek voor het automatiseren van het genereren en manipuleren van documenten in Java-toepassingen.

### Waar kan ik toegang krijgen tot Aspose.Words voor Java? 
   -  U kunt Aspose.Words voor Java downloaden van[hier](https://releases.aspose.com/words/java/).

Ga vandaag nog aan de slag met Aspose.Words voor Java en ontgrendel het volledige potentieel van documentautomatisering en -aanpassing!
