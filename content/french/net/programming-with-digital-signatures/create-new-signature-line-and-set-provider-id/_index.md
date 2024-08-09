---
title: Créer une nouvelle ligne de signature et définir l'identifiant du fournisseur
linktitle: Créer une nouvelle ligne de signature et définir l'identifiant du fournisseur
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer une nouvelle ligne de signature et définir l'ID du fournisseur dans les documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## Introduction

Salut les passionnés de technologie ! Vous êtes-vous déjà demandé comment ajouter une ligne de signature dans vos documents Word par programmation ? Eh bien, aujourd'hui, nous abordons exactement cela en utilisant Aspose.Words pour .NET. Ce guide vous guidera à travers chaque étape, facilitant ainsi la création d'une nouvelle ligne de signature et la définition de l'ID du fournisseur dans vos documents Word. Que vous automatisiez le traitement de documents ou cherchiez simplement à rationaliser votre flux de travail, ce didacticiel est là pour vous.

## Conditions préalables

Avant de mettre la main à la pâte, assurons-nous que nous avons tout ce dont nous avons besoin :

1.  Aspose.Words for .NET : si vous ne l'avez pas déjà fait, téléchargez-le[ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : Visual Studio ou tout autre environnement de développement C#.
3. .NET Framework : assurez-vous que .NET Framework est installé.
4. Certificat PFX : pour signer des documents, vous aurez besoin d'un certificat PFX. Vous pouvez en obtenir un auprès d’une autorité de certification de confiance.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires dans votre projet C# :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Très bien, passons aux choses sérieuses. Voici une description détaillée de chaque étape pour créer une nouvelle ligne de signature et définir l'ID du fournisseur.

## Étape 1 : Créer un nouveau document

Pour commencer, nous devons créer un nouveau document Word. Ce sera la toile de notre ligne signature.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dans cet extrait, nous initialisons un nouveau`Document` et un`DocumentBuilder` . Le`DocumentBuilder` nous aide à ajouter des éléments à notre document.

## Étape 2 : Définir les options de la ligne de signature

Ensuite, nous définissons les options de notre ligne de signature. Cela inclut le nom, le titre, l'adresse e-mail et d'autres détails du signataire.

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Ces options personnalisent la ligne de signature, la rendant claire et professionnelle.

## Étape 3 : Insérez la ligne de signature

Une fois nos options définies, nous pouvons maintenant insérer la ligne de signature dans le document.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 Ici, le`InsertSignatureLine` La méthode ajoute la ligne de signature et nous lui attribuons un identifiant de fournisseur unique.

## Étape 4 : Enregistrez le document

Après avoir inséré la ligne de signature, sauvegardons le document.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Cela enregistre votre document avec la ligne de signature nouvellement ajoutée.

## Étape 5 : Configurer les options de signature

Maintenant, nous devons configurer les options de signature du document. Cela inclut l'ID de la ligne de signature, l'ID du fournisseur, les commentaires et l'heure de signature.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Ces options garantissent que le document est signé avec les détails corrects.

## Étape 6 : Créer un titulaire de certificat

Pour signer le document, nous utiliserons un certificat PFX. Créons un titulaire de certificat pour cela.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Assurez-vous de remplacer`"morzal.pfx"` avec votre fichier de certificat actuel et`"aw"` avec le mot de passe de votre certificat.

## Étape 7 : Signez le document

Enfin, nous signons le document à l'aide de l'utilitaire de signature numérique.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Cela signe le document et l'enregistre en tant que nouveau fichier.

## Conclusion

Et voilà ! Vous avez réussi à créer une nouvelle ligne de signature et à définir l'ID du fournisseur dans un document Word à l'aide d'Aspose.Words pour .NET. Cette puissante bibliothèque facilite incroyablement la gestion et l'automatisation des tâches de traitement des documents. Essayez-le et voyez comment il peut rationaliser votre flux de travail.

## FAQ

### Puis-je personnaliser l’apparence de la ligne de signature ?
Absolument! Vous pouvez modifier diverses options dans le`SignatureLineOptions` pour répondre à vos besoins.

### Que faire si je n'ai pas de certificat PFX ?
Vous devrez en obtenir un auprès d'une autorité de certification de confiance. C’est essentiel pour signer numériquement des documents.

### Puis-je ajouter plusieurs lignes de signature à un document ?
Oui, vous pouvez ajouter autant de lignes de signature que nécessaire en répétant le processus d'insertion avec différentes options.

### Aspose.Words pour .NET est-il compatible avec .NET Core ?
Oui, Aspose.Words for .NET prend en charge .NET Core, ce qui le rend polyvalent pour différents environnements de développement.

### Dans quelle mesure les signatures numériques sont-elles sécurisées ?
Les signatures numériques créées avec Aspose.Words sont hautement sécurisées, à condition que vous utilisiez un certificat valide et fiable.