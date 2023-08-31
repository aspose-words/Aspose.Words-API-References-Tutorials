---
title: Accéder et vérifier la signature dans un document Word
linktitle: Accéder et vérifier la signature dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment accéder et vérifier les signatures numériques dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-digital-signatures/access-and-verify-signature/
---
Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonctionnalité de vérification d'accès et de signature d'Aspose.Words for .NET. Cette fonctionnalité vous permet d'accéder aux signatures numériques dans un document Word et de vérifier leur validité. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document et accès aux signatures

Commencez par télécharger le document contenant les signatures numériques :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Étape 2 : Parcourir les signatures numériques

Utilisez une boucle pour parcourir toutes les signatures numériques du document :

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Accéder aux informations de signature
	Console.WriteLine("* Signature Found *");
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

Voici le code source complet pour la vérification de l'accès et de la signature à l'aide d'Aspose.Words for .NET :

```csharp
	
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Cette propriété est disponible uniquement dans les documents MS Word.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

En suivant ces étapes, vous pourrez facilement accéder et vérifier les signatures numériques de votre document Word avec Aspose.Words pour .NET.

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité d'accès et de vérification des signatures numériques dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant les étapes fournies, vous pouvez facilement charger un document, accéder à ses signatures numériques et vérifier leur validité. La possibilité d'accéder et de vérifier les signatures numériques permet de garantir l'intégrité et l'authenticité de vos documents Word. Aspose.Words for .NET propose une API puissante pour le traitement de mots avec signatures numériques, vous permettant d'automatiser le processus de vérification et d'améliorer la sécurité de vos documents.

### FAQ

#### Q : Que sont les signatures numériques dans un document Word ?

: Les signatures numériques dans un document Word sont des signatures électroniques qui permettent d'authentifier l'intégrité et l'origine du document. Ils sont créés à l'aide de certificats numériques et d'algorithmes cryptographiques, permettant aux destinataires de vérifier que le document n'a pas été altéré et qu'il provient d'une source fiable.

#### Q : Comment puis-je accéder aux signatures numériques dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour accéder aux signatures numériques dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez suivre ces étapes :
1.  Chargez le document à l'aide du`Document` classe et spécifiez le chemin d’accès au fichier de document.
2.  Utilisez une boucle pour parcourir le`DigitalSignatures` collecte du document. Chaque itération représente une signature numérique.

#### Q : À quelles informations puis-je accéder à partir d’une signature numérique dans un document Word ?

R : À partir d'une signature numérique dans un document Word, vous pouvez accéder à diverses informations, telles que :
- Validité : Vérifiez si la signature est valide.
- Commentaires : obtenez la raison de la signature spécifiée par le signataire.
- Heure de signature : obtenez l'heure à laquelle le document a été signé.
- Nom du sujet : récupérez le nom du signataire ou du sujet du certificat.
- Nom de l'émetteur : obtenez le nom de l'émetteur du certificat.

#### Q : Puis-je vérifier la validité d'une signature numérique dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Oui, vous pouvez vérifier la validité d'une signature numérique dans un document Word à l'aide d'Aspose.Words pour .NET. En accédant au`IsValid` propriété du`DigitalSignature` objet, vous pouvez déterminer si la signature est valide ou non.

#### Q : Comment puis-je vérifier la validité des signatures numériques dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour vérifier la validité des signatures numériques dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez suivre ces étapes :
1.  Accéder au`DigitalSignatures` collecte du document.
2.  Parcourez chacun`DigitalSignature` objet dans la collection.
3.  Utilisez le`IsValid` propriété du`DigitalSignature` objet pour vérifier si la signature est valide.

#### Q : Puis-je récupérer les commentaires du signataire ou la raison de sa signature à partir d'une signature numérique dans un document Word ?

 : Oui, vous pouvez récupérer les commentaires du signataire ou la raison de sa signature à partir d'une signature numérique dans un document Word. Le`Comments` propriété du`DigitalSignature` L'objet donne accès aux commentaires spécifiés par le signataire lors du processus de signature.

#### Q : Quels types de documents la fonctionnalité de vérification de signature prend-elle en charge dans Aspose.Words pour .NET ?

R : La fonctionnalité de vérification des signatures d'Aspose.Words pour .NET prend en charge la vérification des signatures numériques dans les documents Word au format de fichier DOCX. Vous pouvez utiliser cette fonctionnalité pour vérifier les signatures dans les fichiers DOCX.

#### Q : Comment puis-je accéder aux détails du certificat d'une signature numérique dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour accéder aux détails du certificat d'une signature numérique dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez accéder au`CertificateHolder` propriété du`DigitalSignature` objet. Du`CertificateHolder` objet, vous pouvez récupérer divers détails du certificat, tels que le nom du sujet et le nom de l'émetteur.

#### : Puis-je personnaliser l'affichage ou le traitement des signatures numériques dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Oui, vous pouvez personnaliser l'affichage ou le traitement des signatures numériques dans un document Word à l'aide d'Aspose.Words pour .NET. En accédant aux propriétés et méthodes du`DigitalSignature` objet, vous pouvez extraire les informations souhaitées, effectuer des validations supplémentaires ou intégrer le processus de vérification de signature dans le flux de travail de votre application.

#### Q : Est-il possible de vérifier plusieurs signatures numériques dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Oui, il est possible de vérifier plusieurs signatures numériques dans un document Word à l'aide d'Aspose.Words pour .NET. En parcourant le`DigitalSignatures` collecte du document, vous pouvez accéder et vérifier chaque signature numérique individuellement.

