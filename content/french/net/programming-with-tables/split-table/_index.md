---
title: Tableau divisé
linktitle: Tableau divisé
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment diviser des tableaux dans des documents Word à l'aide d'Aspose.Words pour .NET. Notre guide étape par étape rend la gestion des tables simple et efficace.
type: docs
weight: 10
url: /fr/net/programming-with-tables/split-table/
---
## Introduction

Vous êtes-vous déjà retrouvé à travailler avec un grand tableau dans un document Word et souhaiteriez-vous pouvoir le diviser en deux tableaux plus petits et plus faciles à gérer ? Eh bien, aujourd'hui, nous examinons exactement comment vous pouvez y parvenir en utilisant Aspose.Words pour .NET. Que vous ayez affaire à des tableaux de données volumineux ou à des structures de documents complexes, le fractionnement des tableaux peut contribuer à améliorer la lisibilité et l'organisation. Explorons le processus étape par étape pour diviser une table à l'aide d'Aspose.Words pour .NET.

## Conditions préalables

Avant de passer au didacticiel, assurez-vous d'avoir les éléments suivants :

1.  Bibliothèque Aspose.Words pour .NET : assurez-vous d'avoir téléchargé et installé la bibliothèque Aspose.Words pour .NET. Vous pouvez l'obtenir auprès du[Page des versions d'Aspose](https://releases.aspose.com/words/net/).
2. Environnement de développement : configurez un environnement de développement avec la prise en charge du framework .NET, tel que Visual Studio.
3. Exemple de document : préparer un document Word (`Tables.docx`) avec au moins une table pour appliquer l'opération de fractionnement.

## Importer des espaces de noms

Tout d’abord, importez les espaces de noms nécessaires dans votre projet. Cela vous permet d'accéder aux classes et méthodes fournies par Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Étape 1 : Charger le document

Commençons par charger le document contenant le tableau que vous souhaitez diviser. Assurez-vous de spécifier le chemin correct vers votre document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
```

## Étape 2 : Identifiez la table à diviser

Ensuite, identifiez et récupérez la table que vous souhaitez diviser. Dans cet exemple, nous ciblerons le premier tableau du document.

```csharp
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Étape 3 : Sélectionnez la ligne à diviser

Déterminez la ligne où vous souhaitez diviser le tableau. Ici, nous divisons le tableau à la troisième ligne (incluse).

```csharp
Row row = firstTable.Rows[2];
```

## Étape 4 : Créer un nouveau conteneur de table

Créez un nouveau conteneur de table pour contenir les lignes qui seront déplacées de la table d'origine.

```csharp
Table table = (Table)firstTable.Clone(false);
```

## Étape 5 : Insérez le nouveau conteneur de table

Insérez le nouveau conteneur de table juste après la table d'origine dans le document.

```csharp
firstTable.ParentNode.InsertAfter(table, firstTable);
```

## Étape 6 : ajouter un paragraphe tampon

Ajoutez un paragraphe tampon entre les deux tableaux pour garantir qu'ils restent séparés.

```csharp
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
```

## Étape 7 : déplacer les lignes vers la nouvelle table

Déplacez les lignes de la table d'origine vers le nouveau conteneur de table. Cette boucle continue jusqu'à ce que la ligne spécifiée (incluse) soit déplacée.

```csharp
Row currentRow;
do
{
    currentRow = firstTable.LastRow;
    table.PrependChild(currentRow);
} while (currentRow != row);
```

## Étape 8 : Enregistrez le document

Enfin, enregistrez le document modifié avec les tableaux divisés.

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Conclusion

Et voilà ! En suivant ces étapes, vous pouvez facilement diviser un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. Cette approche vous aide à gérer plus efficacement les grands tableaux, améliorant ainsi la lisibilité et l’organisation de vos documents. Essayez-le et voyez comment il simplifie votre travail avec les tableaux dans les documents Word.

## FAQ

### Puis-je diviser un tableau en plusieurs lignes ?
Oui, vous pouvez diviser un tableau sur plusieurs lignes en répétant le processus pour chaque point de partage.

### Qu'arrive-t-il au formatage du tableau d'origine ?
Le nouveau tableau hérite du formatage du tableau d'origine. Toute modification de formatage spécifique peut être appliquée au nouveau tableau selon les besoins.

### Est-il possible de fusionner à nouveau les tables ?
Oui, vous pouvez fusionner des tables en déplaçant des lignes d'une table à une autre en utilisant des méthodes similaires.

### Cette méthode fonctionne-t-elle avec des tables imbriquées ?
Oui, Aspose.Words for .NET prend également en charge les opérations sur les tables imbriquées.

### Puis-je automatiser ce processus pour plusieurs documents ?
Absolument! Vous pouvez créer un script ou une application pour automatiser le processus de fractionnement de table pour plusieurs documents.