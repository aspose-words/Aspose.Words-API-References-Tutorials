---
title: Protection en lecture seule
linktitle: Protection en lecture seule
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à protéger vos documents Word en lecture seule avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-protection/read-only-protection/
---
Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonction de protection en lecture seule d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de rendre un document Word en lecture seule pour empêcher toute modification non autorisée. Suivez les étapes ci-dessous :

## Étape 1 : création du document et application de la protection

Commencez par créer une instance de la classe Document et un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Écrivez du contenu dans le document
Utilisez l'objet DocumentBuilder pour écrire du contenu dans le document :

```csharp
builder.Write("Open document as read-only");
```

## Étape 3 : Définir le mot de passe et rendre le document en lecture seule

Définissez un mot de passe pour le document à l'aide de la propriété SetPassword() de l'objet WriteProtection :

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Assurez-vous de remplacer "MyPassword" par le mot de passe réel que vous souhaitez utiliser.

## Étape 4 : Appliquer le document en lecture seule

Rendez le document en lecture seule en définissant la propriété ReadOnlyRecommended sur true :

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Étape 5 : Appliquez la protection en lecture seule et enregistrez le document

Enfin, appliquez la protection en lecture seule à l'aide de la méthode Protect() de l'objet Document :

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour enregistrer le document protégé.

### Exemple de code source pour la protection en lecture seule avec Aspose.Words pour .NET

Voici le code source complet pour la protection en lecture seule à l'aide d'Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	// Entrez un mot de passe de 15 caractères maximum.
	doc.WriteProtection.SetPassword("MyPassword");

	// Rendez le document en lecture seule.
	doc.WriteProtection.ReadOnlyRecommended = true;

	// Appliquez la protection en écriture en lecture seule.
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

En suivant ces étapes, vous pouvez facilement protéger vos documents

