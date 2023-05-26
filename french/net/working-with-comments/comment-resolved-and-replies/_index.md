---
title: Commentaire résolu et réponses
linktitle: Commentaire résolu et réponses
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à résoudre les commentaires et leurs réponses dans les documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-comments/comment-resolved-and-replies/
---

Dans ce didacticiel complet, vous apprendrez à résoudre les commentaires et leurs réponses dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de gérer la résolution des commentaires et de mettre à jour le statut des commentaires et leurs réponses.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Chargez le document et accédez aux commentaires
Pour commencer, chargez le document contenant les commentaires à l'aide de la classe Document et accédez à la collection comments :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Étape 2 : résoudre les commentaires et leurs réponses
Ensuite, parcourez les commentaires et leurs réponses pour les marquer comme résolus :

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Dans le code ci-dessus, nous accédons au commentaire parent et parcourons ses réponses. Nous pouvons récupérer l'ID du commentaire parent et son statut de résolution. Ensuite, nous mettons à jour la marque "Terminé" de chaque réponse de commentaire pour indiquer la résolution.

## Étape 3 : Enregistrer le document
Après avoir résolu les commentaires et mis à jour leur statut, enregistrez le document modifié dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Exemple de code source pour résoudre les commentaires et leurs réponses à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour résoudre les commentaires et leurs réponses en utilisant Aspose.Words pour .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
N'oubliez pas d'ajuster le code en fonction de vos besoins spécifiques, y compris le chemin du fichier de document et la personnalisation supplémentaire

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment résoudre les commentaires et leurs réponses dans un document Word à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais gérer la résolution des commentaires et mettre à jour le statut des commentaires et leurs réponses en fonction de vos besoins.

La résolution des commentaires aide à suivre et à gérer les commentaires dans un document. Testez différents statuts de commentaires et personnalisez-les pour améliorer la collaboration et les processus de révision de vos documents.
