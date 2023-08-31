---
title: Convertir un document Word en PDF 1.7
linktitle: Convertir un document Word en PDF 1.7
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment convertir un document Word en PDF 1.7 avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes de conversion d'un document Word en PDF 1.7 avec Aspose.Words pour .NET. La conversion en PDF 1.7 vous permet de générer des fichiers PDF conformes à la norme PDF 1.7. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin correct vers votre document.

## Étape 2 : Définir les options de conversion PDF

Créez une instance de la classe PdfSaveOptions et spécifiez la version de la norme PDF que vous souhaitez utiliser :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Cette option garantit que le fichier PDF généré est conforme à la norme PDF 1.7.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin correct pour enregistrer le PDF converti.

### Exemple de code source pour la conversion en PDF 17 à l'aide d'Aspose.Words pour .NET

Voici le code source complet à convertir en PDF 1.7 avec Aspose.Words for .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

En suivant ces étapes, vous pouvez facilement convertir en PDF 1.7 avec Aspose.Words pour .NET.


## Conclusion

Dans ce didacticiel, nous avons expliqué comment convertir un document Word en PDF 1.7 à l'aide d'Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez facilement générer des fichiers PDF conformes à la norme PDF 1.7. Assurez-vous de spécifier le chemin correct vers votre document Word et de configurer les options de conversion en PDF selon vos besoins. La conversion vers PDF 1.7 garantit une compatibilité et une lisibilité optimales sur différentes plateformes.

### Questions fréquemment posées

#### Q : Qu'est-ce que la conversion Word en PDF 1.7 ?
R : La conversion de documents Word en PDF 1.7 consiste à générer des fichiers PDF conformes à la norme PDF 1.7. Cette norme spécifie les fonctionnalités et les exigences relatives aux fichiers PDF, permettant une compatibilité et une lisibilité optimales sur différentes plates-formes.

#### Q : Comment puis-je convertir un document Word en PDF 1.7 à l'aide d'Aspose.Words pour .NET ?
R : Pour convertir un document Word en PDF 1.7 à l'aide d'Aspose.Words for .NET, suivez ces étapes :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Chargez le document Word que vous souhaitez convertir en PDF à l'aide du`Document` classe et spécifiez le chemin d’accès au document Word dans le répertoire de documents spécifié.

 Configurez la conversion en options PDF en créant une instance du`PdfSaveOptions`classe et en spécifiant la version du standard PDF que vous souhaitez utiliser à l'aide du`Compliance` propriété avec la valeur`PdfCompliance. Pdf17` pour générer un fichier PDF conforme à la norme PDF 1.7.

 Enregistrez le document au format PDF à l'aide du`Save` méthode du`Document`classe spécifiant le chemin et les options de sauvegarde.

#### Q : Quels sont les avantages de la conversion au format PDF 1.7 avec Aspose.Words pour .NET ?
R : Les avantages de la conversion au format PDF 1.7 avec Aspose.Words pour .NET sont :

Conforme PDF 1.7 : La conversion en PDF 1.7 garantit que le fichier PDF généré est conforme à PDF 1.7, garantissant ainsi la compatibilité et la lisibilité sur différentes plates-formes.

Préservation du formatage des documents : Aspose.Words for .NET garantit une conversion précise des documents Word en préservant le formatage, les images et les styles, ce qui donne un fichier PDF fidèle à l'original.