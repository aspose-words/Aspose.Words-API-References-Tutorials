---
title: Déplacer le nœud dans le document suivi
linktitle: Déplacer le nœud dans le document suivi
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment déplacer des nœuds dans un document Word suivi à l'aide d'Aspose.Words for .NET grâce à notre guide détaillé étape par étape. Parfait pour les développeurs.
type: docs
weight: 10
url: /fr/net/working-with-revisions/move-node-in-tracked-document/
---
## Introduction

Salut, passionnés d'Aspose.Words ! Si vous avez déjà eu besoin de déplacer un nœud dans un document Word lors du suivi des révisions, vous êtes au bon endroit. Aujourd'hui, nous examinons comment y parvenir à l'aide d'Aspose.Words pour .NET. Non seulement vous apprendrez le processus étape par étape, mais vous découvrirez également quelques trucs et astuces pour rendre la manipulation de vos documents fluide et efficace.

## Conditions préalables

Avant de nous salir les mains avec du code, assurons-nous que vous disposez de tout ce dont vous avez besoin :

-  Aspose.Words pour .NET : téléchargez-le[ici](https://releases.aspose.com/words/net/).
- Environnement .NET : assurez-vous d'avoir configuré un environnement de développement .NET compatible.
- Connaissances de base de C# : ce didacticiel suppose que vous possédez une compréhension de base de C#.

Vous avez tout ? Super! Passons aux espaces de noms que nous devons importer.

## Importer des espaces de noms

Tout d’abord, nous devons importer les espaces de noms nécessaires. Ceux-ci sont essentiels pour travailler avec Aspose.Words et gérer les nœuds de document.

```csharp
using Aspose.Words;
using System;
```

Très bien, décomposons le processus en étapes gérables. Chaque étape sera expliquée en détail pour vous assurer de comprendre ce qui se passe à chaque instant.

## Étape 1 : initialiser le document

 Pour commencer, nous devons initialiser un nouveau document et utiliser un`DocumentBuilder` pour ajouter quelques paragraphes.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ajout de quelques paragraphes
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");

// Vérifiez le nombre de paragraphes initial
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Étape 2 : Commencer le suivi des révisions

Ensuite, nous devons commencer à suivre les révisions. Ceci est crucial car cela nous permet de voir les modifications apportées au document.

```csharp
// Commencer le suivi des révisions
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Étape 3 : Déplacer les nœuds

Vient maintenant la partie essentielle de notre tâche : déplacer un nœud d’un emplacement à un autre. Nous allons déplacer le troisième paragraphe et le placer avant le premier paragraphe.

```csharp
// Définir le nœud à déplacer et sa plage de fin
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];

// Déplacer les nœuds dans la plage définie
while (node != endNode)
{
    Node nextNode = node.NextSibling;
    body.InsertBefore(node, referenceNode);
    node = nextNode;
}
```

## Étape 4 : Arrêter le suivi des révisions

Une fois que nous avons déplacé les nœuds, nous devons arrêter de suivre les révisions.

```csharp
// Arrêter de suivre les révisions
doc.StopTrackRevisions();
```

## Étape 5 : Enregistrez le document

Enfin, sauvegardons notre document modifié dans le répertoire spécifié.

```csharp
// Enregistrez le document modifié
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");

// Afficher le nombre final de paragraphes
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Conclusion

Et voilà ! Vous avez réussi à déplacer un nœud dans un document suivi à l'aide d'Aspose.Words pour .NET. Cette puissante bibliothèque facilite la manipulation des documents Word par programmation. Que vous créiez, modifiiez ou suiviez les modifications, Aspose.Words est là pour vous. Alors, allez-y et essayez-le. Bon codage !

## FAQ

### Qu’est-ce qu’Aspose.Words pour .NET ?

Aspose.Words for .NET est une bibliothèque de classes permettant de travailler avec des documents Word par programmation. Il permet aux développeurs de créer, modifier, convertir et imprimer des documents Word dans des applications .NET.

### Comment suivre les révisions dans un document Word à l’aide d’Aspose.Words ?

 Pour suivre les révisions, utilisez le`StartTrackRevisions` méthode sur le`Document` objet. Cela permettra le suivi des révisions, affichant toutes les modifications apportées au document.

### Puis-je déplacer plusieurs nœuds dans Aspose.Words ?

Oui, vous pouvez déplacer plusieurs nœuds en les itérant et en utilisant des méthodes telles que`InsertBefore` ou`InsertAfter` pour les placer à l'endroit souhaité.

### Comment arrêter le suivi des révisions dans Aspose.Words ?

 Utilisez le`StopTrackRevisions` méthode sur le`Document` objet pour arrêter le suivi des révisions.

### Où puis-je trouver plus de documentation sur Aspose.Words pour .NET ?

 Vous pouvez trouver une documentation détaillée[ici](https://reference.aspose.com/words/net/).