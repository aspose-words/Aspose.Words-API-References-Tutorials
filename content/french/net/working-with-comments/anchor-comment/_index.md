---
title: Commentaire d'ancrage
linktitle: Commentaire d'ancrage
second_title: API de traitement de documents Aspose.Words
description: Apprenez à ancrer les réponses aux commentaires à un texte spécifique dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-comments/anchor-comment/
---

Dans ce didacticiel complet, vous apprendrez à ancrer les réponses aux commentaires à un texte spécifique dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure d'associer des commentaires à un texte spécifique dans vos documents.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et ajouter du texte
Pour commencer, créez un nouveau document en utilisant la classe Document et ajoutez le texte souhaité :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Étape 2 : créer un commentaire et ajouter une plage de commentaires
Créez ensuite un commentaire et associez-le à un texte spécifique à l'aide des objets CommentRangeStart et CommentRangeEnd :

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Étape 3 : Enregistrer le document
Après avoir ancré le commentaire à un texte spécifique, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Exemple de code source pour la réponse au commentaire d'ancrage à l'aide de Aspose.Words pour .NET
Voici le code source complet pour ancrer une réponse de commentaire en utilisant Aspose.Words pour .NET :

```csharp
// Créez une instance du document.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Créez trois objets Run.
// Les deux premiers exécutent du texte, tandis que le troisième exécute un commentaire

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Chacun des objets Run est associé à un objet CommentRangeStart et CommentRangeEnd.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### FAQ

#### Q : Qu'est-ce qu'une ancre de commentaire dans Aspose.Words pour .NET ?

R : Dans Aspose.Words pour .NET, une ancre de commentaire est un marqueur qui relie un commentaire à un emplacement spécifique dans un document.

#### Q : Comment puis-je ajouter une ancre de commentaire dans un document Aspose.Words pour .NET ?

R : Pour ajouter une ancre de commentaire dans un document Aspose.Words pour .NET, suivez les étapes mentionnées dans le didacticiel.

#### Q : Comment accéder à une ancre de commentaire existante dans Aspose.Words pour .NET ?

 R : Vous pouvez accéder à une ancre de commentaire existante dans Aspose.Words pour .NET en utilisant le`Comment.Anchor` propriété.

#### Q : Puis-je supprimer une ancre de commentaire dans Aspose.Words pour .NET ?

 R : Oui, vous pouvez supprimer une ancre de commentaire dans Aspose.Words pour .NET en utilisant le`Comment.Remove` méthode.

#### Q : Comment puis-je modifier le texte d'un commentaire lié à une ancre de commentaire dans Aspose.Words pour .NET ?

 R : Pour modifier le texte d'un commentaire lié à une ancre de commentaire dans Aspose.Words pour .NET, vous pouvez accéder au`Comment.Text` propriété du correspondant`Comment` objet et modifiez le texte si nécessaire.

