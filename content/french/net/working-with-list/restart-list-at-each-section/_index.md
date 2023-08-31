---
title: Liste de redémarrage à chaque section
linktitle: Liste de redémarrage à chaque section
second_title: API de traitement de documents Aspose.Words
description: Apprenez à réinitialiser une liste numérotée pour chaque section d'un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-list/restart-list-at-each-section/
---

Dans ce didacticiel étape par étape, nous allons vous montrer comment réinitialiser une liste numérotée pour chaque section d'un document Word à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

 Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas déjà fait, téléchargez et installez la bibliothèque à partir de[Aspose.Releases] https://releases.aspose.com/words/net/.

## Étape 1 : création du document et de la liste

Tout d'abord, créez un nouveau document et ajoutez une liste numérotée par défaut :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Étape 2 : Ajouter des éléments à la liste

 Utilisez ensuite un`DocumentBuilder` pour ajouter des éléments à la liste. Vous pouvez utiliser une boucle pour ajouter plusieurs éléments à la liste :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

Dans cet exemple, nous insérons un saut de section après le 15e élément de la liste pour illustrer la renumérotation.

## Étape 3 : Enregistrer le document modifié

Enfin, enregistrez le document modifié :

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Donc ! Vous avez réinitialisé avec succès une liste numérotée pour chaque section d'un document Word à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour réinitialiser la liste à chaque section

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je redémarrer une liste à chaque section dans Aspose.Words ?

 R : Pour redémarrer une liste à chaque section dans Aspose.Words, vous devez créer une instance de la`List` classe et attribuez-lui une liste numérotée. Ensuite, vous pouvez utiliser le`List.IsRestartAtEachSection` propriété pour spécifier que la numérotation doit être redémarrée à chaque section. Vous pouvez associer cette liste à une ou plusieurs sections de votre document afin que la numérotation soit relancée correctement à chaque section.

#### Q : Puis-je personnaliser le format de numérotation des listes dans Aspose.Words ?

 R : Oui, vous pouvez personnaliser le format de numérotation des listes dans Aspose.Words. Le`List` classe offre plusieurs propriétés pour cela, telles que`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`etc. Vous pouvez utiliser ces propriétés pour définir le type de liste (numérotée, à puces, etc.), le format de numérotation (chiffres arabes, chiffres romains, lettres, etc.) et d'autres options de formatage de numérotation.

#### Q : Est-il possible d'ajouter des niveaux supplémentaires à une liste numérotée dans Aspose.Words ?

 R : Oui, il est possible d'ajouter des niveaux supplémentaires à une liste numérotée dans Aspose.Words. Le`ListLevel` La classe vous permet de définir des propriétés de formatage pour chaque niveau de la liste. Vous pouvez définir des options telles que le préfixe, le suffixe, l'alignement, le retrait, etc. Cela vous permet de créer des listes avec plusieurs niveaux de hiérarchie.