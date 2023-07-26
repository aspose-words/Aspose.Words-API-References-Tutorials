---
title: Format de règle horizontale dans un document Word
linktitle: Format de règle horizontale dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à formater les règles horizontales dans les documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/horizontal-rule-format/
---
Dans cet exemple complet, vous apprendrez à formater une règle horizontale dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de personnaliser l'alignement, la largeur, la hauteur, la couleur et d'autres propriétés d'une règle horizontale.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un DocumentBuilder et insérer une règle horizontale
Pour commencer, créez un objet DocumentBuilder et utilisez la méthode InsertHorizontalRule pour insérer une règle horizontale :

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Étape 2 : Accéder au format de règle horizontale
Accédez ensuite à la propriété HorizontalRuleFormat de l'objet Shape pour récupérer les options de mise en forme :

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Étape 3 : Personnalisez les options de formatage
Désormais, vous pouvez personnaliser diverses options de mise en forme pour la règle horizontale. Par exemple, vous pouvez régler l'alignement, la largeur, la hauteur, la couleur et l'ombrage :

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Étape 4 : Enregistrer le document
Après avoir formaté la règle horizontale, enregistrez le document dans un fichier à l'aide de la méthode Save de l'objet Document :

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Exemple de code source pour le format de règle horizontale à l'aide de Aspose.Words pour .NET
Voici le code source complet pour formater une règle horizontale en utilisant Aspose.Words pour .NET :

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

N'oubliez pas d'ajuster le code en fonction de vos besoins spécifiques et de l'améliorer avec des fonctionnalités supplémentaires si nécessaire.

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment formater une règle horizontale dans un document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais personnaliser l'apparence des règles horizontales pour améliorer la mise en page visuelle de votre document.

Expérimentez avec différentes options de mise en forme pour obtenir le style et l'effet souhaités pour vos règles horizontales.

### FAQ sur le format de règle horizontale dans un document Word

#### Q : Puis-je appliquer différentes couleurs à la règle horizontale ?

R : Absolument ! Avec Aspose.Words pour .NET, vous pouvez facilement personnaliser la couleur de la règle horizontale en définissant la propriété Color sur la valeur de couleur souhaitée. Cela vous permet de faire correspondre la règle horizontale avec la conception globale de votre document.

#### Q : Est-il possible d'ajuster la largeur et la hauteur de la règle horizontale ?

R : Oui, vous avez un contrôle total sur la largeur et la hauteur de la règle horizontale. En modifiant les propriétés WidthPercent et Height, vous pouvez obtenir les dimensions souhaitées pour la règle horizontale.

#### Q : Puis-je modifier l'alignement de la règle horizontale dans le document ?

R : Certainement ! Aspose.Words pour .NET vous permet de spécifier l'alignement de la règle horizontale à l'aide de la propriété Alignment. Vous pouvez choisir parmi différentes options telles que Centre, Gauche, Droite et Justifié.

#### Q : Puis-je appliquer un ombrage ou une couleur d'arrière-plan à la règle horizontale ?

R : Oui, vous pouvez ajouter un ombrage ou une couleur d'arrière-plan à la règle horizontale. Par défaut, la propriété NoShade est définie sur true, mais vous pouvez la définir sur false et définir l'ombrage à l'aide des méthodes appropriées.

#### Q : Puis-je insérer plusieurs filets horizontaux dans un même document ?

: Absolument ! Vous pouvez insérer plusieurs règles horizontales dans un document Word à l'aide de Aspose.Words pour .NET. Répétez simplement les étapes du didacticiel si nécessaire pour ajouter autant de règles horizontales que nécessaire.