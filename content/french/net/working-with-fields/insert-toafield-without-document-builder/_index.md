---
title: Insérer un champ TOA sans Document Builder
linktitle: Insérer un champ TOA sans Document Builder
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un champ TOA sans utiliser de générateur de documents dans Aspose.Words pour .NET. Suivez notre guide étape par étape pour gérer efficacement les citations juridiques.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-toafield-without-document-builder/
---
## Introduction

Créer un champ Table des autorités (TOA) dans un document Word peut donner l'impression de reconstituer un puzzle complexe. Cependant, avec l'aide d'Aspose.Words pour .NET, le processus devient fluide et simple. Dans cet article, nous vous guiderons à travers les étapes pour insérer un champ TOA sans utiliser de générateur de documents, ce qui vous permettra de gérer facilement vos citations et références juridiques dans vos documents Word.

## Conditions préalables

Avant de plonger dans le didacticiel, couvrons les éléments essentiels dont vous aurez besoin :

-  Aspose.Words pour .NET : assurez-vous que la dernière version est installée. Vous pouvez le télécharger depuis le[Site Aspose](https://releases.aspose.com/words/net/).
- Environnement de développement : un IDE compatible .NET comme Visual Studio.
- Connaissances de base en C# : Comprendre la syntaxe et les concepts de base du C# sera utile.
- Exemple de document Word : créez ou préparez un exemple de document dans lequel vous souhaitez insérer le champ TOA.

## Importer des espaces de noms

Pour commencer, vous devrez importer les espaces de noms nécessaires depuis la bibliothèque Aspose.Words. Cette configuration garantit que vous avez accès à toutes les classes et méthodes requises pour la manipulation de documents.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Décomposons le processus en étapes simples et faciles à suivre. Nous vous guiderons à travers chaque étape, en vous expliquant ce que fait chaque morceau de code et comment il contribue à la création du champ TOA.

## Étape 1 : initialiser le document

 Tout d'abord, vous devez créer une instance de`Document` classe. Cet objet représente le document Word sur lequel vous travaillez.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

Ce code initialise un nouveau document Word. Vous pouvez considérer cela comme la création d’une toile vierge à laquelle vous ajouterez votre contenu.

## Étape 2 : Créer et configurer le champ TA

Ensuite, nous ajouterons un champ TA (Table of Authorities). Ce champ marque les entrées qui apparaîtront dans le TOA.

```csharp
Paragraph para = new Paragraph(doc);

// Nous souhaitons insérer les champs TA et TOA comme ceci :
// { TA \c 1 \l "Valeur 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

Voici une répartition :
- Paragraphe para = new Paragraph(doc); : Crée un nouveau paragraphe dans le document.
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false); : ajoute un champ TA au paragraphe. Le`FieldType.FieldTOAEntry` spécifie qu'il s'agit d'un champ d'entrée TOA.
- fieldTA.EntryCategory = "1"; : définit la catégorie d'entrée. Ceci est utile pour catégoriser différents types d’entrées.
- fieldTA.LongCitation = "Value 0"; : Spécifie le texte de citation long. C'est le texte qui apparaîtra dans le TOA.
- doc.FirstSection.Body.AppendChild(para); : ajoute le paragraphe avec le champ TA au corps du document.

## Étape 3 : ajouter le champ TOA

Maintenant, nous allons insérer le champ TOA réel qui compile toutes les entrées TA dans une table.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

Dans cette étape :
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false); : ajoute un champ TOA au paragraphe.
- fieldToa.EntryCategory = "1"; : filtre les entrées pour inclure uniquement celles marquées de la catégorie "1".

## Étape 4 : Mettre à jour le champ TOA

Après avoir inséré le champ TOA, vous devez le mettre à jour pour vous assurer qu'il reflète les dernières entrées.

```csharp
fieldToa.Update();
```

Cette commande actualise le champ TOA, garantissant que toutes les entrées marquées sont correctement affichées dans le tableau.

## Étape 5 : Enregistrez le document

Enfin, enregistrez votre document avec le champ TOA nouvellement ajouté.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 Cette ligne de code enregistre le document dans le répertoire spécifié. Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où vous souhaitez enregistrer votre fichier.

## Conclusion

Et voila! Vous avez ajouté avec succès un champ TOA à un document Word sans utiliser de générateur de documents. En suivant ces étapes, vous pouvez gérer efficacement les citations et créer des tableaux complets de références dans vos documents juridiques. Aspose.Words for .NET rend ce processus fluide et efficace, vous offrant les outils nécessaires pour gérer facilement des tâches documentaires complexes.

## FAQ

### Puis-je ajouter plusieurs champs TA avec différentes catégories ?
 Oui, vous pouvez ajouter plusieurs champs TA avec différentes catégories en définissant le`EntryCategory`propriété en conséquence.

### Comment puis-je personnaliser l’apparence du TOA ?
Vous pouvez personnaliser l'apparence du TOA en modifiant les propriétés du champ TOA, telles que le formatage des entrées et les étiquettes de catégorie.

### Est-il possible de mettre à jour automatiquement le champ TOA ?
 Bien que vous puissiez mettre à jour manuellement le champ TOA à l'aide du`Update` méthode, Aspose.Words ne prend actuellement pas en charge les mises à jour automatiques sur les modifications du document.

### Puis-je ajouter des champs TA par programmation dans des parties spécifiques du document ?
Oui, vous pouvez ajouter des champs TA à des emplacements spécifiques en les insérant dans les paragraphes ou sections souhaités.

### Comment gérer plusieurs champs TOA dans un seul document ?
 Vous pouvez gérer plusieurs champs TOA en attribuant différents`EntryCategory` valeurs et en veillant à ce que chaque champ TOA filtre les entrées en fonction de sa catégorie.