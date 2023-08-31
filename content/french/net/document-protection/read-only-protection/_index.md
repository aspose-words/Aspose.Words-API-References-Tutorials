---
title: Protection en lecture seule dans un document Word
linktitle: Protection en lecture seule dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment protéger vos documents Word en lecture seule avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-protection/read-only-protection/
---
Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonctionnalité de protection en lecture seule d'Aspose.Words for .NET. Cette fonctionnalité vous permet de créer un document Word en lecture seule pour empêcher toute modification non autorisée. Suivez les étapes ci-dessous :

## Étape 1 : Création du document et application de la protection

Commencez par créer une instance de la classe Document et un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Écrire le contenu du document
Utilisez l'objet DocumentBuilder pour écrire du contenu dans le document :

```csharp
builder.Write("Open document as read-only");
```

## Étape 3 : Définir le mot de passe et rendre le document en lecture seule

Définissez un mot de passe pour le document à l'aide de la propriété SetPassword() de l'objet WriteProtection :

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Assurez-vous de remplacer « MyPassword » par le mot de passe réel que vous souhaitez utiliser.

## Étape 4 : Appliquer le document en lecture seule

Rendez le document en lecture seule en définissant la propriété ReadOnlyRecommended sur true :

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Étape 5 : appliquez la protection en lecture seule et enregistrez le document

Enfin, appliquez une protection en lecture seule à l'aide de la méthode Protect() de l'objet Document :

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour enregistrer le document protégé.

### Exemple de code source pour la protection en lecture seule à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour la protection en lecture seule à l’aide d’Aspose.Words for .NET :

```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Saisissez un mot de passe comportant jusqu'à 15 caractères.
doc.WriteProtection.SetPassword("MyPassword");

// Définissez le document en lecture seule.
doc.WriteProtection.ReadOnlyRecommended = true;

// Appliquez la protection en écriture en lecture seule.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

En suivant ces étapes, vous pouvez facilement protéger vos documents

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de protection en lecture seule d'Aspose.Words pour .NET, qui vous permet de rendre les documents Word en lecture seule pour empêcher toute modification non autorisée. En suivant les étapes fournies, vous pouvez facilement appliquer une protection en lecture seule à vos documents et améliorer leur sécurité. La protection en lecture seule contribue à garantir l'intégrité et l'exactitude du contenu de votre document en limitant les capacités d'édition. Aspose.Words for .NET fournit une API puissante et flexible pour gérer la protection des documents et prend en charge diverses autres fonctionnalités pour personnaliser et sécuriser vos documents Word.

### FAQ pour la protection en lecture seule dans un document Word

#### Q : Qu'est-ce que la protection en lecture seule dans Aspose.Words pour .NET ?

R : La protection en lecture seule dans Aspose.Words pour .NET est une fonctionnalité qui vous permet de rendre un document Word en lecture seule, empêchant ainsi les modifications non autorisées. Lorsqu'un document est défini en lecture seule, les utilisateurs peuvent ouvrir et afficher le document, mais ils ne peuvent apporter aucune modification à son contenu.

#### Q : Comment puis-je appliquer une protection en lecture seule à un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour appliquer une protection en lecture seule à un document Word à l'aide d'Aspose.Words for .NET, vous pouvez suivre ces étapes :
1.  Créez une instance du`Document` classe et un`DocumentBuilder` objet.
2.  Utilisez le`DocumentBuilder` pour écrire le contenu du document.
3.  Définissez un mot de passe pour le document à l'aide du`SetPassword` méthode du`WriteProtection` objet.
4.  Met le`ReadOnlyRecommended` propriété du`WriteProtection` s'opposer à`true` pour recommander d'ouvrir le document en lecture seule.
5.  Appliquez une protection en lecture seule à l'aide de l'option`Protect` méthode du`Document` objet, en spécifiant le`ProtectionType` comme`ReadOnly`.
6.  Enregistrez le document protégé à l'aide du`Save` méthode du`Document` objet.

#### Q : Puis-je supprimer la protection en lecture seule d'un document Word à l'aide d'Aspose.Words pour .NET ?

 : Oui, vous pouvez supprimer la protection en lecture seule d'un document Word à l'aide d'Aspose.Words pour .NET. Pour ce faire, vous pouvez utiliser le`Unprotect` méthode du`Document` classe, qui supprime toute protection existante du document.

#### Q : Puis-je définir un mot de passe différent pour la protection en lecture seule dans un document Word ?

 R : Non, la protection en lecture seule dans Aspose.Words for .NET ne vous permet pas de définir un mot de passe distinct spécifiquement pour la protection en lecture seule. Le mot de passe défini à l'aide du`SetPassword` méthode du`WriteProtection` L'objet s'applique à la protection globale du document, y compris la protection en lecture seule et en lecture-écriture.

#### Q : Les utilisateurs peuvent-ils contourner la protection en lecture seule dans un document Word ?

R : La protection en lecture seule dans un document Word vise à décourager et à empêcher les modifications accidentelles ou non autorisées. Bien qu'il offre un certain niveau de protection, il peut être contourné par les utilisateurs disposant de connaissances techniques ou d'autorisations de modification suffisantes. Cependant, la protection en lecture seule a un effet dissuasif et contribue à maintenir l'intégrité du document.