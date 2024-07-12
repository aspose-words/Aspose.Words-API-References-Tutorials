---
title: Signature d'un document Word crypté
linktitle: Signature d'un document Word crypté
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment signer des documents Word cryptés à l'aide d'Aspose.Words pour .NET avec ce guide détaillé étape par étape. Parfait pour les développeurs.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/signing-encrypted-document/
---
## Introduction

Vous êtes-vous déjà demandé comment signer un document Word crypté ? Aujourd'hui, nous allons parcourir ce processus en utilisant Aspose.Words pour .NET. Attachez votre ceinture et préparez-vous pour un didacticiel détaillé, engageant et amusant !

## Conditions préalables

Avant de plonger dans le code, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1.  Aspose.Words pour .NET : télécharger et installer à partir de[ici](https://releases.aspose.com/words/net/).
2. Visual Studio : assurez-vous de l'avoir installé.
3. Un certificat valide : vous aurez besoin d'un fichier de certificat .pfx.
4. Connaissances de base en C# : Comprendre les bases rendra ce didacticiel plus fluide.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires. Ceux-ci sont cruciaux pour accéder aux fonctionnalités d’Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Words.DigitalSignatures;
```

Maintenant, décomposons le processus en étapes simples et gérables.

## Étape 1 : Configuration de votre projet

Tout d’abord, configurez votre projet Visual Studio. Ouvrez Visual Studio et créez une nouvelle application console C#. Nommez-le de manière descriptive, comme "SignEncryptedWordDoc".

## Étape 2 : Ajout d'Aspose.Words à votre projet

Ensuite, nous devons ajouter Aspose.Words à votre projet. Il existe plusieurs façons de procéder, mais utiliser NuGet est la plus simple. 

1. Ouvrez la console du gestionnaire de packages NuGet depuis Outils > Gestionnaire de packages NuGet > Console du gestionnaire de packages.
2. Exécutez la commande suivante :

```powershell
Install-Package Aspose.Words
```

## Étape 3 : préparation du répertoire de documents

Vous aurez besoin d'un répertoire pour stocker vos documents et certificats Word. Créons-en un.

1. Créez un répertoire sur votre ordinateur. Pour plus de simplicité, appelons-le « DocumentDirectory ».
2. Placez votre document Word (par exemple, "Document.docx") et votre certificat .pfx (par exemple, "morzal.pfx") dans ce répertoire.

## Étape 4 : Rédaction du code

 Passons maintenant au code. Ouvrez votre`Program.cs` fichier et commencez par configurer le chemin d’accès à votre répertoire de documents et initialiser le`SignOptions` avec le mot de passe de décryptage.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };
```

## Étape 5 : Chargement du certificat

 Ensuite, chargez votre certificat à l'aide du`CertificateHolder`classe. Cela nécessitera le chemin d'accès à votre fichier .pfx et le mot de passe du certificat.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Étape 6 : Signature du document

 Enfin, utilisez le`DigitalSignatureUtil.Sign` méthode pour signer votre document Word crypté. Cette méthode nécessite les options de fichier d’entrée, de fichier de sortie, de titulaire du certificat et de signature.

```csharp
DigitalSignatureUtil.Sign(
    dataDir + "Document.docx",
    dataDir + "DigitallySignedDocument.docx",
    certHolder,
    signOptions);
```

## Étape 7 : Exécuter le code

Enregistrez votre fichier et exécutez le projet. Si tout est correctement configuré, vous devriez voir votre document signé dans le répertoire spécifié.

## Conclusion

Et voila! Vous avez signé avec succès un document Word chiffré à l'aide d'Aspose.Words pour .NET. Avec cette puissante bibliothèque, la signature numérique devient un jeu d'enfant, même pour les fichiers cryptés. Bon codage !

## FAQ

### Puis-je utiliser un autre type de certificat ?
Oui, Aspose.Words prend en charge différents types de certificats, à condition qu'ils soient au format correct.

### Est-il possible de signer plusieurs documents à la fois ?
Absolument! Vous pouvez parcourir une collection de documents et signer chacun d’eux par programme.

### Que faire si j'oublie le mot de passe de décryptage ?
Malheureusement, sans le mot de passe de décryptage, vous ne pourrez pas signer le document.

### Puis-je ajouter une signature visible au document ?
Oui, Aspose.Words vous permet également d'ajouter des signatures numériques visibles.

### Existe-t-il un moyen de vérifier la signature ?
 Oui, vous pouvez utiliser le`DigitalSignatureUtil.Verify` méthode pour vérifier les signatures.