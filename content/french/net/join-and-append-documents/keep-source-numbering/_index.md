---
title: Conserver la numérotation des sources
linktitle: Conserver la numérotation des sources
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment importer des documents tout en préservant le formatage à l'aide d'Aspose.Words for .NET. Guide étape par étape avec des exemples de code.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/keep-source-numbering/
---
## Introduction

 Lorsque vous travaillez avec Aspose.Words for .NET, l'importation de documents d'une source à une autre tout en préservant le formatage peut être gérée efficacement à l'aide de l'outil`NodeImporter` classe. Ce tutoriel vous guidera tout au long du processus étape par étape.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Visual Studio installé sur votre ordinateur.
-  Aspose.Words pour .NET installé. Sinon, téléchargez-le depuis[ici](https://releases.aspose.com/words/net/).
- Connaissance de base de la programmation C# et .NET.

## Importer des espaces de noms

Tout d’abord, incluez les espaces de noms nécessaires dans votre projet :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## Étape 1 : Configurez votre projet

Commencez par créer un nouveau projet C# dans Visual Studio et installez Aspose.Words via NuGet Package Manager.

## Étape 2 : initialiser les documents
Créer des instances de la source (`srcDoc`) et la destination (`dstDoc`) documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : configurer les options d'importation
Configurez les options d'importation pour conserver le formatage source, y compris les paragraphes numérotés.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Étape 4 : Importer des paragraphes
Parcourez les paragraphes du document source et importez-les dans le document de destination.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Étape 5 : Enregistrez le document
Enregistrez le document fusionné à l'emplacement souhaité.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Conclusion

 En conclusion, utiliser Aspose.Words for .NET pour importer des documents tout en préservant le formatage est simple avec le`NodeImporter` classe. Cette méthode garantit que vos documents conservent parfaitement leur apparence et leur structure d’origine.

## FAQ

### Puis-je importer des documents avec différents styles de formatage ?
 Oui, le`NodeImporter` La classe prend en charge l'importation de documents avec des styles de formatage variés.

### Que se passe-t-il si mes documents contiennent des tableaux et des images complexes ?
Aspose.Words for .NET gère des structures complexes telles que des tableaux et des images lors des opérations d'importation.

### Aspose.Words est-il compatible avec toutes les versions de .NET ?
Aspose.Words prend en charge les versions .NET Framework et .NET Core pour une intégration transparente.

### Comment puis-je gérer les erreurs lors de l’importation de documents ?
Utilisez des blocs try-catch pour gérer les exceptions pouvant survenir pendant le processus d'importation.

### Où puis-je trouver une documentation plus détaillée sur Aspose.Words pour .NET ?
 Visitez le[documentation](https://reference.aspose.com/words/net/) pour des guides complets et des références API.
