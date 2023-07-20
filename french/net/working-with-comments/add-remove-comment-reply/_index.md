---
title: Ajouter Supprimer le commentaire Répondre
linktitle: Ajouter Supprimer le commentaire Répondre
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter et supprimer des réponses aux commentaires dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-comments/add-remove-comment-reply/
---

Dans ce didacticiel complet, vous apprendrez à ajouter et à supprimer des réponses aux commentaires dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de gérer les réponses aux commentaires et de les personnaliser en fonction de vos besoins.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Charger le document
Pour commencer, chargez le document contenant les commentaires à l'aide de la classe Document :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Étape 2 : Accéder au commentaire et gérer les réponses
Ensuite, accédez au commentaire du document à l'aide de la méthode GetChild avec le paramètre NodeType.Comment :

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Pour supprimer une réponse du commentaire, utilisez la méthode RemoveReply et fournissez l'index de réponse souhaité :

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Pour ajouter une nouvelle réponse au commentaire, utilisez la méthode AddReply et indiquez le nom de l'auteur, les initiales de l'auteur, la date et l'heure et le texte de la réponse :

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Étape 3 : Enregistrer le document
Après avoir ajouté ou supprimé des réponses aux commentaires, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Exemple de code source pour ajouter et supprimer des réponses aux commentaires à l'aide de Aspose.Words pour .NET
Voici le code source complet pour ajouter et supprimer des réponses aux commentaires à l'aide d'Aspose.Words pour .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment ajouter et supprimer des réponses aux commentaires dans un document Word à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais gérer les réponses aux commentaires et les personnaliser selon vos besoins.

Les réponses aux commentaires permettent des discussions collaboratives et des commentaires dans un document. Expérimentez avec différents auteurs de réponse, initiales, dates et textes pour améliorer la collaboration et la communication au sein de vos documents.

### FAQ

#### Q : Comment puis-je ajouter un commentaire dans Aspose.Words pour .NET ?

 R : Pour ajouter un commentaire dans Aspose.Words pour .NET, vous pouvez utiliser le`Comment.AddComment` méthode spécifiant le texte du commentaire et où vous voulez l'ajouter dans le document.

#### Q : Comment puis-je supprimer un commentaire dans Aspose.Words pour .NET ?

 R : Pour supprimer un commentaire dans Aspose.Words pour .NET, vous pouvez utiliser le`Comment.Remove` méthode spécifiant la`Comment` objet que vous souhaitez supprimer.

#### Q : Puis-je répondre à un commentaire dans Aspose.Words pour .NET ?

 R : Oui, vous pouvez répondre à un commentaire dans Aspose.Words pour .NET en utilisant le`Comment.AddReply` méthode spécifiant le texte de réponse et où vous voulez l'ajouter dans le document.

#### Q : Comment puis-je accéder aux commentaires existants dans Aspose.Words pour .NET ?

 R : Vous pouvez accéder aux commentaires existants dans Aspose.Words pour .NET en utilisant le`CommentCollection` propriété de la`Document`objet. Cela vous permettra de parcourir tous les commentaires présents dans le document.

#### Q : Puis-je modifier le texte des commentaires dans Aspose.Words pour .NET ?

 R : Oui, vous pouvez modifier le texte d'un commentaire dans Aspose.Words pour .NET en accédant au`Comment.Text` propriété du correspondant`Comment` objet et en modifiant le texte si nécessaire.