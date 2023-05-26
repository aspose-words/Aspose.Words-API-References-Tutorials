---
title: Ajouter le japonais comme langue d'édition
linktitle: Ajouter le japonais comme langue d'édition
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour ajouter le japonais comme langue d'édition avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

Dans ce didacticiel, nous vous guiderons étape par étape pour comprendre et implémenter la fonctionnalité d'ajout du japonais comme langue d'édition avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de définir des préférences linguistiques lors du chargement d'un document et d'ajouter le japonais comme langue d'édition.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document Word qui ne contient pas de langue d'édition par défaut et auquel nous souhaitons ajouter le japonais. Utilisez le code suivant pour charger le document :

```csharp
LoadOptions loadOptions = new LoadOptions();

// Définissez les préférences de langue qui seront utilisées lors du chargement du document.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Étape 3 : Vérification de la langue par défaut

Après avoir chargé le document, nous vérifierons si la langue d'édition par défaut a été correctement définie sur le japonais. Utilisez le code suivant pour obtenir l'ID de langue extrême-orientale :

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Le code vérifie si l'ID de langue d'Extrême-Orient correspond à celui du japonais. Selon le résultat, il affiche un message correspondant.

### Exemple de code source pour Ajouter le japonais en tant que langues d'édition à l'aide d'Aspose.Words pour .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Définissez les préférences de langue qui seront utilisées lors du chargement du document.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

