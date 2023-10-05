---
title: Charger un PDF crypté
linktitle: Charger un PDF crypté
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour charger un PDF crypté à l'aide d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

Lors du traitement de texte avec des documents PDF dans votre application .NET, il peut être nécessaire de charger des fichiers PDF protégés par mot de passe. Aspose.Words for .NET est une bibliothèque puissante qui fournit des fonctionnalités permettant de charger des documents PDF cryptés. Dans cet article, nous vous guiderons étape par étape pour comprendre et utiliser cette fonctionnalité.

## Comprendre la fonctionnalité Charger un PDF crypté

La fonctionnalité Charger un PDF crypté d'Aspose.Words for .NET vous permet de charger des fichiers PDF protégés par mot de passe. Vous pouvez spécifier le mot de passe lors du chargement du document afin de pouvoir accéder à son contenu et le manipuler selon vos besoins.

## Étape 1 : Chargement du document PDF crypté

La première étape consiste à charger le document PDF crypté dans votre application. Voici comment procéder :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Assurez-vous de spécifier le chemin correct vers le fichier PDF crypté dans le`dataDir` variable.

## Étape 2 : Cryptage du document PDF

 Si vous souhaitez également crypter votre document PDF, vous pouvez le faire en utilisant le`PdfSaveOptions` classe et en spécifiant les détails de chiffrement :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Cela créera une version cryptée du document PDF dans le répertoire spécifié.

## Étape 3 : Enregistrement du document PDF crypté

Après avoir téléchargé et éventuellement crypté le document PDF, vous pouvez l'enregistrer dans un autre format ou le traiter davantage en fonction de vos besoins spécifiques.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Étape 5 : Chargement du document PDF crypté avec mot de passe

Entretien

Cependant, si vous souhaitez charger le document PDF crypté avec un mot de passe, vous devez utiliser le`PdfLoadOptions` classe et précisez le mot de passe lors du chargement du document :

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Assurez-vous de fournir le mot de passe correct dans le`Password` variable.

### Exemple de code source pour charger un PDF crypté à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Conclusion

Dans cet article, nous avons exploré comment utiliser la fonctionnalité Charger un PDF crypté d'Aspose.Words pour .NET. Vous avez appris comment télécharger des fichiers PDF cryptés, comment crypter un document PDF, comment télécharger un PDF crypté avec un mot de passe et comment générer une sortie au format Markdown. Cette fonctionnalité est extrêmement utile lors du traitement de texte avec des documents PDF sécurisés.


