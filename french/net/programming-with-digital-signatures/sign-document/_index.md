---
title: Signer le document
linktitle: Signer le document
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à signer numériquement un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/sign-document/
---

Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour utiliser la fonctionnalité de signature de document avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de signer numériquement un document Word à l'aide d'un certificat. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du certificat

Commencez par charger le certificat de signature à l'aide de la classe CertificateHolder :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assurez-vous de spécifier le chemin correct vers votre certificat et le mot de passe associé.

## Étape 2 : signature du document

Utilisez la classe DigitalSignatureUtil pour signer le document :

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Assurez-vous de spécifier les chemins d'accès corrects pour le document source et le document signé.

### Exemple de code source pour signer un document à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour signer un document avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

En suivant ces étapes, vous pouvez facilement signer un document Word avec Aspose.Words pour .NET.



