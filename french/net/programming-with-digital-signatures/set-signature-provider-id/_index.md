---
title: Définir l'ID du fournisseur de signature
linktitle: Définir l'ID du fournisseur de signature
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment définir l'ID du fournisseur de signature dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/set-signature-provider-id/
---

Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour utiliser la fonctionnalité Définir l'ID du fournisseur de signature avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de spécifier l'ID du fournisseur de signature pour une ligne de signature dans un document Word. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document et accès à la ligne de signature

Commencez par télécharger le document contenant la ligne de signature :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Étape 2 : Définition des options de signature

Créez une instance de la classe SignOptions et définissez les options de signature, y compris l'ID du fournisseur :

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Étape 3 : signature du document

Pour signer le document, vous devez utiliser la classe DigitalSignatureUtil et spécifier le certificat de signature :

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Assurez-vous de spécifier les chemins d'accès corrects pour le document, le certificat et le document signé.

### Exemple de code source pour Set Signature Provider Id à l'aide de Aspose.Words pour .NET

Voici le code source complet pour définir l'ID du fournisseur de signature avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Terminez l'ID du fournisseur de signature dans votre document Word avec Aspose.Words pour .NET.

