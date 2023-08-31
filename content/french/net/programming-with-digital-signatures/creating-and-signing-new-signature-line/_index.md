---
title: Créer et signer une nouvelle ligne de signature
linktitle: Créer et signer une nouvelle ligne de signature
second_title: API de traitement de documents Aspose.Words
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

Voici le code source complet pour créer et signer une nouvelle ligne de signature avec Aspose.Words pour .NET :

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

## Conclusion

Dans ce didacticiel, nous avons appris à créer et à signer une nouvelle ligne de signature dans un document Word à l'aide de Aspose.Words pour .NET. En suivant les étapes fournies, vous pouvez facilement insérer une ligne de signature dans votre document, personnaliser ses options et signer le document à l'aide d'un certificat numérique. L'ajout de lignes de signature et de signatures numériques à vos documents améliore leur authenticité et leur intégrité, les rendant plus sûrs et dignes de confiance. Aspose.Words pour .NET fournit une API puissante pour le traitement de mots avec des signatures et des certificats numériques dans les documents Word, vous permettant d'automatiser le processus de signature et d'assurer la validité de vos documents.

### FAQ

#### Q : Qu'est-ce qu'une ligne de signature dans un document Word ?

R : Une ligne de signature dans un document Word est un espace réservé qui indique où une signature doit être placée. Il comprend généralement le nom, le titre et la date, et offre un espace pour une signature manuscrite ou numérique.

#### Q : Comment puis-je créer une ligne de signature dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour créer une ligne de signature dans un document Word à l'aide d'Aspose.Words pour .NET, vous pouvez suivre ces étapes :
1.  Créer une instance de`Document` classe et une`DocumentBuilder` objet.
2.  Utilisez le`InsertSignatureLine` méthode de la`DocumentBuilder` objet pour insérer une nouvelle ligne de signature dans le document.
3. Enregistrez le document modifié.

#### Q : Puis-je personnaliser les options de la ligne de signature, telles que le nom, le titre et la date ?

 R : Oui, vous pouvez personnaliser les options de ligne de signature. Le`SignatureLineOptions` La classe fournit des propriétés pour définir les options souhaitées, telles que`Signer`, `SignerTitle`, `ShowDate`, etc. Vous pouvez modifier ces propriétés avant d'insérer la ligne de signature.

#### Q : Comment puis-je signer le document après avoir créé une ligne de signature ?

 R : Pour signer le document après avoir créé une ligne de signature, vous devez définir les options de signature et utiliser le`DigitalSignatureUtil` classe. Voici les étapes :
1.  Met le`SignatureLineId` propriété dans le`SignOptions` objet à l'ID de la ligne de signature.
2.  Met le`SignatureLineImage` propriété dans le`SignOptions` objet à l'image de la signature que vous souhaitez utiliser.
3.  Chargez le certificat de signature à l'aide de la`CertificateHolder` classe.
4.  Utilisez le`DigitalSignatureUtil.Sign` méthode pour signer le document, en fournissant les paramètres nécessaires.

#### Q : Puis-je utiliser une image de signature numérique pour signer le document ?

 R : Oui, vous pouvez utiliser une image de signature numérique pour signer le document. Pour ce faire, vous devez fournir le fichier image dans le`SignOptions` objet à l'aide de`SignatureLineImage`propriété. L'image peut être dans n'importe quel format d'image pris en charge, tel que JPEG, PNG ou EMF.

#### Q : À quoi sert la création et la signature d'une nouvelle ligne de signature dans un document Word ?

R : La création et la signature d'une nouvelle ligne de signature dans un document Word à l'aide d'Aspose.Words pour .NET vous permet d'ajouter un espace réservé pour une signature, puis de signer le document à l'aide d'un certificat numérique. Ce processus garantit l'authenticité et l'intégrité du document, fournissant la preuve de l'approbation ou de l'accord.

#### Q : Puis-je créer et signer plusieurs lignes de signature dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Oui, vous pouvez créer et signer plusieurs lignes de signature dans un document Word à l'aide d'Aspose.Words pour .NET. Chaque ligne de signature peut avoir son propre identifiant unique et ses propres options. Vous pouvez répéter les étapes pour créer et signer des lignes de signature supplémentaires dans le document.

#### Q : Puis-je modifier la ligne de signature ou ajouter des informations supplémentaires après la signature ?

R : Une fois qu'une ligne de signature a été signée, elle fait partie du contenu du document et ne peut pas être modifiée séparément. Cependant, vous pouvez ajouter des informations ou du contenu supplémentaires après la ligne de signature signée.

#### Q : Puis-je vérifier la signature numérique d'un document contenant une ligne de signature ?

 R : Oui, Aspose.Words pour .NET fournit une fonctionnalité permettant de vérifier la signature numérique d'un document contenant une ligne de signature. Vous pouvez utiliser le`DigitalSignatureUtil.Verify` méthode de vérification de la validité et de l'authenticité de la signature numérique.

#### Q : Quel format de fichier Aspose.Words pour .NET prend-il en charge pour créer et signer des lignes de signature ?

R : Aspose.Words pour .NET prend en charge la création et la signature de lignes de signature au format de fichier DOCX. Vous pouvez créer et signer des lignes de signature dans des fichiers DOCX à l'aide des méthodes et classes fournies.