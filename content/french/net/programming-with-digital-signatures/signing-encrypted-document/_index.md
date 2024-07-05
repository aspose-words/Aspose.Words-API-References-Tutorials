---
title: Signature d'un document Word crypté
linktitle: Signature d'un document Word crypté
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment signer numériquement un document Word crypté avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/signing-encrypted-document/
---
Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonctionnalité de signature d'un document Word crypté avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de signer numériquement un document Word crypté à l'aide d'un mot de passe de décryptage. Suivez les étapes ci-dessous :

## Étape 1 : Définition des options de signature

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

Assurez-vous de spécifier les chemins corrects pour le document chiffré, le document signé et le certificat.

### Exemple de code source pour la signature d'un document crypté à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour signer un document crypté avec Aspose.Words for .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
En suivant ces étapes, vous pouvez facilement signer un document Word crypté avec Aspose.Words for .NET.

## Conclusion

Dans ce didacticiel, nous avons exploré le processus de signature d'un document Word chiffré à l'aide d'Aspose.Words pour .NET. En fournissant le mot de passe de décryptage et le certificat de signature, nous pouvons ajouter une signature numérique à un document crypté. La signature de documents cryptés garantit leur authenticité et leur intégrité, offrant ainsi une couche de sécurité supplémentaire. Aspose.Words for .NET vous permet de signer des documents cryptés et de maintenir la sécurité et la fiabilité de vos fichiers Word.

### FAQ

#### Q : Qu'est-ce que la signature de documents dans Aspose.Words pour .NET ?

R : La signature de documents dans Aspose.Words pour .NET fait référence au processus de signature numérique d'un document Word pour garantir son authenticité, son intégrité et sa non-répudiation. Il s'agit d'ajouter une signature numérique au document à l'aide d'un certificat.

#### Q : Qu’est-ce qu’un document Word crypté ?

: Un document Word chiffré est un document qui a été chiffré à l'aide d'un mot de passe. Le cryptage est une mesure de sécurité qui protège le contenu du document en le brouillant et en le rendant illisible sans le bon mot de passe de décryptage.

#### Q : Comment puis-je signer un document Word crypté à l'aide d'Aspose.Words pour .NET ?

R : Pour signer un document Word crypté à l'aide d'Aspose.Words for .NET, vous devez fournir le mot de passe de décryptage ainsi que le certificat de signature. Suivez ces étapes:
1.  Définissez le mot de passe de décryptage dans le`SignOptions` objet.
2.  Chargez le certificat de signature à l'aide du`CertificateHolder` classe.
3.  Utilisez le`DigitalSignatureUtil.Sign` méthode pour signer le document crypté, en fournissant les paramètres nécessaires.

#### Q : Quel est le but de signer un document crypté ?

: La signature d'un document crypté avec Aspose.Words for .NET vous permet d'ajouter une signature numérique au document même lorsqu'il est crypté. Cela fournit une couche de sécurité supplémentaire et garantit l'authenticité et l'intégrité du contenu crypté. Il permet aux destinataires de vérifier l'origine du document et de détecter toute falsification.

#### Q : Puis-je signer un document crypté sans fournir le mot de passe de décryptage ?

R : Non, pour signer un document crypté, vous devez fournir le bon mot de passe de décryptage. Le mot de passe de décryptage est requis pour accéder et modifier le contenu crypté du document avant d'appliquer la signature numérique.

#### Q : Puis-je signer un document Word crypté à l'aide de n'importe quel certificat ?

R : Pour signer un document Word crypté à l'aide d'Aspose.Words pour .NET, vous avez besoin d'un certificat X.509 valide. Le certificat peut être obtenu auprès d'une autorité de certification (CA) de confiance ou un certificat auto-signé peut être utilisé à des fins de test.

#### Q : Puis-je signer plusieurs documents Word cryptés en utilisant le même certificat ?

 R : Oui, vous pouvez signer plusieurs documents Word cryptés en utilisant le même certificat. Une fois que vous avez chargé le certificat à l'aide du`CertificateHolder` classe, vous pouvez le réutiliser pour signer plusieurs documents cryptés.

#### Q : Puis-je vérifier la signature numérique d'un document crypté signé ?

 R : Oui, Aspose.Words for .NET fournit une fonctionnalité permettant de vérifier la signature numérique d'un document crypté signé. Vous pouvez utiliser le`DigitalSignatureUtil.Verify` méthode pour vérifier la validité et l’authenticité de la signature numérique.

#### Q : Quel format de fichier Aspose.Words for .NET prend-il en charge pour signer des documents cryptés ?

 R : Aspose.Words for .NET prend en charge la signature de documents Word cryptés au format de fichier DOCX. Vous pouvez signer des fichiers DOCX cryptés à l'aide du`DigitalSignatureUtil.Sign` méthode ainsi que le mot de passe de décryptage et le certificat nécessaires.

#### Q : Comment la signature d'un document crypté affecte-t-elle le cryptage ?

: La signature d'un document chiffré avec Aspose.Words for .NET n'affecte pas le chiffrement du document. Le cryptage reste intact et la signature numérique est ajoutée au contenu crypté. La signature numérique offre une sécurité et une vérification supplémentaires sans compromettre le cryptage appliqué au document.