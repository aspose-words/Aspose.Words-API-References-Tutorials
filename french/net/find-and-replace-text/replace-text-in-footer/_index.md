---
title: Remplacer le texte dans le pied de page
linktitle: Remplacer le texte dans le pied de page
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à remplacer du texte dans le pied de page de documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/find-and-replace-text/replace-text-in-footer/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Remplacer le texte dans le pied de page dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet de rechercher et de remplacer un texte spécifique dans les pieds de page des documents Word.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Charger le document

Avant de commencer à utiliser le remplacement de texte dans le pied de page, nous devons charger le document dans Aspose.Words pour .NET. Ceci peut être fait en utilisant le`Document` class et en spécifiant le chemin du fichier de document :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

## Étape 2 : Accéder au pied de page

 Une fois le document chargé, nous devons accéder au pied de page pour effectuer le remplacement du texte. Dans notre exemple, nous utilisons le`HeadersFooters` propriété de la première section du document pour obtenir la collection d'en-têtes/pieds de page. Ensuite, nous sélectionnons le pied de page principal à l'aide de la`HeaderFooterType.FooterPrimary` indice:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

## Étape 3 : Configurer les options de recherche et de remplacement

 Nous allons maintenant configurer les options de recherche et de remplacement à l'aide d'un`FindReplaceOptions` objet. Dans notre exemple, nous posons`MatchCase` pour`false` pour ignorer la casse lors de la recherche, et`FindWholeWordsOnly` pour`false` pour permettre la recherche et le remplacement de parties de mots :

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

## Étape 4 : Remplacer le texte dans le pied de page

 Nous utilisons le`Range.Replace` méthode pour effectuer un remplacement de texte dans le pied de page. Dans notre exemple, nous remplaçons la phrase "(C) 2006 Aspose Pty Ltd." par "Copyright (C) 2020 par Aspose Pty Ltd." :

```csharp
footer

.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

## Étape 5 : Enregistrer le document modifié

 Enfin, nous enregistrons le document modifié dans un répertoire spécifié à l'aide de la`Save` méthode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
```

### Exemple de code source pour Remplacer le texte dans le pied de page à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer l'utilisation du remplacement du texte de pied de page avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Footer.docx");

	HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
	HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

	FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };

	footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
            
        
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Remplacer le texte dans le pied de page d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour charger un document, accéder au pied de page, configurer les options de recherche et de remplacement, effectuer le remplacement de texte et enregistrer le document modifié.
