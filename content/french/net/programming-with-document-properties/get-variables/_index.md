---
title: Obtenir des variables
linktitle: Obtenir des variables
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour récupérer les variables de document avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-properties/get-variables/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour récupérer les variables d'un document avec Aspose.Words for .NET. Cette fonctionnalité vous permet d'accéder aux variables définies dans un document.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words for .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document Word à partir duquel nous souhaitons récupérer les variables. Utilisez le code suivant pour charger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Récupération des variables

Nous allons maintenant récupérer les variables définies dans le document. Utilisez le code suivant :

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Ce code parcourt chaque paire clé-valeur dans les variables du document et récupère le nom et la valeur de chaque variable. Les variables sont ensuite concaténées pour afficher les informations de chaque variable.

### Exemple de code source pour obtenir des variables à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Assurez-vous de spécifier le chemin d'accès correct au document dans le champ`dataDir` variable.

Vous avez maintenant appris à récupérer des variables d'un document à l'aide d'Aspose.Words for .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement accéder et afficher les variables de vos propres documents.