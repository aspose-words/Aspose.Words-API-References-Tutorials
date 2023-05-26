---
title: Supprimer la restriction de lecture seule
linktitle: Supprimer la restriction de lecture seule
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment supprimer la restriction en lecture seule d'un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-protection/remove-read-only-restriction/
---
Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour utiliser Aspose.Words pour la fonctionnalité de suppression des restrictions en lecture seule .NET. Cette fonctionnalité vous permet de supprimer la restriction de lecture seule d'un document Word pour le rendre modifiable. Suivez les étapes ci-dessous :

## Étape 1 : création du document et définition de la protection

Commencez par créer une instance de la classe Document :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Définissez un mot de passe pour le document à l'aide de la propriété SetPassword() de l'objet WriteProtection :

Assurez-vous de remplacer "MyPassword" par le mot de passe réel que vous avez utilisé pour protéger le document.

## Étape 2 : Supprimer la restriction de lecture seule

Pour supprimer la restriction de lecture seule, définissez la propriété ReadOnlyRecommended sur false :

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Étape 3 : Appliquer la protection illimitée

Enfin, appliquez une protection illimitée à l'aide de la méthode Protect() de l'objet Document :

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour enregistrer le document sans la restriction de lecture seule.

### Exemple de code source pour supprimer la restriction en lecture seule à l'aide de Aspose.Words pour .NET

Voici le code source complet pour supprimer la restriction en lecture seule à l'aide d'Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	// Saisissez un mot de passe comportant jusqu'à 15 caractères.
	doc.WriteProtection.SetPassword("MyPassword");

	// Supprimez l'option de lecture seule.
	doc.WriteProtection.ReadOnlyRecommended = false;

	// Appliquez la protection en écriture sans aucune protection.
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

En suivant ces étapes, vous pouvez facilement supprimer la restriction en lecture seule d'un document Word avec Aspose.Words pour .NET.

