---
title: Mot de passe de protection
linktitle: Mot de passe de protection
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à protéger par mot de passe vos documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-protection/password-protection/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonction de protection par mot de passe d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de protéger un document Word avec un mot de passe pour assurer sa confidentialité. Suivez les étapes ci-dessous :

## Étape 1 : création du document et application de la protection

Commencez par créer une instance de la classe Document :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Appliquer la protection par mot de passe

Ensuite, vous pouvez appliquer une protection par mot de passe à l'aide de la méthode Protect() de l'objet Document :

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

Assurez-vous de remplacer "mot de passe" par le mot de passe réel que vous souhaitez utiliser pour protéger le document.

## Étape 3 : Enregistrer le document protégé

Enfin, vous pouvez enregistrer le document protégé en utilisant la méthode Save() de l'objet Document :

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour enregistrer le document protégé.

### Exemple de code source pour la protection par mot de passe à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour la protection par mot de passe en utilisant Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	//Appliquer la protection des documents.
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

N'oubliez pas de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le répertoire de vos documents et "mot de passe" par le mot de passe réel que vous souhaitez utiliser.

