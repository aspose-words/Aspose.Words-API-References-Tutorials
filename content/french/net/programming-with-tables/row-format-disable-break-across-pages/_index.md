---
title: Format de ligne Désactiver le saut entre les pages
linktitle: Format de ligne Désactiver le saut entre les pages
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment désactiver les sauts de ligne sur les pages des documents Word à l’aide d’Aspose.Words for .NET pour maintenir la lisibilité et le formatage des tableaux.
type: docs
weight: 10
url: /fr/net/programming-with-tables/row-format-disable-break-across-pages/
---
## Introduction

Lorsque vous travaillez avec des tableaux dans des documents Word, vous souhaiterez peut-être vous assurer que les lignes ne sont pas réparties sur plusieurs pages, ce qui peut être essentiel pour maintenir la lisibilité et le formatage de vos documents. Aspose.Words for .NET fournit un moyen simple de désactiver les sauts de ligne sur les pages.

Dans ce didacticiel, nous vous guiderons tout au long du processus de désactivation des sauts de ligne sur les pages d'un document Word à l'aide d'Aspose.Words pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous de disposer des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée.
- Un document Word avec un tableau qui s'étend sur plusieurs pages.

## Importer des espaces de noms

Tout d’abord, importez les espaces de noms nécessaires dans votre projet :

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Étape 1 : Charger le document

Chargez le document contenant le tableau qui s'étend sur plusieurs pages.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Étape 2 : accéder au tableau

Accédez au premier tableau du document. Cela suppose que le tableau que vous souhaitez modifier est le premier tableau du document.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Étape 3 : Désactiver la répartition entre les pages pour toutes les lignes

 Parcourez chaque ligne du tableau et définissez le`AllowBreakAcrossPages`propriété à`false`. Cela garantit que les lignes ne seront pas réparties sur plusieurs pages.

```csharp
// Désactivez le fractionnement entre les pages pour toutes les lignes du tableau.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Étape 4 : Enregistrez le document

Enregistrez le document modifié dans votre répertoire spécifié.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusion

Dans ce didacticiel, nous avons montré comment désactiver les sauts de ligne sur les pages d'un document Word à l'aide d'Aspose.Words pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez vous assurer que les lignes de votre tableau restent intactes et ne sont pas divisées sur plusieurs pages, préservant ainsi la lisibilité et le formatage du document.

## FAQ

### Puis-je désactiver les sauts de ligne sur les pages pour une ligne spécifique au lieu de toutes les lignes ?  
 Oui, vous pouvez désactiver les sauts de ligne pour des lignes spécifiques en accédant à la ligne souhaitée et en définissant son`AllowBreakAcrossPages`propriété à`false`.

### Cette méthode fonctionne-t-elle pour les tableaux avec des cellules fusionnées ?  
 Oui, cette méthode fonctionne pour les tableaux avec des cellules fusionnées. La propriété`AllowBreakAcrossPages` s'applique à la ligne entière, quelle que soit la fusion de cellules.

### Cette méthode fonctionnera-t-elle si la table est imbriquée dans une autre table ?  
Oui, vous pouvez accéder et modifier les tables imbriquées de la même manière. Assurez-vous de référencer correctement la table imbriquée par son index ou d'autres propriétés.

### Comment puis-je vérifier si une ligne permet de parcourir plusieurs pages ?  
 Vous pouvez vérifier si une ligne permet de parcourir les pages en accédant au`AllowBreakAcrossPages` propriété du`RowFormat` et vérifier sa valeur.

### Existe-t-il un moyen d'appliquer ce paramètre à tous les tableaux d'un document ?  
Oui, vous pouvez parcourir tous les tableaux du document et appliquer ce paramètre à chacun.