---
title: Signature d'une ligne de signature existante dans un document Word
linktitle: Signature d'une ligne de signature existante dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment signer une ligne de signature existante dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/signing-existing-signature-line/
---
Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonctionnalité de signature d'une ligne de signature existante avec Aspose.Words for .NET. Cette fonctionnalité permet de signer numériquement une ligne de signature déjà présente dans un document Word. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document et accès à la ligne de signature

Commencez par télécharger le document contenant la ligne de signature existante :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Étape 2 : Définition des options de signature

Créez une instance de la classe SignOptions et définissez les options de signature, y compris l'ID de ligne de signature et l'image de la ligne de signature :

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Assurez-vous de spécifier le chemin correct vers l’image de la ligne de signature.

## Étape 3 : Chargement du certificat

Commencez par charger le certificat de signature à l'aide de la classe CertificateHolder :

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assurez-vous de spécifier le chemin correct vers votre certificat et le mot de passe associé.

## Étape 4 : Signature de la ligne de signature existante

Utilisez la classe DigitalSignatureUtil pour signer la ligne de signature existante :

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Assurez-vous de spécifier les chemins corrects pour le document source, le document signé et le certificat.

### Exemple de code source pour signer une ligne de signature existante à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour signer une ligne de signature existante avec Aspose.Words for .NET :


```csharp

	// Le chemin d'accès au répertoire des documents.
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

En suivant ces étapes, vous pouvez facilement signer une ligne de signature existante dans un document Word avec Aspose.Words for .NET.

## Conclusion

Dans ce didacticiel, nous avons appris à signer une ligne de signature existante dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant les étapes fournies, vous pouvez facilement charger le document, accéder à la ligne de signature existante, définir les options de signature et signer le document. La possibilité de signer une ligne de signature existante constitue un moyen pratique d'ajouter des signatures numériques à des zones prédéfinies de vos documents Word, garantissant ainsi l'intégrité et l'authentification des documents. Aspose.Words for .NET propose une API puissante pour le traitement de mots avec signatures numériques, vous permettant de personnaliser le processus de signature et d'améliorer la sécurité de vos documents Word.

### FAQ

#### Q : Qu'est-ce qu'une ligne de signature existante dans un document Word ?

R : Une ligne de signature existante dans un document Word est une zone prédéfinie dans laquelle une signature peut être placée. Il est généralement représenté par une forme ou un objet dans le document et sert d'espace désigné permettant au signataire d'ajouter sa signature numérique.

#### Q : Comment puis-je signer une ligne de signature existante dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour signer une ligne de signature existante dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez suivre ces étapes :
1.  Chargez le document à l'aide du`Document` classe et spécifiez le chemin d’accès au fichier de document.
2.  Accédez à la ligne de signature existante à l’aide de la méthode ou de la propriété appropriée. Par exemple, vous pouvez utiliser`GetChild` méthode pour récupérer la forme de la ligne de signature.
3.  Créez une instance du`SignOptions`classe et définir le`SignatureLineId` propriété à l’ID de la ligne de signature existante.
4.  Met le`SignatureLineImage` propriété du`SignOptions` classe à l’image représentant la signature numérique.
5.  Chargez le certificat de signature à l'aide du`CertificateHolder` classe et fournissez le certificat et le mot de passe nécessaires.
6.  Utilisez le`DigitalSignatureUtil.Sign` méthode pour signer le document, en fournissant les paramètres nécessaires, y compris le`SignOptions` objet.

#### Q : Comment accéder à la ligne de signature existante dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour accéder à la ligne de signature existante dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez utiliser la méthode ou la propriété appropriée pour récupérer la forme de la ligne de signature à partir de la structure du document. Par exemple, vous pouvez utiliser le`GetChild` méthode avec les paramètres appropriés pour obtenir la forme de ligne de signature souhaitée.

#### Q : Puis-je personnaliser l’apparence de la signature numérique dans une ligne de signature existante ?

 : Oui, vous pouvez personnaliser l'apparence de la signature numérique dans une ligne de signature existante en fournissant un fichier image représentant la signature. L'image peut être un logo, une signature manuscrite ou toute autre représentation graphique de la signature. Vous pouvez définir le`SignatureLineImage` propriété du`SignOptions` classe aux octets du fichier image.

#### Q : Puis-je signer plusieurs lignes de signature existantes dans un document Word ?
 R : Oui, vous pouvez signer plusieurs lignes de signature existantes dans un document Word. Vous devez suivre les étapes pour chaque ligne de signature individuellement, en définissant le paramètre approprié.`SignatureLineId` et`SignatureLineImage` valeurs dans le`SignOptions` objet pour chaque ligne de signature.

#### Q : Quel doit être le format du fichier image pour la signature numérique dans une ligne de signature existante ?

 R : Le fichier image de la signature numérique dans une ligne de signature existante peut être dans différents formats, tels que PNG, JPEG, BMP ou GIF. Vous pouvez spécifier le chemin du fichier ou lire les octets du fichier image et l'attribuer au`SignatureLineImage` propriété du`SignOptions` classe.
