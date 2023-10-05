---
title: Champs de formulaire obtenus par nom
linktitle: Champs de formulaire obtenus par nom
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment récupérer et modifier les champs de formulaire par nom dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-formfields/form-fields-get-by-name/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words for .NET pour récupérer les champs de formulaire par nom à partir d'un document Word. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

 Pour commencer, assurez-vous que Aspose.Words for .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas fait, téléchargez et installez la bibliothèque depuis[Aspose.Releases]https://releases.aspose.com/words/net/.

## Étape 1 : initialisation de l'objet document

 Tout d'abord, initialisez le`Document` objectez en fournissant le chemin d'accès à votre document source contenant les champs du formulaire :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Étape 2 : Récupération des champs du formulaire

 Ensuite, accédez au`FormFields` propriété du`Range` objet dans le document pour récupérer tous les champs du formulaire :

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Vous pouvez récupérer les champs du formulaire soit par index, soit par nom. Dans cet exemple, nous récupérons un champ de formulaire en utilisant les deux méthodes :

```csharp
FormField formField1 = documentFormFields[3]; // Récupération par index
FormField formField2 = documentFormFields["Text2"]; // Récupération par nom
```

## Étape 3 : Modification des propriétés du champ de formulaire

Une fois que vous avez récupéré les champs du formulaire, vous pouvez modifier leurs propriétés selon vos besoins. Dans cet exemple, nous modifions la taille de la police de`formField1` à 20 et la couleur de la police de`formField2` au rouge :

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Étape 4 : enregistrement du document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

C'est ça! Vous avez réussi à récupérer les champs de formulaire par nom et à modifier leurs propriétés dans un document Word à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour les champs de formulaire Get By Name à l'aide d'Aspose.Words pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je obtenir un champ de formulaire par son nom dans Aspose.Words ?

 R : Pour obtenir un champ de formulaire par son nom dans Aspose.Words, vous pouvez utiliser le`Document.Range.FormFields[name]` méthode. Cette méthode renvoie le champ de formulaire correspondant au nom spécifié.

#### Q : Que se passe-t-il si le champ de formulaire portant le nom spécifié n'existe pas dans le document ?

 R : Si le champ de formulaire portant le nom spécifié n'existe pas dans le document, le`Document.Range.FormFields[name]` la méthode reviendra`null`. Vous pouvez vérifier ce résultat pour gérer les cas où le champ du formulaire est introuvable.

#### Q : Comment puis-je modifier les propriétés d'un champ de formulaire trouvé ?

R : Une fois que vous obtenez un champ de formulaire par son nom, vous pouvez accéder à ses propriétés individuelles pour les modifier. Par exemple, vous pouvez modifier la valeur du champ, activer ou désactiver sa visibilité ou modifier d'autres propriétés selon vos besoins.

#### Q : Puis-je obtenir plusieurs champs de formulaire portant le même nom dans un document ?

 R : Oui, il est possible d'avoir plusieurs champs de formulaire portant le même nom dans un document. Dans ce cas, le`Document.Range.FormFields[name]` La méthode renverra le premier champ de formulaire trouvé avec le nom spécifié. Si vous disposez de plusieurs champs de formulaire portant le même nom, vous devrez en tenir compte lors de la manipulation des champs.

#### Q : Comment puis-je parcourir tous les champs de formulaire d'un document ?

 R : Pour parcourir tous les champs de formulaire d'un document, vous pouvez utiliser un`foreach` boucle sur le`Document.Range.FormFields` collection. Cela vous permettra d'accéder à chaque champ du formulaire individuellement et d'effectuer des opérations sur chacun d'eux.