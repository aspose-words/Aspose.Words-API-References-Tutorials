---
title: Insérer un objet Ole dans Word avec le package Ole
linktitle: Insérer un objet Ole dans Word avec le package Ole
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer des objets OLE dans des documents Word à l'aide d'Aspose.Words pour .NET. Suivez notre guide détaillé étape par étape pour intégrer des fichiers de manière transparente.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---
## Introduction

Si vous avez toujours voulu intégrer un fichier dans un document Word, vous êtes au bon endroit. Qu'il s'agisse d'un fichier ZIP, d'une feuille Excel ou de tout autre type de fichier, l'intégrer directement dans votre document Word peut être incroyablement utile. Pensez-y comme si vous aviez un compartiment secret dans votre document où vous pouvez cacher toutes sortes de trésors. Et aujourd'hui, nous allons expliquer comment procéder à l'aide d'Aspose.Words pour .NET. Prêt à devenir un assistant Word ? Allons-y !

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Aspose.Words for .NET : si vous ne l'avez pas déjà fait, téléchargez-le depuis[ici](https://releases.aspose.com/words/net/).
2. Un environnement de développement : Visual Studio ou tout autre environnement de développement .NET.
3. Compréhension de base de C# : vous n'avez pas besoin d'être un expert, mais connaître C# vous aidera.
4. Un répertoire de documents : un dossier dans lequel vous pouvez stocker et récupérer des documents.

## Importer des espaces de noms

Tout d’abord, mettons de l’ordre dans nos espaces de noms. Vous devez inclure les espaces de noms suivants dans votre projet :

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Décomposons cela en petites étapes, afin qu'il soit facile à suivre.

## Étape 1 : Configurez votre document

Imaginez que vous êtes un artiste avec une toile vierge. Tout d’abord, nous avons besoin de notre toile vierge, qui est notre document Word. Voici comment le configurer :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Ce code initialise un nouveau document Word et configure un DocumentBuilder, que nous utiliserons pour insérer du contenu dans notre document.

## Étape 2 : Lisez votre objet Ole

Ensuite, lisons le fichier que vous souhaitez intégrer. Considérez cela comme si vous récupériez le trésor que vous souhaitez cacher dans votre compartiment secret :

```csharp
byte[] bs = File.ReadAllBytes(dataDir + "Zip file.zip");
```

Cette ligne lit tous les octets de votre fichier ZIP et les stocke dans un tableau d'octets.

## Étape 3 : Insérez l'objet Ole

Vient maintenant la partie magique. Nous allons intégrer le fichier dans notre document Word :

```csharp
using (Stream stream = new MemoryStream(bs))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);
    OlePackage olePackage = shape.OleFormat.OlePackage;
    olePackage.FileName = "filename.zip";
    olePackage.DisplayName = "displayname.zip";
}
```

 Ici, nous créons un flux mémoire à partir du tableau d'octets et utilisons le`InsertOleObject` méthode pour l’intégrer dans le document. Nous définissons également le nom de fichier et le nom d'affichage de l'objet incorporé.

## Étape 4 : Enregistrez votre document

Enfin, sauvons notre chef-d'œuvre :

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Cela enregistre le document avec votre fichier intégré dans le répertoire spécifié.

## Conclusion

Et voilà ! Vous avez intégré avec succès un objet OLE dans un document Word à l'aide d'Aspose.Words pour .NET. C'est comme ajouter un joyau caché à l'intérieur de votre document qui peut être dévoilé à tout moment. Cette technique peut être incroyablement utile pour diverses applications, de la documentation technique aux rapports dynamiques. 

## FAQ

### Puis-je intégrer d’autres types de fichiers en utilisant cette méthode ?
Oui, vous pouvez intégrer différents types de fichiers tels que des feuilles Excel, des PDF et des images.

### Ai-je besoin d’une licence pour Aspose.Words ?
 Oui, vous avez besoin d'une licence valide. Vous pouvez obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour évaluation.

### Comment puis-je personnaliser le nom d'affichage de l'objet OLE ?
 Vous pouvez définir le`DisplayName` propriété du`OlePackage` pour le personnaliser.

### Aspose.Words est-il compatible avec .NET Core ?
Oui, Aspose.Words prend en charge à la fois .NET Framework et .NET Core.

### Puis-je modifier l’objet OLE incorporé dans le document Word ?
Non, vous ne pouvez pas modifier l'objet OLE directement dans Word. Vous devez l'ouvrir dans son application native.