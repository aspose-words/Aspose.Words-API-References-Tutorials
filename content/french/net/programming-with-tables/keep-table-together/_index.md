---
title: Gardez la table ensemble
linktitle: Gardez la table ensemble
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment empêcher les tableaux de s'étendre sur plusieurs pages de documents Word à l'aide d'Aspose.Words pour .NET. Suivez notre guide pour conserver des documents professionnels et lisibles.
type: docs
weight: 10
url: /fr/net/programming-with-tables/keep-table-together/
---
## Introduction

Vous êtes-vous déjà senti frustré lorsqu'un tableau de votre document Word est divisé sur deux pages ? C'est comme si vos informations soigneusement présentées avaient soudainement décidé de faire une pause à mi-chemin ! Garder les tableaux ensemble sur une seule page est crucial pour la lisibilité et la présentation. Qu'il s'agisse d'un rapport, d'une proposition de projet ou simplement d'un document personnel, diviser les tableaux peut être assez choquant. Heureusement pour nous, Aspose.Words for .NET propose un moyen astucieux de résoudre ce problème. Dans ce didacticiel, nous passerons en revue les étapes à suivre pour garder vos tables intactes et impeccables. Allons-y !

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1.  Aspose.Words for .NET - Si vous ne l'avez pas encore installé, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/net/).
2. Un document Word avec un tableau - Nous travaillerons avec un exemple de document comportant un tableau s'étendant sur plusieurs pages.
3. Connaissance de base de C# - Ce didacticiel suppose que vous possédez une compréhension de base de la programmation C#.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires. Cela nous donnera accès aux classes et méthodes dont nous avons besoin depuis Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Décomposons le processus en étapes faciles et digestes. Nous commencerons par charger notre document et terminerons par enregistrer le document mis à jour où le tableau reste ensemble.

## Étape 1 : Charger le document

 Pour travailler avec un document Word, nous devons d'abord le charger. Nous utiliserons le`Document` classe pour ça.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Étape 2 : accéder au tableau

Ensuite, nous devons trouver la table que nous voulons garder ensemble. Nous supposerons qu'il s'agit du premier tableau du document.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Étape 3 : définissez KeepWithNext pour les paragraphes

 Pour éviter que le tableau ne s'étende sur plusieurs pages, nous devons définir le`KeepWithNext` propriété pour chaque paragraphe du tableau, à l’exception des derniers paragraphes de la dernière ligne.

```csharp
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
    cell.EnsureMinimum();
    foreach (Paragraph para in cell.Paragraphs)
    {
        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }
}
```

## Étape 4 : Enregistrez le document

Enfin, nous enregistrons le document mis à jour. Cela appliquera nos modifications et garantira que le tableau reste ensemble sur une seule page.

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Conclusion

Et voilà ! Avec seulement quelques lignes de code, vous pouvez empêcher vos tableaux de se diviser sur plusieurs pages de vos documents Word. Cette solution simple mais efficace garantit que vos tableaux restent soignés et professionnels, améliorant ainsi la lisibilité de vos documents. Aspose.Words for .NET facilite la gestion de ces problèmes de formatage, vous permettant de vous concentrer sur la création d'un contenu de qualité.

## FAQ

### Puis-je conserver plusieurs tables ensemble en utilisant cette méthode ?  
Oui, vous pouvez appliquer la même logique à plusieurs tables en parcourant chaque table de votre document.

### Que faire si mon tableau est trop grand pour tenir sur une seule page ?  
Si un tableau est trop grand pour tenir sur une seule page, il s’étendra quand même sur plusieurs pages. Cette méthode garantit que les petites tables restent intactes sans se diviser.

### Existe-t-il un moyen d'automatiser cela pour tous les tableaux d'un document ?  
 Oui, vous pouvez parcourir tous les tableaux de votre document et appliquer le`KeepWithNext` propriété à chaque paragraphe.

### Ai-je besoin d’une licence payante pour Aspose.Words pour .NET ?  
Vous pouvez commencer par un essai gratuit à partir de[ici](https://releases.aspose.com/), mais pour bénéficier de fonctionnalités complètes, une licence payante est recommandée.

### Puis-je appliquer une autre mise en forme au tableau tout en le gardant ensemble ?  
Absolument! Vous pouvez formater votre tableau selon vos besoins tout en vous assurant qu'il reste ensemble sur une seule page.