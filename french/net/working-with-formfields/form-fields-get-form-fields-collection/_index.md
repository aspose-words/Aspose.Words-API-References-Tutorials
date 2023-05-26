---
title: Champs de formulaire Obtenir la collection de champs de formulaire
linktitle: Champs de formulaire Obtenir la collection de champs de formulaire
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à récupérer et à manipuler la collection de champs de formulaire dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-formfields/form-fields-get-form-fields-collection/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour récupérer la collection de champs de formulaire à partir d'un document Word. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre document source contenant les champs de formulaire :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");
```

## Étape 2 : Récupération de la collection de champs de formulaire

 Ensuite, accédez au`FormFields` propriété de la`Range` objet dans le document pour récupérer la collection de champs de formulaire :

```csharp
FormFieldCollection formFields = doc.Range.FormFields;
```

 Maintenant, vous avez la collection de champs de formulaire du document Word stocké dans le`formFields` variable.

## Étape 3 : Accéder et manipuler les champs du formulaire

Vous pouvez parcourir la collection de champs de formulaire et effectuer diverses opérations sur chaque champ de formulaire, telles que l'obtention ou la définition de valeurs, la modification de la mise en forme ou l'extraction d'informations.

```csharp
foreach (FormField formField in formFields)
{
    // Accéder et manipuler chaque champ de formulaire
    // ...
}
```

## Étape 4 : Enregistrer le document

Enfin, enregistrez le document modifié si nécessaire :

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

C'est ça! Vous avez récupéré avec succès la collection de champs de formulaire d'un document Word à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour les champs de formulaire Obtenir la collection de champs de formulaire à l'aide de Aspose.Words pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection formFields = doc.Range.FormFields;

// Accéder et manipuler les champs du formulaire selon les besoins
// ...

doc.Save(dataDir + "ModifiedFormFields.docx");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.