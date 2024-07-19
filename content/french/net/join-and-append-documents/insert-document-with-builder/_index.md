---
title: Insérer un document avec le générateur
linktitle: Insérer un document avec le générateur
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment fusionner deux documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape pour insérer un document avec DocumentBuilder et conserver le formatage.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/insert-document-with-builder/
---
## Introduction

Vous disposez donc de deux documents Word et vous souhaitez les fusionner en un seul. Vous vous demandez peut-être : « Existe-t-il un moyen simple de procéder ainsi par programmation ? » Absolument! Aujourd'hui, je vais vous guider tout au long du processus d'insertion d'un document dans un autre à l'aide de la bibliothèque Aspose.Words for .NET. Cette méthode est très pratique, surtout lorsque vous traitez des documents volumineux ou que vous devez automatiser le processus. Allons-y !

## Conditions préalables

Avant de commencer, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1.  Aspose.Words for .NET : si vous ne l'avez pas déjà fait, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : assurez-vous que Visual Studio ou tout autre IDE approprié est installé.
3. Connaissance de base de C# : Une petite familiarité avec C# sera très utile.

## Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires pour accéder aux fonctionnalités de la bibliothèque Aspose.Words. Voici comment procéder :

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Maintenant que nous avons mis en place nos conditions préalables, décomposons le processus étape par étape.

## Étape 1 : configuration de votre répertoire de documents

Avant de commencer le codage, vous devez définir le chemin d'accès à votre répertoire de documents. C'est ici que sont stockés vos documents source et destination.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où se trouvent vos documents. Cela aidera le programme à trouver facilement vos fichiers.

## Étape 2 : chargement des documents source et de destination

Ensuite, nous devons charger les documents avec lesquels nous voulons travailler. Dans cet exemple, nous avons un document source et un document destination.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

 Ici, nous utilisons le`Document` classe de la bibliothèque Aspose.Words pour charger nos documents. Assurez-vous que les noms de fichiers correspondent à ceux de votre répertoire.

## Étape 3 : Création d'un objet DocumentBuilder

 Le`DocumentBuilder` class est un outil puissant de la bibliothèque Aspose.Words. Cela nous permet de naviguer et de manipuler le document.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

 Dans cette étape, nous avons créé un`DocumentBuilder` objet pour notre document de destination. Cela nous aidera à insérer du contenu dans le document.

## Étape 4 : Passer à la fin du document

Nous devons déplacer le curseur du générateur à la fin du document de destination avant d'insérer le document source.

```csharp
builder.MoveToDocumentEnd();
```

Cela garantit que le document source est inséré à la fin du document de destination.

## Étape 5 : Insérer un saut de page

Pour que les choses restent claires, ajoutons un saut de page avant d'insérer le document source. Cela démarrera le contenu du document source sur une nouvelle page.

```csharp
builder.InsertBreak(BreakType.PageBreak);
```

Un saut de page garantit que le contenu du document source commence sur une nouvelle page, ce qui donne au document fusionné un aspect professionnel.

## Étape 6 : Insertion du document source

Vient maintenant la partie passionnante : insérer le document source dans le document de destination.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

 En utilisant le`InsertDocument` méthode, nous pouvons insérer l’intégralité du document source dans le document de destination. Le`ImportFormatMode.KeepSourceFormatting` garantit que le formatage du document source est préservé.

## Étape 7 : enregistrement du document fusionné

Enfin, sauvons le document fusionné. Cela combinera les documents source et de destination en un seul fichier.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

En enregistrant le document, nous terminons le processus de fusion des deux documents. Votre nouveau document est maintenant prêt et enregistré dans le répertoire spécifié.

## Conclusion

Et voila! Vous avez réussi à insérer un document dans un autre à l'aide d'Aspose.Words pour .NET. Cette méthode est non seulement efficace mais préserve également le formatage des deux documents, garantissant une fusion transparente. Que vous travailliez sur un projet ponctuel ou que vous ayez besoin d'automatiser le traitement de documents, Aspose.Words for .NET est là pour vous.

## FAQ

### Qu’est-ce qu’Aspose.Words pour .NET ?  
Aspose.Words for .NET est une bibliothèque puissante qui permet aux développeurs de créer, modifier, convertir et manipuler des documents Word par programme.

### Puis-je conserver la mise en forme du document source ?  
 Oui, en utilisant`ImportFormatMode.KeepSourceFormatting`, la mise en forme du document source est conservée lors de son insertion dans le document de destination.

### Ai-je besoin d’une licence pour utiliser Aspose.Words pour .NET ?  
 Oui, Aspose.Words for .NET nécessite une licence pour bénéficier de toutes les fonctionnalités. Vous pouvez obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour évaluation.

### Puis-je automatiser ce processus ?  
Absolument! La méthode décrite peut être intégrée à des applications plus vastes pour automatiser les tâches de traitement de documents.

### Où puis-je trouver plus de ressources et d’assistance ?  
Pour plus d'informations, vous pouvez consulter le[Documentation](https://reference.aspose.com/words/net/) , ou visitez le[forum d'entraide](https://forum.aspose.com/c/words/8) à l'aide.