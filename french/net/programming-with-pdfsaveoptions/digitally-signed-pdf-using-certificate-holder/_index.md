---
title: Pdf signé numériquement à l'aide du titulaire du certificat
linktitle: Pdf signé numériquement à l'aide du titulaire du certificat
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à signer numériquement un PDF à l'aide d'un détenteur de certificat avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

Dans ce tutoriel, nous vous guiderons à travers les étapes pour créer un PDF signé numériquement à l'aide d'un certificat avec Aspose.Words pour .NET. La signature numérique ajoute une couche de sécurité et d'intégrité au document PDF. Suivez les étapes ci-dessous :

## Étape 1 : création du document et ajout de contenu

Commencez par créer une instance de la classe Document :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Ajouter du contenu au document

 Utilisez ensuite le`DocumentBuilder` pour ajouter du contenu au document. Par exemple, pour ajouter un paragraphe contenant le texte "Tester le PDF signé", utilisez la`Writeln` méthode:

```csharp
builder.Writeln("Test Signed PDF.");
```

Vous pouvez ajouter d'autres éléments de contenu si nécessaire.

## Étape 3 : Définir les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et spécifiez les détails de la signature numérique :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Assurez-vous de spécifier le chemin correct vers votre certificat et le mot de passe associé. Vous pouvez également personnaliser la raison et l'emplacement de la signature.

## Étape 4 : Enregistrer le document en tant que PDF signé numériquement

 Utilisez le`Save` méthode pour enregistrer le document au format PDF en spécifiant les options d'enregistrement :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF signé numériquement.

En suivant ces étapes, vous pouvez facilement créer un PDF signé numériquement avec un certificat en utilisant Aspose.Words pour .NET.

### Exemple de code source pour un PDF signé numériquement à l'aide d'un détenteur de certificat à l'aide d'Aspose.Words pour .NET

Voici le code source complet du Pdf signé numériquement à l'aide du titulaire du certificat d'un document utilisant Aspose.Words pour .NET :

```csharp

            // Chemin d'accès au répertoire des documents.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
