---
title: Définir le russe comme langue d'édition par défaut
linktitle: Définir le russe comme langue d'édition par défaut
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour définir le russe comme langue d'édition par défaut d'un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour définir le russe comme langue d'édition par défaut avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de définir la langue par défaut lors du chargement d'un document.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words for .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous chargerons le document Word pour lequel nous souhaitons définir le russe comme langue d'édition par défaut. Utilisez le code suivant pour charger le document :

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Vérification de la langue par défaut

Après avoir téléchargé le document, nous vérifierons si la langue par défaut a été correctement définie sur le russe. Utilisez le code suivant pour obtenir l'ID de langue par défaut :

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Le code vérifie si l'identifiant de langue correspond à celui du russe. Selon le résultat, il affiche un message correspondant.

### Exemple de code source pour définir le russe comme langue d'édition par défaut à l'aide d'Aspose.Words pour .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Assurez-vous de spécifier le chemin d'accès correct au document dans le champ`dataDir` variable.

Vous avez maintenant appris à définir le russe comme langue d'édition par défaut pour un document à l'aide d'Aspose.Words for .NET. En suivant le guide des étapes