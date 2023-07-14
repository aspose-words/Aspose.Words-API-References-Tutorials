---
title: Insérer une règle horizontale
linktitle: Insérer une règle horizontale
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer des règles horizontales dans des documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-horizontal-rule/
---

Dans cet exemple complet, vous apprendrez à insérer une règle horizontale dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure d'ajouter des règles horizontales à vos documents pour une séparation visuelle et une organisation.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer une règle horizontale
Ensuite, utilisez la méthode Writeln de la classe DocumentBuilder pour ajouter un texte descriptif puis insérez une règle horizontale :

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Étape 3 : Enregistrer le document
Après avoir inséré la règle horizontale, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Exemple de code source pour insérer une règle horizontale à l'aide de Aspose.Words pour .NET
Voici le code source complet pour insérer une règle horizontale en utilisant Aspose.Words pour .NET :
Les règles horizontales sont utiles pour divers scénarios, tels que la division de sections, la création de pauses visuelles ou la mise en évidence d'informations importantes.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

N'oubliez pas d'ajuster le code en fonction de vos besoins spécifiques et de l'améliorer avec des fonctionnalités supplémentaires si nécessaire.

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment insérer une règle horizontale dans un document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais séparer et organiser visuellement vos documents à l'aide de règles horizontales.

