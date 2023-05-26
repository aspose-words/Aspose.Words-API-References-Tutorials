---
title: Champs de formulaire Obtenir par nom
linktitle: Champs de formulaire Obtenir par nom
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment récupérer et modifier des champs de formulaire par leur nom dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-formfields/form-fields-get-by-name/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour récupérer les champs de formulaire par nom à partir d'un document Word. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre document source contenant les champs de formulaire :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Étape 2 : Récupération des champs de formulaire

 Ensuite, accédez au`FormFields` propriété de la`Range` objet dans le document pour récupérer tous les champs du formulaire :

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Vous pouvez récupérer les champs de formulaire soit par index, soit par nom. Dans cet exemple, nous récupérons un champ de formulaire en utilisant les deux méthodes :

```csharp
FormField formField1 = documentFormFields[3]; // Récupération par index
FormField formField2 = documentFormFields["Text2"]; // Récupération par nom
```

## Étape 3 : Modification des propriétés du champ de formulaire

 Une fois que vous avez récupéré les champs du formulaire, vous pouvez modifier leurs propriétés selon vos besoins. Dans cet exemple, nous changeons la taille de la police de`formField1` à 20 et la couleur de police de`formField2` au rouge :

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Étape 4 : Enregistrer le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

C'est ça! Vous avez récupéré avec succès les champs de formulaire par nom et modifié leurs propriétés dans un document Word à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour les champs de formulaire Get By Name à l'aide de Aspose.Words pour .NET

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
