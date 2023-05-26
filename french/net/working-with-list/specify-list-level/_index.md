---
title: Spécifier le niveau de liste
linktitle: Spécifier le niveau de liste
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à spécifier le niveau de liste dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-list/specify-list-level/
---

Dans ce didacticiel pas à pas, nous allons vous montrer comment spécifier le niveau de liste dans un document Word à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas déjà fait, téléchargez et installez la bibliothèque à partir du site officiel.

## Étape 1 : Création du document et du générateur de documents

Commencez par créer un nouveau document et un générateur de documents associé :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Création et application d'une liste numérotée

Ensuite, créez une liste numérotée basée sur l'un des modèles de liste de Microsoft Word et appliquez-la au paragraphe actuel dans le générateur de documents :

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Étape 3 : Spécification du niveau de liste

 Utilisez le générateur de documents`ListLevelNumber`propriété pour spécifier le niveau de la liste et ajouter du texte au paragraphe :

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Répétez ces étapes pour spécifier les niveaux de liste et ajouter du texte à chaque niveau.

## Étape 4 : Création et application d'une liste à puces

Vous pouvez également créer et appliquer une liste à puces à l'aide de l'un des modèles de liste de Microsoft Word :

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Étape 5 : Ajouter du texte aux niveaux de la liste à puces

 Utilisez le`ListLevelNumber` à nouveau pour spécifier le niveau de la liste à puces et ajouter du texte :

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Étape 6 : arrêter la mise en forme de la liste

 Pour arrêter le formatage de la liste, définissez`null` au`List` propriété du générateur de documents :

```csharp
builder. ListFormat. List = null;
```

## Étape 7 : Enregistrer le document modifié

Enregistrez le document modifié :

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Donc ! Vous avez spécifié avec succès le niveau de liste dans un document Word à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour spécifier le niveau de la liste

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Créer une liste numérotée basée sur l'un des modèles de liste Microsoft Word
// et appliquez-le au paragraphe actuel du générateur de document.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Il y a neuf niveaux dans cette liste, essayons-les tous.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//Créer une liste à puces basée sur l'un des modèles de liste Microsoft Word
// et appliquez-le au paragraphe actuel du générateur de document.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// C'est un moyen d'arrêter le formatage de la liste.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```



