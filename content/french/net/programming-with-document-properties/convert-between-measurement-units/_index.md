---
title: Convertir entre les unités de mesure
linktitle: Convertir entre les unités de mesure
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour la conversion entre les unités de mesure dans un document avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-properties/convert-between-measurement-units/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour convertir entre les unités de mesure avec Aspose.Words for .NET. Cette fonctionnalité vous permet de spécifier les marges, les distances d'en-tête et de pied de page, etc. dans différentes unités de mesure.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words for .NET est référencée dans votre projet.

## Étape 2 : Création du document et du constructeur

Dans cette étape, nous allons créer un nouveau document et initialiser le constructeur. Utilisez le code suivant :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Configurer les unités de mesure

Nous allons maintenant convertir les valeurs des marges, des distances d'en-tête et de pied de page, etc. dans différentes unités de mesure. Utilisez le code suivant pour spécifier les valeurs dans des unités de mesure spécifiques :

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Ce code utilise le`ConvertUtil` classe d'Aspose.Words pour convertir les valeurs spécifiées en pouces (`InchToPoint` ). Vous pouvez également utiliser d'autres méthodes de conversion disponibles dans le`ConvertUtil` classe pour convertir les valeurs vers d’autres unités de mesure.

### Exemple de code source pour la conversion entre unités de mesure à l'aide d'Aspose.Words pour .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Vous avez maintenant appris à effectuer une conversion entre les unités de mesure lors de la spécification des marges, des distances d'en-tête et de pied de page, etc. dans un document à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce tutoriel, vous pourrez facilement spécifier les valeurs dans les unités de mesure souhaitées dans vos propres documents.