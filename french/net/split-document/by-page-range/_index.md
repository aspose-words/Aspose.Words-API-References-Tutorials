---
title: Par plage de pages
linktitle: Par plage de pages
second_title: Référence de l'API Aspose.Words pour .NET
description: Extrayez facilement par plage de pages d'un document Word à l'aide du guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/split-document/by-page-range/
---

## Introduction
Dans ce tutoriel, nous vous guiderons pas à pas pour comprendre et utiliser la fonctionnalité "Par plage de pages" d'Aspose.Words pour .NET. Cette fonctionnalité vous permet d'extraire une partie spécifique d'un grand document Word en utilisant une plage de pages donnée. Nous vous fournirons le code source complet et les formats de sortie Markdown pour vous faciliter la compréhension et l'utilisation ultérieure.

## Exigences
Avant de commencer, assurez-vous que les éléments suivants sont en place :

1. Aspose.Words pour .NET installé sur votre machine de développement.
2. Un gros fichier Word dont vous souhaitez extraire une partie spécifique.

Maintenant que nous avons couvert les exigences, nous pouvons passer aux étapes d'utilisation de la fonctionnalité Par plage de pages.

## Étape 1 : Initialisation et chargement du document
Une fois que vous avez configuré votre environnement de développement, vous devez initialiser et charger le document Word dont vous souhaitez extraire une partie spécifique. Voici le code à utiliser :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Name_of_large_document.docx");
```

Assurez-vous de remplacer "YOUR_DOCUMENTS_DIRECTORY" par le chemin d'accès réel à votre répertoire de documents et "Name_of_large_document.docx" par le nom de votre gros fichier Word.

## Etape 2 : Extraction de la partie du document
 Maintenant que nous avons chargé le document, nous pouvons extraire la partie spécifique en utilisant le`ExtractPages` fonction avec la plage de pages souhaitée. Voici comment procéder :

```csharp
Document extractedPages = doc.ExtractPages(3, 6);
```

Dans cet exemple, nous extrayons les pages 3 à 6 du document original. Vous pouvez ajuster les numéros de page en fonction de vos besoins.

## Étape 3 : Enregistrer la pièce extraite
Une fois que nous avons extrait les pages souhaitées, nous pouvons les enregistrer dans un nouveau document Word. Voici comment:

```csharp
extractedPages.Save(dataDir + "Document_Extraits.ParRangeDePages.docx");
```

Veillez à remplacer "Document_Extraits.ParPlageDePages.docx" par le nom souhaité pour votre fichier de sortie.

### Exemple de code source pour Par plage de pages en utilisant Aspose.Words pour .NET

```csharp

            // Chemin d'accès au répertoire des documents.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(MyDir + "Big document.docx");
            
            // Obtenir une partie du document.
            Document extractedPages = doc.ExtractPages(3, 6);
            extractedPages.Save(dataDir + "SplitDocument.ByPageRange.docx");
            
        
```

## Conclusion
Félicitation ! Vous avez appris à utiliser "Par plage de pages" d'Aspose.Words pour .NET. Désormais, vous pouvez facilement extraire des parties spécifiques d'un document Word volumineux à l'aide d'une plage de pages donnée. N'hésitez pas à expérimenter davantage avec les autres fonctionnalités puissantes d'Aspose. .Des mots pour répondre à vos besoins spécifiques.

