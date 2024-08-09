---
title: Ajouter une signature numérique au PDF à l'aide du titulaire du certificat
linktitle: Ajouter une signature numérique au PDF à l'aide du titulaire du certificat
second_title: API de traitement de documents Aspose.Words
description: Sécurisez vos fichiers PDF avec une signature numérique à l'aide d'Aspose.Words for .NET. Suivez ce guide étape par étape pour ajouter une signature numérique à vos PDF sans effort.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---
## Introduction

Vous êtes-vous déjà demandé comment sécuriser vos documents PDF avec une signature numérique ? Eh bien, vous êtes au bon endroit ! Les signatures numériques sont l'équivalent moderne des signatures manuscrites, offrant un moyen de vérifier l'authenticité et l'intégrité des documents numériques. Dans ce didacticiel, nous allons vous montrer comment ajouter une signature numérique à un PDF à l'aide d'Aspose.Words for .NET. Nous couvrirons tout, de la configuration de votre environnement à l'exécution du code étape par étape. À la fin de ce guide, vous disposerez d’un PDF signé numériquement, sécurisé et fiable.

## Conditions préalables

Avant de commencer, vous aurez besoin de quelques éléments :

1.  Aspose.Words pour .NET : assurez-vous que Aspose.Words pour .NET est installé. Vous pouvez le télécharger depuis le[Site Aspose](https://releases.aspose.com/words/net/).
2. Un fichier de certificat : vous aurez besoin d'un fichier de certificat .pfx pour signer le PDF. Si vous n'en avez pas, vous pouvez créer un certificat auto-signé à des fins de test.
3. Visual Studio : ce didacticiel suppose que vous utilisez Visual Studio comme environnement de développement.
4. Connaissance de base de C# : Une connaissance de la programmation C# et .NET est essentielle.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires. Ceux-ci sont essentiels pour accéder aux classes et méthodes nécessaires à la manipulation de documents et aux signatures numériques.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System;
```

Décomposons le processus en étapes simples et gérables.

## Étape 1 : Configurez votre projet

Créez un nouveau projet C# dans Visual Studio. Ajoutez une référence à Aspose.Words pour .NET. Vous pouvez le faire via NuGet Package Manager en recherchant « Aspose.Words » et en l’installant.

## Étape 2 : charger ou créer un document

Vous aurez besoin d'un document à signer. Vous pouvez soit charger un document existant, soit en créer un nouveau. Pour ce didacticiel, nous allons créer un nouveau document et ajouter un exemple de texte.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ajoutez du texte au document.
builder.Writeln("Test Signed PDF.");
```

## Étape 3 : Spécifiez les détails de la signature numérique

Il est maintenant temps de configurer les détails de la signature numérique. Vous devrez spécifier le chemin d'accès à votre fichier de certificat .pfx, la raison de la signature, l'emplacement et la date de signature.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    DigitalSignatureDetails = new PdfDigitalSignatureDetails(
        CertificateHolder.Create(dataDir + "morzal.pfx", "your_password"), "reason", "location",
        DateTime.Now)
};
```

 Remplacer`"your_password"` avec le mot de passe de votre fichier .pfx.

## Étape 4 : Enregistrez le document au format PDF signé numériquement

Enfin, enregistrez le document au format PDF avec la signature numérique.

```csharp
doc.Save(dataDir + "DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Et c'est tout ! Votre document est maintenant signé et enregistré au format PDF.

## Conclusion

Les signatures numériques sont un outil puissant pour garantir l'intégrité et l'authenticité de vos documents. Avec Aspose.Words pour .NET, l'ajout d'une signature numérique à vos fichiers PDF est simple et efficace. En suivant ce guide étape par étape, vous pouvez sécuriser vos documents PDF et offrir une tranquillité d'esprit aux destinataires quant à leur authenticité. Bon codage !

## FAQ

### Qu'est-ce qu'une signature numérique ?
Une signature numérique est une forme électronique de signature qui vérifie l'authenticité et l'intégrité d'un document numérique.

### Ai-je besoin d’un certificat pour ajouter une signature numérique ?
Oui, vous aurez besoin d'un fichier de certificat .pfx pour ajouter une signature numérique à votre PDF.

### Puis-je créer un certificat auto-signé pour les tests ?
Oui, vous pouvez créer un certificat auto-signé à des fins de test. Cependant, pour une utilisation en production, il est recommandé d'obtenir un certificat auprès d'une autorité de certification de confiance.

### Aspose.Words pour .NET est-il gratuit ?
 Aspose.Words for .NET est un produit commercial, mais vous pouvez télécharger un essai gratuit à partir du[Site Aspose](https://releases.aspose.com/).

### Puis-je utiliser Aspose.Words for .NET pour signer d’autres types de documents ?
Oui, Aspose.Words for .NET peut être utilisé pour signer différents types de documents, pas seulement des PDF.