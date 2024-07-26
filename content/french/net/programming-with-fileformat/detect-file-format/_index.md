---
title: Détecter le format de fichier de document
linktitle: Détecter le format de fichier de document
second_title: API de traitement de documents Aspose.Words
description: Apprenez à détecter les formats de fichiers de documents à l'aide d'Aspose.Words for .NET avec ce guide complet étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-fileformat/detect-file-format/
---
## Introduction

Dans le monde numérique d’aujourd’hui, la gestion efficace des différents formats de documents est cruciale. Que vous manipuliez Word, PDF, HTML ou d'autres formats, être capable de détecter et de traiter correctement ces fichiers peut vous faire gagner beaucoup de temps et d'efforts. Dans ce didacticiel, nous verrons comment détecter les formats de fichiers de documents à l'aide d'Aspose.Words pour .NET. Ce guide vous guidera à travers tout ce que vous devez savoir, des prérequis à un guide détaillé étape par étape.

## Conditions préalables

Avant de plonger dans le code, assurons-nous que vous disposez de tout ce dont vous avez besoin :

-  Aspose.Words pour .NET : vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/net/) . Assurez-vous d'avoir une licence valide. Sinon, vous pouvez obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/).
- Visual Studio : toute version récente fonctionnera correctement.
- .NET Framework : assurez-vous que la version correcte est installée.

## Importer des espaces de noms

Pour commencer, vous devrez importer les espaces de noms nécessaires dans votre projet :

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

Décomposons l'exemple en plusieurs étapes pour le rendre plus facile à suivre.

## Étape 1 : Configurer les répertoires

Tout d’abord, nous devons créer des répertoires dans lesquels les fichiers seront triés en fonction de leur format.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Créez les répertoires s'ils n'existent pas déjà.
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## Étape 2 : Obtenez la liste des fichiers

Ensuite, nous obtiendrons une liste des fichiers du répertoire, à l'exclusion de tout document corrompu.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Étape 3 : Détecter les formats de fichiers

Maintenant, nous parcourons chaque fichier et détectons son format à l’aide d’Aspose.Words.

```csharp
foreach (string fileName in fileList)
{
    string nameOnly = Path.GetFileName(fileName);

    Console.Write(nameOnly);

    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

    // Afficher le type de document
    switch (info.LoadFormat)
    {
        case LoadFormat.Doc:
            Console.WriteLine("\tMicrosoft Word 97-2003 document.");
            break;
        case LoadFormat.Dot:
            Console.WriteLine("\tMicrosoft Word 97-2003 template.");
            break;
        case LoadFormat.Docx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
            break;
        case LoadFormat.Docm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
            break;
        case LoadFormat.Dotx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
            break;
        case LoadFormat.Dotm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
            break;
        case LoadFormat.FlatOpc:
            Console.WriteLine("\tFlat OPC document.");
            break;
        case LoadFormat.Rtf:
            Console.WriteLine("\tRTF format.");
            break;
        case LoadFormat.WordML:
            Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
            break;
        case LoadFormat.Html:
            Console.WriteLine("\tHTML format.");
            break;
        case LoadFormat.Mhtml:
            Console.WriteLine("\tMHTML (Web archive) format.");
            break;
        case LoadFormat.Odt:
            Console.WriteLine("\tOpenDocument Text.");
            break;
        case LoadFormat.Ott:
            Console.WriteLine("\tOpenDocument Text Template.");
            break;
        case LoadFormat.DocPreWord60:
            Console.WriteLine("\tMS Word 6 or Word 95 format.");
            break;
        case LoadFormat.Unknown:
            Console.WriteLine("\tUnknown format.");
            break;
    }

    if (info.IsEncrypted)
    {
        Console.WriteLine("\tAn encrypted document.");
        File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
    }
    else
    {
        switch (info.LoadFormat)
        {
            case LoadFormat.DocPreWord60:
                File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
                break;
            case LoadFormat.Unknown:
                File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
                break;
            default:
                File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
                break;
        }
    }
}
```

## Conclusion

La détection des formats de fichiers de documents à l'aide d'Aspose.Words pour .NET est un processus simple. En configurant vos répertoires, en obtenant votre liste de fichiers et en utilisant Aspose.Words pour détecter les formats de fichiers, vous pouvez organiser et gérer efficacement vos documents. Cette approche permet non seulement de gagner du temps, mais garantit également que vous gérez correctement les différents formats de documents.

## FAQ

### Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une bibliothèque puissante permettant de travailler avec des documents Word par programmation. Il permet aux développeurs de créer, modifier et convertir des documents dans différents formats.

### Aspose.Words peut-il détecter les documents cryptés ?
Oui, Aspose.Words peut détecter si un document est crypté et vous pouvez gérer ces documents en conséquence.

### Quels formats Aspose.Words peut-il détecter ?
Aspose.Words peut détecter un large éventail de formats, notamment DOC, DOCX, RTF, HTML, MHTML, ODT et bien d'autres.

### Comment puis-je obtenir une licence temporaire pour Aspose.Words ?
 Vous pouvez obtenir une licence temporaire auprès du[Asposez l'achat](https://purchase.aspose.com/temporary-license/) page.

### Où puis-je trouver la documentation pour Aspose.Words ?
 La documentation pour Aspose.Words peut être trouvée[ici](https://reference.aspose.com/words/net/).
