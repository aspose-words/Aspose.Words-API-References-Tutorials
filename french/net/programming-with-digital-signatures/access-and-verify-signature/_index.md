---
title: Accéder et vérifier la signature
linktitle: Accéder et vérifier la signature
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à accéder et à vérifier les signatures numériques dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/access-and-verify-signature/
---
Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonction de vérification d'accès et de signature d'Aspose.Words pour .NET. Cette fonctionnalité vous permet d'accéder aux signatures numériques dans un document Word et de vérifier leur validité. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document et accès aux signatures

Commencez par télécharger le document contenant les signatures numériques :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Étape 2 : parcourir les signatures numériques

Utilisez une boucle pour parcourir toutes les signatures numériques du document :

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Accéder aux informations sur les signatures
	Console.WriteLine("*** Signature Found ***");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Cette propriété est disponible uniquement dans les documents MS Word.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Assurez-vous de personnaliser les messages affichés en fonction de vos besoins.

### Exemple de code source pour accéder et vérifier la signature à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour la vérification d'accès et de signature à l'aide d'Aspose.Words pour .NET :

```csharp
	
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("*** Signature Found ***");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Cette propriété est disponible uniquement dans les documents MS Word.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

En suivant ces étapes, vous pourrez facilement accéder et vérifier les signatures numériques dans votre document Word avec Aspose.Words pour .NET.


