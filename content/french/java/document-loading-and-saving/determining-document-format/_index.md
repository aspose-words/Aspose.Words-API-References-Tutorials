---
title: Détermination du format du document dans Aspose.Words pour Java
linktitle: Détermination du format du document
second_title: API de traitement de documents Java Aspose.Words
description: Apprenez à détecter les formats de documents en Java avec Aspose.Words. Identifiez DOC, DOCX et plus encore. Organisez les fichiers efficacement.
type: docs
weight: 25
url: /fr/java/document-loading-and-saving/determining-document-format/
---

## Introduction à la détermination du format du document dans Aspose.Words pour Java

Lorsque vous travaillez avec le traitement de documents en Java, il est crucial de déterminer le format des fichiers que vous traitez. Aspose.Words for Java fournit des fonctionnalités puissantes pour identifier les formats de documents, et nous vous guiderons tout au long du processus.

## Conditions préalables

Avant de commencer, assurez-vous de disposer des prérequis suivants :

- [Aspose.Words pour Java](https://releases.aspose.com/words/java/)
- Kit de développement Java (JDK) installé sur votre système
- Connaissance de base de la programmation Java

## Étape 1 : configuration du répertoire

Tout d’abord, nous devons configurer les répertoires nécessaires pour organiser efficacement nos fichiers. Nous allons créer des répertoires pour différents types de documents.

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

// Créez les répertoires s'ils n'existent pas déjà.
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

Nous avons créé des répertoires pour les types de documents pris en charge, inconnus, cryptés et antérieurs à 97.

## Étape 2 : Détection du format du document

Détectons maintenant le format des documents dans nos répertoires. Nous utiliserons Aspose.Words pour Java pour y parvenir.

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    // Afficher le type de document
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        // Ajoutez des cas pour d'autres formats de documents si nécessaire
    }

    // Gérer les documents cryptés
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        // Gérer d'autres types de documents
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

Dans cet extrait de code, nous parcourons les fichiers, détectons leurs formats et les organisons dans les répertoires respectifs.

## Code source complet pour déterminer le format du document dans Aspose.Words pour Java

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        // Créez les répertoires s'ils n'existent pas déjà.
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
            // Afficher le type de document
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

## Conclusion

La détermination des formats de documents dans Aspose.Words pour Java est essentielle pour un traitement efficace des documents. Grâce aux étapes décrites dans ce guide, vous pouvez identifier les types de documents et les gérer en conséquence dans vos applications Java.

## FAQ

### Comment installer Aspose.Words pour Java ?

 Vous pouvez télécharger Aspose.Words pour Java à partir du[ici](https://releases.aspose.com/words/java/) et suivez les instructions d'installation fournies.

### Quels sont les formats de documents pris en charge ?

Aspose.Words for Java prend en charge divers formats de documents, notamment DOC, DOCX, RTF, HTML, etc. Vous pouvez vous référer à la documentation pour une liste complète.

### Comment puis-je détecter des documents cryptés à l'aide d'Aspose.Words pour Java ?

 Vous pouvez utiliser le`FileFormatUtil.detectFileFormat()` méthode pour détecter les documents cryptés, comme démontré dans ce guide.

### Existe-t-il des limitations lorsque l’on travaille avec des formats de documents plus anciens ?

Les formats de documents plus anciens, tels que MS Word 6 ou Word 95, peuvent présenter des limitations en termes de fonctionnalités et de compatibilité avec les applications modernes. Pensez à mettre à niveau ou à convertir ces documents si nécessaire.

### Puis-je automatiser la détection du format de document dans mon application Java ?

Oui, vous pouvez automatiser la détection du format de document en intégrant le code fourni dans votre application Java. Cela vous permet de traiter les documents en fonction de leurs formats détectés.