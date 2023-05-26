---
title: Créer et signer une nouvelle ligne de signature
linktitle: Créer et signer une nouvelle ligne de signature
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer et à signer une nouvelle ligne de signature dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour utiliser la fonctionnalité de création et de signature d'une nouvelle ligne de signature avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'insérer une ligne de signature dans un document Word, de définir des options personnalisées et de signer le document. Suivez les étapes ci-dessous :

## Étape 1 : Création du document et du générateur

Commencez par créer une instance de la classe Document et un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insertion de la ligne de signature

Utilisez la méthode InsertSignatureLine() de l'objet DocumentBuilder pour insérer une nouvelle ligne de signature dans le document :

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Étape 3 : Enregistrez le document

Enregistrez le document modifié :

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour enregistrer le document.

## Étape 4 : Signature du document

Pour signer le document, vous devez définir les options de signature et utiliser la classe DigitalSignatureUtil :

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Assurez-vous de spécifier les chemins d'accès corrects pour le document, l'image de la ligne de signature et le document signé.

### Exemple de code source pour la création et la signature d'une nouvelle ligne de signature à l'aide de Aspose.Words pour .NET

Voici le code source complet pour créer et signer une nouvelle ligne de signature avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

En suivant ces étapes, vous pourrez facilement créer et signer une nouvelle ligne de signature dans votre document Word avec Aspose.Words pour .NET.

