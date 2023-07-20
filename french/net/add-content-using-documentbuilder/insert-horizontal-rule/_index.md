---
title: Insérer une règle horizontale dans un document Word
linktitle: Insérer une règle horizontale dans un document Word
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

### FAQ pour insérer une règle horizontale dans un document Word

#### Q : Puis-je personnaliser l'apparence de la règle horizontale ?

R : Oui, absolument ! Aspose.Words pour .NET fournit diverses propriétés pour personnaliser l'apparence de la règle horizontale. Vous pouvez ajuster sa largeur, sa hauteur, son alignement, sa couleur et son ombrage en fonction de l'esthétique de votre document.

#### Q : Puis-je ajouter plusieurs règles horizontales dans un seul document ?

R : Certainement ! Vous pouvez insérer autant de règles horizontales que nécessaire dans un document Word en utilisant Aspose.Words pour .NET. Répétez simplement le processus d'insertion pour ajouter plusieurs pauses visuelles ou séparateurs de section.

#### Q : Les règles horizontales sont-elles compatibles avec d'autres formats de fichiers, tels que PDF ?

: Oui, les règles horizontales insérées à l'aide d'Aspose.Words pour .NET sont compatibles avec divers formats de fichiers, notamment DOCX et PDF. Cela signifie que vous pouvez exporter vos documents dans différents formats tout en conservant les règles horizontales.

#### Q : Puis-je insérer par programmation une règle horizontale à des positions spécifiques dans le document ?

R : Absolument ! Aspose.Words pour .NET vous permet de positionner la règle horizontale à des emplacements spécifiques dans le document par programmation. Vous pouvez contrôler son emplacement en fonction du contenu et de la structure de votre document.

#### Q : Aspose.Words pour .NET convient-il à la fois aux applications de bureau et Web ?

R : Oui, Aspose.Words pour .NET est polyvalent et peut être utilisé à la fois dans les applications de bureau et Web. Que vous construisiez une application Windows ou un système basé sur le Web, vous pouvez intégrer la bibliothèque sans effort.