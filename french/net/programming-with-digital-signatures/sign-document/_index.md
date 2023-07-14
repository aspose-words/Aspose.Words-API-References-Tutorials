---
title: Signer un document Word
linktitle: Signer un document Word
second_title: API de traitement de documents Aspose.Words
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

## Étape 2 : Signature du document

Utilisez la classe DigitalSignatureUtil pour signer le document :

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Assurez-vous de spécifier les chemins d'accès corrects pour le document source et le document signé.

### Exemple de code source pour signer un document à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour signer un document avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

En suivant ces étapes, vous pouvez facilement signer un document Word avec Aspose.Words pour .NET.

## Conclusion

 Dans ce didacticiel, nous avons exploré la fonctionnalité de signature de document dans Aspose.Words pour .NET. En chargeant un certificat de signature et en utilisant le`DigitalSignatureUtil.Sign` méthode, nous pouvons signer numériquement un document Word. La signature de document fournit une authentification et garantit l'intégrité du contenu du document, ce qui en fait une fonctionnalité précieuse pour une gestion sécurisée et fiable des documents.

### FAQ pour le document Word signé

#### Q : Qu'est-ce que la signature de document dans Aspose.Words pour .NET ?

R : La signature de document dans Aspose.Words pour .NET fait référence au processus de signature numérique d'un document Word à l'aide d'un certificat. Cette fonction ajoute une signature numérique au document, assurant l'authenticité, l'intégrité et la non-répudiation du contenu du document.

#### Q : Comment puis-je charger le certificat de signature dans Aspose.Words pour .NET ?

 R : Pour charger le certificat de signature dans Aspose.Words pour .NET, vous pouvez utiliser le`CertificateHolder` classe. Créer une instance de`CertificateHolder` en fournissant le chemin d'accès au fichier de certificat et le mot de passe associé. Voici un exemple :

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Assurez-vous de fournir le chemin correct vers votre certificat et le mot de passe associé.

#### Q : Comment signer un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour signer un document Word à l'aide d'Aspose.Words pour .NET, vous pouvez utiliser le`DigitalSignatureUtil` classe. Appeler le`Sign` méthode, fournissant le chemin d'accès au document source, le chemin d'accès au document signé (sortie) et la`CertificateHolder` objet. Voici un exemple :

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Assurez-vous de fournir les chemins d'accès corrects pour le document source et le document signé (sortie).

#### Q : À quoi sert la signature de documents ?

: La signature de document sert de méthode pour garantir l'authenticité et l'intégrité d'un document. En signant numériquement un document, vous pouvez apporter la preuve de son origine, vérifier que son contenu n'a pas été altéré et établir la non-répudiation. La signature de documents est couramment utilisée pour les documents juridiques, financiers et sensibles.

#### Q : Puis-je utiliser n'importe quel certificat pour la signature de documents dans Aspose.Words pour .NET ?

R : Pour la signature de documents dans Aspose.Words pour .NET, vous devez utiliser un certificat X.509 valide. Ce certificat peut être obtenu auprès d'une autorité de certification (CA) de confiance ou un certificat auto-signé peut être utilisé à des fins de test.

#### Q : Quel format de fichier Aspose.Words pour .NET prend-il en charge pour la signature de documents ?

 R : Aspose.Words pour .NET prend en charge la signature de documents pour les documents Word au format de fichier DOCX. Vous pouvez signer des fichiers DOCX à l'aide du`DigitalSignatureUtil` classe et le certificat approprié.

#### Q : Puis-je signer plusieurs documents Word à l'aide du même certificat ?

R : Oui, vous pouvez signer plusieurs documents Word à l'aide du même certificat. Une fois que vous avez chargé le certificat à l'aide du`CertificateHolder` classe, vous pouvez la réutiliser pour signer plusieurs documents en appelant la`DigitalSignatureUtil.Sign` méthode avec différents chemins d'accès aux documents source et signés.

#### Q : La signature de document modifie-t-elle le document d'origine ?

R : La signature de document avec Aspose.Words pour .NET ne modifie pas le document d'origine. Au lieu de cela, il crée une copie signée numériquement du document, laissant le document original intact. La copie signée numériquement contient la signature numérique ajoutée, garantissant l'intégrité du contenu du document.

#### Q : Puis-je vérifier la signature numérique d'un document signé à l'aide d'Aspose.Words pour .NET ?

 R : Oui, Aspose.Words pour .NET fournit des fonctionnalités pour vérifier la signature numérique d'un document signé. Vous pouvez utiliser le`DigitalSignatureUtil.Verify` méthode de vérification de la validité et de l'authenticité de la signature numérique.