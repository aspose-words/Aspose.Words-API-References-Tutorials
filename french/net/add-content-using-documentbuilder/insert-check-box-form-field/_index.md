---
title: Insérer un champ de formulaire de case à cocher dans un document Word
linktitle: Insérer un champ de formulaire de case à cocher dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer des champs de formulaire de case à cocher dans des documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-check-box-form-field/
---
Dans ce didacticiel complet, vous apprendrez à insérer un champ de formulaire de case à cocher dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure d'ajouter des champs de formulaire de case à cocher avec des propriétés personnalisables à vos documents.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer un champ de formulaire de case à cocher
Ensuite, utilisez la méthode InsertCheckBox de la classe DocumentBuilder pour insérer un champ de formulaire de case à cocher. Fournissez le nom, l'état coché, l'état par défaut et les paramètres de taille en tant qu'arguments :

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## Étape 3 : Enregistrer le document
Après avoir inséré le champ de formulaire de case à cocher, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Exemple de code source pour Insérer un champ de formulaire de case à cocher à l'aide de Aspose.Words pour .NET
Voici le code source complet pour insérer un champ de formulaire de case à cocher en utilisant Aspose.Words pour .NET :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", true, true, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

N'oubliez pas d'ajuster le code en fonction de vos besoins spécifiques et de l'améliorer avec des fonctionnalités supplémentaires si nécessaire.

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment insérer un champ de formulaire de case à cocher dans un document Word à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais améliorer vos documents avec des champs de formulaire de case à cocher interactifs.

### FAQ

#### Q : Puis-je insérer plusieurs champs de formulaire de case à cocher dans un seul document ?

R : Absolument ! Vous pouvez insérer autant de champs de formulaire de case à cocher que nécessaire dans un document Word à l'aide de Aspose.Words pour .NET. Répétez simplement le processus d'insertion pour ajouter plusieurs cases à cocher interactives.

#### Q : Puis-je définir l'état initial (coché ou décoché) du champ de formulaire de case à cocher ?

R : Oui, vous avez un contrôle total sur l'état initial du champ de formulaire de case à cocher. En définissant le paramètre d'état coché sur true ou false, vous pouvez définir si la case à cocher est initialement cochée ou décochée.

#### Q : Les champs de formulaire de case à cocher sont-ils compatibles avec d'autres formats de fichier, tels que PDF ?

R : Oui, les champs de formulaire de case à cocher insérés à l'aide d'Aspose.Words pour .NET sont compatibles avec divers formats de fichiers, y compris DOCX et PDF. Cela vous permet d'exporter vos documents dans différents formats tout en conservant les cases à cocher interactives.

#### Q : Puis-je ajuster la taille du champ de formulaire de case à cocher ?

R : Certainement ! Vous pouvez spécifier la taille du champ de formulaire de case à cocher à l'aide du paramètre de taille dans la méthode InsertCheckBox. Cela vous permet de contrôler les dimensions de la case à cocher en fonction de vos préférences de conception.

#### Q : Aspose.Words pour .NET convient-il à la fois aux applications de bureau et Web ?

R : Oui, Aspose.Words pour .NET est une bibliothèque polyvalente adaptée aux applications de bureau et Web. Que vous construisiez une application Windows ou un système basé sur le Web, vous pouvez intégrer la bibliothèque sans effort.