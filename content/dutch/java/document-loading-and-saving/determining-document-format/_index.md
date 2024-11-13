---
title: Bepalen van documentformaat in Aspose.Words voor Java
linktitle: Bepalen van het documentformaat
second_title: Aspose.Words Java Documentverwerkings-API
description: Leer hoe u documentformaten in Java kunt detecteren met Aspose.Words. Identificeer DOC, DOCX en meer. Organiseer bestanden efficiënt.
type: docs
weight: 25
url: /nl/java/document-loading-and-saving/determining-document-format/
---

## Inleiding tot het bepalen van het documentformaat in Aspose.Words voor Java

Bij het werken met documentverwerking in Java is het cruciaal om het formaat van de bestanden te bepalen waarmee u werkt. Aspose.Words voor Java biedt krachtige functies voor het identificeren van documentformaten en we leiden u door het proces.

## Vereisten

Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- [Aspose.Words voor Java](https://releases.aspose.com/words/java/)
- Java Development Kit (JDK) geïnstalleerd op uw systeem
- Basiskennis van Java-programmering

## Stap 1: Directory-instelling

Eerst moeten we de benodigde mappen instellen om onze bestanden effectief te organiseren. We maken mappen voor verschillende documenttypen.

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

// Maak de mappen aan als ze nog niet bestaan.
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

We hebben mappen gemaakt voor ondersteunde, onbekende, gecodeerde en pre-97 documenttypen.

## Stap 2: Documentformaat detecteren

Laten we nu het formaat van de documenten in onze directory's detecteren. We gebruiken Aspose.Words voor Java om dit te bereiken.

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    // Geef het documenttype weer
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        // Voeg indien nodig zaken toe voor andere documentformaten
    }

    // Versleutelde documenten verwerken
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        // Andere documenttypen verwerken
        switch (info.getLoadFormat()) {
            case LoadFormat.DOC_PRE_WORD_60:
                FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                break;
            case LoadFormat.UNKNOWN:
                FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                break;
            default:
                FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                break;
        }
    }
}
```

In dit codefragment doorlopen we de bestanden, detecteren we hun indelingen en ordenen we ze in de betreffende mappen.

## Volledige broncode voor het bepalen van het documentformaat in Aspose.Words voor Java

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        // Maak de mappen aan als ze nog niet bestaan.
        if (supportedDir.exists() == false)
            supportedDir.mkdir();
        if (unknownDir.exists() == false)
            unknownDir.mkdir();
        if (encryptedDir.exists() == false)
            encryptedDir.mkdir();
        if (pre97Dir.exists() == false)
            pre97Dir.mkdir();
        Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
                .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
                .map(File::getPath)
                .collect(Collectors.toSet());
        for (String fileName : listFiles) {
            String nameOnly = Paths.get(fileName).getFileName().toString();
            System.out.println(nameOnly);
            FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);
            // Geef het documenttype weer
            switch (info.getLoadFormat()) {
                case LoadFormat.DOC:
                    System.out.println("\tMicrosoft Word 97-2003 document.");
                    break;
                case LoadFormat.DOT:
                    System.out.println("\tMicrosoft Word 97-2003 template.");
                    break;
                case LoadFormat.DOCX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Document.");
                    break;
                case LoadFormat.DOCM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
                    break;
                case LoadFormat.DOTX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Template.");
                    break;
                case LoadFormat.DOTM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
                    break;
                case LoadFormat.FLAT_OPC:
                    System.out.println("\tFlat OPC document.");
                    break;
                case LoadFormat.RTF:
                    System.out.println("\tRTF format.");
                    break;
                case LoadFormat.WORD_ML:
                    System.out.println("\tMicrosoft Word 2003 WordprocessingML format.");
                    break;
                case LoadFormat.HTML:
                    System.out.println("\tHTML format.");
                    break;
                case LoadFormat.MHTML:
                    System.out.println("\tMHTML (Web archive) format.");
                    break;
                case LoadFormat.ODT:
                    System.out.println("\tOpenDocument Text.");
                    break;
                case LoadFormat.OTT:
                    System.out.println("\tOpenDocument Text Template.");
                    break;
                case LoadFormat.DOC_PRE_WORD_60:
                    System.out.println("\tMS Word 6 or Word 95 format.");
                    break;
                case LoadFormat.UNKNOWN:
                    System.out.println("\tUnknown format.");
                    break;
            }
            if (info.isEncrypted()) {
                System.out.println("\tAn encrypted document.");
                FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
            } else {
                switch (info.getLoadFormat()) {
                    case LoadFormat.DOC_PRE_WORD_60:
                        FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                        break;
                    case LoadFormat.UNKNOWN:
                        FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                        break;
                    default:
                        FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                        break;
                }
            }
        }

```

## Conclusie

Het bepalen van documentformaten in Aspose.Words voor Java is essentieel voor efficiënte documentverwerking. Met de stappen die in deze handleiding worden beschreven, kunt u documenttypen identificeren en deze dienovereenkomstig verwerken in uw Java-applicaties.

## Veelgestelde vragen

### Hoe installeer ik Aspose.Words voor Java?

 U kunt Aspose.Words voor Java downloaden van de[hier](https://releases.aspose.com/words/java/)en volg de meegeleverde installatie-instructies.

### Welke documentformaten worden ondersteund?

Aspose.Words voor Java ondersteunt verschillende documentformaten, waaronder DOC, DOCX, RTF, HTML en meer. U kunt de documentatie raadplegen voor een complete lijst.

### Hoe kan ik versleutelde documenten detecteren met Aspose.Words voor Java?

 U kunt de`FileFormatUtil.detectFileFormat()` methode om versleutelde documenten te detecteren, zoals in deze handleiding wordt gedemonstreerd.

### Zijn er beperkingen bij het werken met oudere documentformaten?

Oudere documentformaten, zoals MS Word 6 of Word 95, kunnen beperkingen hebben in termen van functies en compatibiliteit met moderne applicaties. Overweeg deze documenten indien nodig te upgraden of te converteren.

### Kan ik de detectie van documentindelingen in mijn Java-applicatie automatiseren?

Ja, u kunt de detectie van documentformaten automatiseren door de meegeleverde code te integreren in uw Java-applicatie. Hiermee kunt u documenten verwerken op basis van hun gedetecteerde formaten.