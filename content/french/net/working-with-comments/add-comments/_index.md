---
title: Ajoutez des commentaires
linktitle: Ajoutez des commentaires
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter des commentaires aux documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-comments/add-comments/
---

Dans ce didacticiel complet, vous apprendrez comment ajouter des commentaires à un document Word à l'aide d'Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous pourrez insérer des commentaires et personnaliser leur contenu dans vos documents.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : ajouter du contenu au document
Ensuite, ajoutez le contenu souhaité au document à l'aide de l'objet DocumentBuilder. Dans cet exemple, nous ajoutons du texte :

```csharp
builder.Write("Some text is added.");
```

## Étape 3 : Créez un commentaire et ajoutez du contenu
Pour ajouter un commentaire, créez une instance de la classe Comment, en transmettant l'objet Document, le nom de l'auteur, les initiales de l'auteur et la date actuelle :

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Ensuite, ajoutez le commentaire au paragraphe actuel :

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Ajoutez du contenu au commentaire, tel qu'un paragraphe et du texte :

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Étape 4 : Enregistrez le document
Après avoir ajouté le commentaire et son contenu, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Exemple de code source pour ajouter des commentaires à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour ajouter des commentaires à l’aide d’Aspose.Words for .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment ajouter des commentaires à un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais insérer des commentaires et personnaliser leur contenu dans vos documents.

Les commentaires sont utiles pour collaborer, fournir des informations supplémentaires ou prendre des notes dans un document. Expérimentez avec différents noms d'auteurs, initiales et contenus de commentaires pour répondre à vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je ajouter un commentaire dans un document Aspose.Words for .NET ?

R : Pour ajouter un commentaire dans un document Aspose.Words for .NET, vous devez suivre les étapes mentionnées dans le didacticiel.

#### Q : Puis-je formater le texte des commentaires dans Aspose.Words pour .NET ?

R : Oui, vous pouvez formater le texte des commentaires dans Aspose.Words for .NET à l'aide des propriétés de formatage disponibles.

#### Q : Comment récupérer tous les commentaires présents dans un document ?

 : Vous pouvez récupérer tous les commentaires présents dans un document en utilisant le`Document.Comments` propriété.

#### Q : Puis-je supprimer un commentaire spécifique dans Aspose.Words pour .NET ?

 R : Oui, vous pouvez supprimer un commentaire spécifique dans Aspose.Words for .NET à l'aide de l'outil`Comment.Remove` méthode.

#### Q : Comment puis-je modifier le texte d'un commentaire existant dans Aspose.Words for .NET ?

 R : Pour modifier le texte d'un commentaire existant dans Aspose.Words for .NET, vous pouvez accéder au`Comment.Text` propriété du correspondant`Comment` objet et modifiez le texte si nécessaire.