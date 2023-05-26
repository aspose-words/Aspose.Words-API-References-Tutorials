---
title: Créer une nouvelle ligne de signature et définir l'identifiant du fournisseur
linktitle: Créer une nouvelle ligne de signature et définir l'identifiant du fournisseur
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer une nouvelle ligne de signature et à définir l'ID du fournisseur dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour utiliser la fonctionnalité Créer une nouvelle ligne de signature et définir l'ID du fournisseur avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'insérer une ligne de signature dans un document Word, de définir des options personnalisées et de signer le document. Suivez les étapes ci-dessous :

## Étape 1 : Création du document et du générateur

Commencez par créer une instance de la classe Document et un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Définition des options de ligne de signature

Créez une instance de la classe SignatureLineOptions et définissez les options souhaitées :

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Étape 3 : Insertion de la ligne de signature

Utilisez la méthode InsertSignatureLine() de l'objet DocumentBuilder pour insérer la ligne de signature dans le document :

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Étape 4 : Définir l'ID du fournisseur

Définissez l'ID du fournisseur pour la ligne de signature à l'aide de la propriété ProviderId :

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Assurez-vous de spécifier l'ID de fournisseur correct pour votre cas d'utilisation.

## Étape 5 : Enregistrer le document

Enregistrez le document modifié :

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour enregistrer le document.

## Étape 6 : Signature du document

Pour signer le document, vous devez définir les options de signature et utiliser la classe DigitalSignatureUtil :

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Assurez-vous de spécifier les chemins d'accès corrects pour le document, le certificat et le document signé.

### Exemple de code source pour créer une nouvelle ligne de signature et définir l'identifiant du fournisseur à l'aide de Aspose.Words pour .NET

Voici le code source complet pour créer une nouvelle ligne de signature et définir l'ID du fournisseur avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

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

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

En suivant ces étapes, vous pouvez facilement créer une nouvelle ligne de signature et définir l'ID du fournisseur dans votre document Word avec Aspose.Words pour .NET.

