---
title: Supprimer la protection des documents
linktitle: Supprimer la protection des documents
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment supprimer la protection d'un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-protection/remove-document-protection/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonction de déprotection de document d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de supprimer la protection d'un document Word pour le rendre accessible pour une modification ultérieure. Suivez les étapes ci-dessous :

## Étape 1 : création du document et ajout de contenu

Commencez par créer une instance de la classe Document et un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Ajouter du contenu au document

Utilisez l'objet DocumentBuilder pour ajouter du contenu au document :

```csharp
builder.Writeln("Text added to a document.");
```

## Étape 3 : Déprotéger le document

Pour déprotéger le document, vous pouvez utiliser la méthode Unprotect() de l'objet Document. Vous pouvez choisir de supprimer la protection sans mot de passe ou avec un mot de passe correct. Suppression de la protection sans mot de passe :

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Assurez-vous de remplacer "newPassword" par le mot de passe correct du document.

## Étape 4 : Enregistrez le document sans protection

Enfin, enregistrez le document sans protection en utilisant la méthode Save() de l'objet Document :

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour enregistrer le document sans protection.

### Exemple de code source pour supprimer la protection de document à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour déprotéger le document en utilisant Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Text added to a document.");

	// La protection des documents peut être supprimée soit sans mot de passe, soit avec le mot de passe correct.
	doc.Unprotect();
	doc.Protect(ProtectionType.ReadOnly, "newPassword");
	doc.Unprotect("newPassword");

	doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

En suivant ces étapes, vous pouvez facilement supprimer la protection du document Word avec Aspose.Words pour .NET.
