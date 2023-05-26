---
title: Signature de la ligne de signature existante
linktitle: Signature de la ligne de signature existante
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à signer une ligne de signature existante dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/signing-existing-signature-line/
---

Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour utiliser la fonctionnalité de signature d'une ligne de signature existante avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de signer numériquement une ligne de signature déjà présente dans un document Word. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document et accès à la ligne de signature

Commencez par télécharger le document contenant la ligne de signature existante :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Étape 2 : Définition des options de signature

Créez une instance de la classe SignOptions et définissez les options de signature, y compris l'ID de la ligne de signature et l'image de la ligne de signature :

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Assurez-vous de spécifier le chemin d'accès correct à l'image de la ligne de signature.

## Étape 3 : Chargement du certificat

Commencez par charger le certificat de signature à l'aide de la classe CertificateHolder :

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assurez-vous de spécifier le chemin correct vers votre certificat et le mot de passe associé.

## Étape 4 : Signer la ligne de signature existante

Utilisez la classe DigitalSignatureUtil pour signer la ligne de signature existante :

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Assurez-vous de spécifier les chemins d'accès corrects pour le document source, le document signé et le certificat.

### Exemple de code source pour la signature d'une ligne de signature existante à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour signer une ligne de signature existante avec Aspose.Words pour .NET :


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

En suivant ces étapes, vous pouvez facilement signer une ligne de signature existante dans un document Word avec Aspose.Words pour .NET.

