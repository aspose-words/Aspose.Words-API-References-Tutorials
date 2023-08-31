---
title: Insérer un document lors du remplacement
linktitle: Insérer un document lors du remplacement
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un document lors du remplacement à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/clone-and-combine-documents/insert-document-at-replace/
---
Dans ce didacticiel, nous vous expliquerons comment insérer un document dans un autre document lors du remplacement à l'aide de la fonctionnalité Insérer un document lors du remplacement d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et effectuer l'insertion du document.

## Étape 1 : Chargement du document principal

Pour commencer, spécifiez le répertoire de vos documents et chargez le document principal dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Étape 2 : Configurer les options de recherche et de remplacement

Nous allons maintenant configurer les options de recherche et de remplacement en spécifiant le sens de recherche et le rappel de remplacement pour insérer un document dans un autre document. Voici comment:

```csharp
// Configurez les options de recherche et de remplacement.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Étape 3 : Appel de la méthode de remplacement

Nous allons maintenant appeler la méthode replace pour rechercher et remplacer le texte spécifié par une chaîne vide, en utilisant les options configurées. Voici comment:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Exemple de code source pour Insérer un document lors du remplacement à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Insérer un document lors du remplacement d'Aspose.Words pour .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Définissez les options de recherche et de remplacement.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Appelez la méthode de remplacement.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Conclusion

Dans ce didacticiel, nous avons exploré comment insérer un document dans un autre document lors du remplacement à l'aide de la fonctionnalité Insérer un document lors du remplacement d'Aspose.Words pour .NET. En configurant les options de recherche et de remplacement et en fournissant les données nécessaires, vous pouvez assembler dynamiquement des documents en remplaçant des espaces réservés spécifiques par le contenu d'autres modèles ou sections de document. Aspose.Words for .NET offre un moyen puissant et flexible de gérer des tâches complexes de manipulation de documents, ce qui en fait un outil précieux pour automatiser la création de documents et les scénarios d'insertion de contenu.

### FAQ

#### Q : A quoi sert l'insertion d'un document dans un autre document lors du remplacement ?

R : L'insertion d'un document dans un autre document lors du remplacement vous permet de remplacer dynamiquement un espace réservé spécifique par le contenu d'un document distinct. Cette fonctionnalité est particulièrement utile lorsque vous souhaitez assembler un document plus volumineux en combinant divers modèles ou sections de document prédéfinis dans des espaces réservés spécifiques.

#### Q : Comment insérer un document dans un autre document lors d'un remplacement à l'aide d'Aspose.Words for .NET ?

R : Pour insérer un document dans un autre document lors du remplacement à l'aide d'Aspose.Words for .NET, procédez comme suit :
1. Chargez le document principal contenant les espaces réservés dans un objet Document.
2. Configurez les options de recherche et de remplacement, y compris le sens de recherche et le rappel de remplacement pour gérer l'insertion du document.
3. Appelez la méthode de remplacement avec le modèle de recherche approprié, en remplaçant les espaces réservés par une chaîne vide, à l'aide des options configurées.

#### Q : Puis-je personnaliser le comportement d'insertion lors du remplacement ?

R : Oui, vous pouvez personnaliser le comportement d'insertion lors du remplacement en implémentant un ReplacingCallback personnalisé. En héritant de l'interface IReplacingCallback, vous pouvez contrôler la manière dont les documents sont insérés et fusionnés en fonction de vos besoins spécifiques lors du remplacement des espaces réservés.

#### Q : Puis-je remplacer plusieurs espaces réservés par différents documents ?

R : Oui, vous pouvez remplacer plusieurs espaces réservés par différents documents en spécifiant les modèles de recherche appropriés pour chaque espace réservé et en fournissant les documents correspondants à insérer.