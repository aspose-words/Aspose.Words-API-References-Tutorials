---
title: Signature d'un document crypté
linktitle: Signature d'un document crypté
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à signer numériquement un document crypté avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/signing-encrypted-document/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes pour utiliser la fonctionnalité de signature d'un document chiffré avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de signer numériquement un document Word chiffré à l'aide d'un mot de passe de déchiffrement. Suivez les étapes ci-dessous :

## Étape 1 : Définition des options de signature

Créez une instance de la classe SignOptions et définissez le mot de passe de déchiffrement :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Assurez-vous de spécifier le mot de passe de décryptage correct pour votre document crypté.

## Étape 2 : Chargement du certificat

Commencez par charger le certificat de signature à l'aide de la classe CertificateHolder :

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assurez-vous de spécifier le chemin correct vers votre certificat et le mot de passe associé.

## Étape 3 : Signature du document crypté

Utilisez la classe DigitalSignatureUtil pour signer le document chiffré :

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Assurez-vous de spécifier les chemins d'accès corrects pour le document chiffré, le document signé et le certificat.

### Exemple de code source pour la signature d'un document crypté à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour signer un document chiffré avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
En suivant ces étapes, vous pouvez facilement signer un document Word chiffré avec Aspose.Words pour .NET.

