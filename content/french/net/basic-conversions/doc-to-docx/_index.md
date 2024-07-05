---
title: Convertir un document en Docx
linktitle: Convertir un document en Docx
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment convertir DOC en DOCX à l'aide d'Aspose.Words pour .NET. Guide étape par étape avec des exemples de code. Parfait pour les développeurs.
type: docs
weight: 10
url: /fr/net/basic-conversions/doc-to-docx/
---
## Introduction

Dans ce didacticiel, nous verrons comment convertir des fichiers DOC au format DOCX à l'aide d'Aspose.Words pour .NET. Aspose.Words est une puissante bibliothèque de traitement de documents qui permet aux développeurs de manipuler et de convertir des documents Word par programme.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir la configuration suivante :
- Visual Studio installé sur votre système.
-  Aspose.Words pour .NET installé. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/net/).
- Connaissance de base du langage de programmation C#.

## Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires dans votre code C# :
```csharp
using Aspose.Words;
```

Cet espace de noms donne accès à l'API Aspose.Words, vous permettant de travailler avec des documents Word dans votre application.

## Étape 1 : Chargez le fichier DOC

Commencez par charger le fichier DOC que vous souhaitez convertir :
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Chargez le fichier DOC à l'aide d'Aspose.Words
Document doc = new Document(dataDir + "Document.doc");
```

## Étape 2 : Enregistrer au format DOCX

Ensuite, enregistrez le document chargé au format DOCX :
```csharp
// Enregistrez le document au format DOCX
doc.Save(dataDir + "ConvertedDocument.docx", SaveFormat.Docx);
```

## Étape 3 : Exécutez le code

Compilez et exécutez votre application pour exécuter le processus de conversion. Assurez-vous que le fichier d'entrée "Document.doc" existe dans le répertoire spécifié.

## Étape 4 : vérifier la sortie

Vérifiez le répertoire de sortie du fichier DOCX converti nommé « ConvertedDocument.docx ». Vous avez converti avec succès un fichier DOC en DOCX à l'aide d'Aspose.Words pour .NET !

## Conclusion

La conversion de DOC en DOCX par programmation à l'aide d'Aspose.Words pour .NET est simple et efficace. Avec seulement quelques lignes de code, vous pouvez automatiser les conversions de documents, économisant ainsi du temps et des efforts. Que vous gériez des conversions par lots ou que vous intégriez le traitement de documents dans votre application, Aspose.Words offre des fonctionnalités robustes pour répondre à vos besoins.

## FAQ

### Aspose.Words peut-il convertir d’autres formats de documents ?
Oui, Aspose.Words prend en charge la conversion entre différents formats, notamment DOC, DOCX, RTF, HTML, PDF, etc.

### Où puis-je trouver la documentation Aspose.Words ?
 Vous pouvez accéder à la documentation[ici](https://reference.aspose.com/words/net/).

### Existe-t-il un essai gratuit disponible pour Aspose.Words ?
 Oui, vous pouvez bénéficier d'un essai gratuit auprès de[ici](https://releases.aspose.com/).

### Comment puis-je acheter une licence pour Aspose.Words ?
 Vous pouvez acheter une licence[ici](https://purchase.aspose.com/buy).

### Où puis-je obtenir de l’aide pour Aspose.Words ?
 Pour obtenir de l'aide, visitez Aspose.Words[forum](https://forum.aspose.com/c/words/8).
