---
title: Créer une nouvelle ligne de signature et définir l'identifiant du fournisseur
linktitle: Créer une nouvelle ligne de signature et définir l'identifiant du fournisseur
second_title: API de traitement de documents Aspose.Words
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

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de création d'une nouvelle ligne de signature et de définition de l'ID du fournisseur dans un document Word à l'aide de Aspose.Words pour .NET. En suivant les étapes fournies, vous pouvez facilement insérer une ligne de signature avec des options personnalisées et l'associer à un fournisseur spécifique à l'aide de l'ID du fournisseur. L'ajout de lignes de signature et la personnalisation des informations du fournisseur améliorent l'authenticité et la fiabilité de vos documents. Aspose.Words pour .NET fournit une API puissante pour le traitement de mots avec des lignes de signature et des certificats numériques dans les documents Word, vous permettant d'automatiser le processus de signature et d'assurer la validité de vos documents.

### FAQ

#### Q : Qu'est-ce qu'un ID de fournisseur dans une ligne de signature ?

R : Un ID de fournisseur dans une ligne de signature est un identifiant unique qui représente le fournisseur de la signature numérique. Il permet d'identifier la source ou l'organisation responsable de la signature.

#### Q : Comment puis-je créer une nouvelle ligne de signature dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour créer une nouvelle ligne de signature dans un document Word à l'aide d'Aspose.Words pour .NET, vous pouvez suivre ces étapes :
1.  Créer une instance de`Document` classe et une`DocumentBuilder` objet.
2.  Créer une instance de`SignatureLineOptions` class et définissez les options de ligne de signature souhaitées.
3.  Utilisez le`InsertSignatureLine` méthode de la`DocumentBuilder` objet pour insérer la ligne de signature dans le document.

#### Q : Puis-je personnaliser les options de la ligne de signature, telles que le nom du signataire, le titre et les instructions ?

 R : Oui, vous pouvez personnaliser les options de la ligne de signature. Le`SignatureLineOptions` La classe fournit des propriétés pour définir les options souhaitées, telles que`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, etc. Vous pouvez modifier ces propriétés avant d'insérer la ligne de signature.

#### Q : À quoi sert la définition de l'ID de fournisseur pour une ligne de signature ?

R : La définition de l'ID de fournisseur pour une ligne de signature permet d'identifier la source ou l'organisation responsable de la signature numérique. Il vous permet d'associer la signature à un fournisseur ou à une entité spécifique, en fournissant des informations supplémentaires sur l'origine et la fiabilité de la signature.

#### Q : Comment puis-je définir l'ID du fournisseur pour une ligne de signature à l'aide d'Aspose.Words pour .NET ?

R : Pour définir l'ID du fournisseur pour une ligne de signature à l'aide d'Aspose.Words pour .NET, vous pouvez suivre ces étapes :
1.  Après avoir inséré la ligne de signature, accédez à la`ProviderId` propriété de la`SignatureLine` objet.
2.  Met le`ProviderId` propriété à la valeur d'ID de fournisseur souhaitée à l'aide de la`Guid` Type de données.

#### Q : Puis-je signer le document après avoir créé une nouvelle ligne de signature et défini l'ID du fournisseur ?

 R : Oui, après avoir créé une nouvelle ligne de signature et défini l'ID du fournisseur, vous pouvez signer le document. Pour signer le document, vous devez définir les options de signature, y compris l'ID de la ligne de signature, l'ID du fournisseur, les commentaires et l'heure de signature. Ensuite, utilisez le`DigitalSignatureUtil.Sign` méthode pour signer le document à l'aide d'un certificat numérique.

#### Q : Puis-je spécifier un ID de fournisseur spécifique pour chaque ligne de signature dans un document Word ?

R : Oui, vous pouvez spécifier un ID de fournisseur spécifique pour chaque ligne de signature dans un document Word. Après avoir inséré chaque ligne de signature, vous pouvez définir l'ID du fournisseur pour cette ligne de signature particulière en accédant au`ProviderId` propriété du respectif`SignatureLine` objet.

#### Q : Comment puis-je enregistrer le document modifié après avoir créé une nouvelle ligne de signature et défini l'ID du fournisseur ?

 R : Pour enregistrer le document modifié après avoir créé une nouvelle ligne de signature et défini l'ID du fournisseur, vous pouvez utiliser le`Save` méthode de la`Document` objet. Spécifiez le chemin d'accès et le nom de fichier corrects pour enregistrer le document.

#### Q : Quel format de fichier Aspose.Words pour .NET prend-il en charge pour créer et signer des lignes de signature ?

R : Aspose.Words pour .NET prend en charge la création et la signature de lignes de signature au format de fichier DOCX. Vous pouvez créer et signer des lignes de signature dans des fichiers DOCX à l'aide des méthodes et classes fournies.

#### Q : Puis-je modifier l'identifiant du fournisseur ou d'autres options d'une ligne de signature une fois qu'elle a été signée ?

R : Une fois qu'une ligne de signature a été signée, elle fait partie du contenu du document et ne peut pas être modifiée séparément. Toute modification de la ligne de signature, telle que la modification de l'ID du fournisseur ou d'autres options, nécessiterait la suppression de la signature existante et la création d'une nouvelle ligne de signature.