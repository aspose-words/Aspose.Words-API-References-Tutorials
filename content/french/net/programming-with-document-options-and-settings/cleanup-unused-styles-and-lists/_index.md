---
title: Nettoyer les styles et les listes inutilisés
linktitle: Nettoyer les styles et les listes inutilisés
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour nettoyer les styles et les listes inutilisés dans un document avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour nettoyer les styles et les listes inutilisés avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de supprimer les styles et les listes qui ne sont pas utilisés dans un document.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words for .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous chargerons le document Word contenant les styles et les listes inutilisés que nous souhaitons nettoyer. Utilisez le code suivant pour charger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Comptez les styles et les listes avant de nettoyer

Avant le nettoyage, nous compterons le nombre de styles et de listes présents dans le document. Utilisez le code suivant pour afficher les compteurs :

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Ces instructions indiquent le nombre de styles et de listes présents dans le document avant le nettoyage.

## Étape 4 : Nettoyer les styles et les listes inutilisés

Nettoyons maintenant les styles et les listes inutilisés du document. Utilisez le code suivant pour effectuer le nettoyage :

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Ce code nettoie les styles et les listes inutilisés du document à l'aide des options spécifiées. Dans cet exemple, nous avons activé le`UnusedStyles` option pour supprimer les styles inutilisés et désactiver l'option`UnusedLists` possibilité de conserver les listes même si elles ne sont pas utilisées.

## Étape 5 : Comptez les styles et les listes après le nettoyage

Après avoir effectué le nettoyage, nous compterons à nouveau les styles et les listes pour vérifier s'ils ont été réduits. Utilisez le code suivant pour afficher les nouveaux compteurs :

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Ces instructions indiquent le nombre de styles et de listes restant après le nettoyage.

### Exemple de code source pour nettoyer les styles et les listes inutilisés à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Combiné avec les styles intégrés, le document dispose désormais de huit styles.
	// Un style personnalisé est marqué comme « utilisé » lorsqu'il y a du texte dans le document
	// formaté dans ce style. Cela signifie que les 4 styles que nous avons ajoutés sont actuellement inutilisés.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Nettoie les styles et les listes inutilisés du document en fonction des options de nettoyage données.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Assurez-vous de spécifier le chemin d'accès correct au document dans le champ`dataDir` variable.

Vous avez maintenant appris à nettoyer les styles et les listes inutilisés d'un document à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement appliquer cette fonctionnalité à vos propres documents.

