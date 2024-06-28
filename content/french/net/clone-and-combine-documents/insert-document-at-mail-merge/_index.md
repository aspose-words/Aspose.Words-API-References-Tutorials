---
title: Insérer un document lors du publipostage
linktitle: Insérer un document lors du publipostage
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer des documents dans des champs de publipostage à l'aide d'Aspose.Words for .NET dans ce didacticiel complet, étape par étape.
type: docs
weight: 10
url: /fr/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## Introduction

Bienvenue dans le monde de l'automatisation des documents avec Aspose.Words pour .NET ! Vous êtes-vous déjà demandé comment insérer dynamiquement des documents dans des champs spécifiques d'un document principal lors d'une opération de publipostage ? Eh bien, vous êtes au bon endroit. Ce didacticiel vous guidera étape par étape tout au long du processus d'insertion de documents dans les champs de publipostage à l'aide d'Aspose.Words pour .NET. C'est comme reconstituer un puzzle, où chaque pièce s'emboîte parfaitement. Alors, plongeons-nous !

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1.  Aspose.Words pour .NET : vous pouvez[Télécharger la dernière version ici](https://releases.aspose.com/words/net/) . Si vous devez acheter une licence, vous pouvez le faire[ici](https://purchase.aspose.com/buy) . Alternativement, vous pouvez obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/) ou essayez-le avec un[essai gratuit](https://releases.aspose.com/).
2. Environnement de développement : Visual Studio ou tout autre IDE C#.
3. Connaissance de base de C# : La familiarité avec la programmation C# fera de ce didacticiel un jeu d'enfant.

## Importer des espaces de noms

Tout d’abord, vous devrez importer les espaces de noms nécessaires. Ce sont comme les éléments constitutifs de votre projet.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Décomposons le processus en étapes gérables. Chaque étape s’appuiera sur la précédente, vous conduisant à une solution complète.

## Étape 1 : configuration de votre annuaire

Avant de pouvoir commencer à insérer des documents, vous devez définir le chemin d'accès à votre répertoire de documents. C'est ici que sont stockés vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : chargement du document principal

Ensuite, vous chargerez le document principal. Ce document contient les champs de fusion où d'autres documents seront insérés.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## Étape 3 : Définition du rappel de fusion de champs

Pour gérer le processus de fusion, vous devrez définir une fonction de rappel. Cette fonction sera responsable de l'insertion des documents dans les champs de fusion spécifiés.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Étape 4 : Exécution du publipostage

Il est maintenant temps d'exécuter le publipostage. C'est là que la magie opère. Vous spécifierez le champ de fusion et le document qui doit être inséré dans ce champ.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Étape 5 : Sauvegarde du document

Une fois le publipostage terminé, vous enregistrerez le document modifié. Ce nouveau document aura le contenu inséré là où vous le souhaitez.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Étape 6 : Création du gestionnaire de rappel

Le gestionnaire de rappel est une classe qui effectue un traitement spécial pour le champ de fusion. Il charge le document spécifié dans la valeur du champ et l'insère dans le champ de fusion actuel.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## Étape 7 : Insertion du document

Cette méthode insère le document spécifié dans le paragraphe ou la cellule du tableau actuel.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## Conclusion

Et voila! Vous avez réussi à insérer des documents dans des champs spécifiques lors d'une opération de publipostage à l'aide d'Aspose.Words pour .NET. Cette fonctionnalité puissante peut vous faire gagner beaucoup de temps et d’efforts, en particulier lorsque vous traitez de gros volumes de documents. Pensez-y comme si vous aviez un assistant personnel qui s’occupe de tout le gros du travail à votre place. Alors, allez-y et essayez-le. Bon codage !

## FAQ

### Puis-je insérer plusieurs documents dans différents champs de fusion ?
 Oui, vous pouvez. Spécifiez simplement les champs de fusion appropriés et les chemins de documents correspondants dans le`MailMerge.Execute` méthode.

### Est-il possible de formater le document inséré différemment du document principal ?
 Absolument! Vous pouvez utiliser le`ImportFormatMode` paramètres dans le`NodeImporter` pour contrôler le formatage.

### Que se passe-t-il si le nom du champ de fusion est dynamique ?
Vous pouvez gérer les noms de champs de fusion dynamiques en les transmettant comme paramètres au gestionnaire de rappel.

### Puis-je utiliser cette méthode avec différents formats de fichiers ?
Oui, Aspose.Words prend en charge divers formats de fichiers, notamment DOCX, PDF, etc.

### Comment gérer les erreurs lors du processus d’insertion de documents ?
Implémentez la gestion des erreurs dans votre gestionnaire de rappel pour gérer les exceptions pouvant survenir.