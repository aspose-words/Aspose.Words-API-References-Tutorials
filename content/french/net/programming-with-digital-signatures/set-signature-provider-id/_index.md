---
title: Définir l'ID du fournisseur de signature dans un document Word
linktitle: Définir l'ID du fournisseur de signature dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir l’ID du fournisseur de signature dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/set-signature-provider-id/
---
Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonctionnalité Définir l'ID du fournisseur de signature avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de spécifier l'ID du fournisseur de signature pour une ligne de signature dans un document Word. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document et accès à la ligne de signature

Commencez par télécharger le document contenant la ligne de signature :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Étape 2 : Définition des options de signature

Créez une instance de la classe SignOptions et définissez les options de signature, y compris l'ID du fournisseur :

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Étape 3 : Signature du document

Pour signer le document, vous devez utiliser la classe DigitalSignatureUtil et spécifier le certificat de signature :

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Assurez-vous de spécifier les chemins corrects pour le document, le certificat et le document signé.

### Exemple de code source pour définir l'ID du fournisseur de signature à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour définir l’ID du fournisseur de signature avec Aspose.Words for .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
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

Terminez l'ID du fournisseur de signature dans votre document Word avec Aspose.Words for .NET.


## Conclusion

Dans ce didacticiel, nous avons appris à définir l'ID du fournisseur de signature pour une ligne de signature dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant les étapes fournies, vous pouvez facilement charger le document, accéder à la ligne de signature, définir l'ID du fournisseur et signer le document. La possibilité de définir l'ID du fournisseur de signature permet d'établir l'identité et la fiabilité du signataire, améliorant ainsi la sécurité et l'intégrité de vos documents Word. Aspose.Words for .NET fournit une API robuste pour le traitement de mots avec signatures numériques, vous permettant de personnaliser et de gérer facilement le processus de signature.

### FAQ pour définir l'identifiant du fournisseur de signature dans un document Word

#### Q : Qu'est-ce qu'un identifiant de fournisseur de signature dans un document Word ?

R : Un identifiant de fournisseur de signature dans un document Word est un identifiant unique qui spécifie le fournisseur d'une signature numérique. Il permet d'identifier l'entité ou l'organisation responsable de la création et de la gestion de la signature numérique.

#### Q : Comment puis-je définir l'ID du fournisseur de signature pour une ligne de signature dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour définir l'ID du fournisseur de signature pour une ligne de signature dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez suivre ces étapes :
1.  Chargez le document à l'aide du`Document` classe et spécifiez le chemin d’accès au fichier de document.
2.  Accédez à la ligne de signature à l’aide de la méthode ou de la propriété appropriée. Par exemple, vous pouvez utiliser`GetChild` méthode pour récupérer la forme de la ligne de signature.
3. Récupérez l’ID du fournisseur à partir de la ligne de signature.
4.  Créez une instance du`SignOptions`classe et définir le`ProviderId` propriété à l’ID du fournisseur récupéré.
5.  Utilisez le`DigitalSignatureUtil.Sign` méthode pour signer le document, en fournissant les paramètres nécessaires, y compris le`SignOptions` objet.

#### Q : Comment accéder à la ligne de signature dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour accéder à la ligne de signature dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez utiliser la méthode ou la propriété appropriée pour récupérer la forme de la ligne de signature à partir de la structure du document. Par exemple, vous pouvez utiliser le`GetChild` méthode avec les paramètres appropriés pour obtenir la forme de ligne de signature souhaitée.

#### Q : Puis-je définir l’ID du fournisseur de signature pour plusieurs lignes de signature dans un document Word ?

 R : Oui, vous pouvez définir l'ID du fournisseur de signature pour plusieurs lignes de signature dans un document Word. Vous pouvez parcourir la collection de lignes de signature dans le document et définir l'ID de fournisseur pour chaque ligne de signature individuellement à l'aide de l'option`SignOptions.ProviderId` propriété.

#### Q : À quoi sert l’ID du fournisseur de signature dans un document Word ?

R : L'ID du fournisseur de signature dans un document Word sert à identifier l'entité ou l'organisation responsable de la création et de la gestion de la signature numérique. Il permet d'établir l'authenticité et la fiabilité de la signature numérique en l'associant à un fournisseur spécifique.

#### Q : Quels types de certificats numériques peuvent être utilisés pour définir l’ID du fournisseur de signature dans un document Word ?

R : Vous pouvez utiliser des certificats numériques X.509 avec les informations de fournisseur appropriées pour définir l'ID du fournisseur de signature dans un document Word. Le certificat numérique doit être émis par une autorité de certification (CA) de confiance et contenir les métadonnées nécessaires pour identifier le fournisseur.