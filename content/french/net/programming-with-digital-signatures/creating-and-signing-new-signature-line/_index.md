---
title: Création et signature d'une nouvelle ligne de signature
linktitle: Création et signature d'une nouvelle ligne de signature
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer et signer numériquement une ligne de signature dans un document Word à l'aide d'Aspose.Words for .NET avec ce didacticiel étape par étape. Parfait pour l'automatisation des documents.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## Introduction

Salut! Donc, vous avez un document Word et vous devez ajouter une ligne de signature, puis le signer numériquement. Cela semble délicat ? Pas du tout! Grâce à Aspose.Words pour .NET, vous pouvez y parvenir de manière transparente avec seulement quelques lignes de code. Dans ce didacticiel, nous vous guiderons tout au long du processus, depuis la configuration de votre environnement jusqu'à l'enregistrement de votre document avec une nouvelle signature brillante. Prêt? Allons-y !

## Conditions préalables

Avant de passer au code, assurons-nous que vous disposez de tout ce dont vous avez besoin :
1.  Aspose.Words pour .NET - Vous pouvez[Télécharger les ici](https://releases.aspose.com/words/net/).
2. Un environnement de développement .NET - Visual Studio est fortement recommandé.
3. Un document à signer - Créez un simple document Word ou utilisez-en un existant.
4.  Un fichier de certificat – Ceci est nécessaire pour les signatures numériques. Vous pouvez utiliser un`.pfx` déposer.
5. Images pour la ligne de signature – Facultativement, un fichier image pour la signature.

## Importer des espaces de noms

Tout d’abord, nous devons importer les espaces de noms nécessaires. Cette étape est cruciale car elle met en place l’environnement d’utilisation des fonctionnalités d’Aspose.Words.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Étape 1 : configuration du répertoire de documents

Chaque projet a besoin d'un bon départ. Configurons le chemin d'accès à votre répertoire de documents. C'est ici que vos documents seront enregistrés et récupérés.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Création d'un nouveau document

Maintenant, créons un nouveau document Word en utilisant Aspose.Words. Ce sera notre toile où nous ajouterons la ligne de signature.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insertion de la ligne de signature

 C'est là que la magie opère. Nous insérons une ligne de signature dans notre document en utilisant le`DocumentBuilder` classe.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Étape 4 : enregistrement du document avec la ligne de signature

Une fois la ligne de signature en place, nous devons sauvegarder le document. Il s’agit d’une étape intermédiaire avant de procéder à sa signature.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Étape 5 : Configuration des options de signature

Maintenant, configurons les options de signature du document. Cela inclut la spécification de l’ID de la ligne de signature et de l’image à utiliser.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## Étape 6 : Chargement du certificat

Les signatures numériques nécessitent un certificat. Ici, nous chargeons le fichier de certificat qui servira à signer le document.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Étape 7 : Signature du document

 C'est la dernière étape. Nous utilisons le`DigitalSignatureUtil`classe pour signer le document. Le document signé est enregistré sous un nouveau nom.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## Conclusion

Et voila! Grâce à ces étapes, vous avez réussi à créer un nouveau document Word, à ajouter une ligne de signature et à le signer numériquement à l'aide d'Aspose.Words pour .NET. C'est un outil puissant qui facilite l'automatisation des documents. Qu'il s'agisse de contrats, d'accords ou de tout autre document formel, cette méthode garantit qu'ils sont signés et authentifiés en toute sécurité.

## FAQ

### Puis-je utiliser d’autres formats d’image pour la ligne de signature ?
Oui, vous pouvez utiliser différents formats d'image comme PNG, JPG, BMP, etc.

###  Est-il nécessaire d'utiliser un`.pfx` file for the certificate?
 Oui un`.pfx` Le fichier est un format courant pour stocker des informations cryptographiques, notamment des certificats et des clés privées.

### Puis-je ajouter plusieurs lignes de signature dans un seul document ?
Absolument! Vous pouvez insérer plusieurs lignes de signature en répétant l'étape d'insertion pour chaque signature.

### Que faire si je n'ai pas de certificat numérique ?
Vous devrez obtenir un certificat numérique auprès d'une autorité de certification de confiance ou en générer un à l'aide d'outils comme OpenSSL.

### Comment vérifier la signature numérique du document ?
Vous pouvez ouvrir le document signé dans Word et accéder aux détails de la signature pour vérifier l'authenticité et l'intégrité de la signature.