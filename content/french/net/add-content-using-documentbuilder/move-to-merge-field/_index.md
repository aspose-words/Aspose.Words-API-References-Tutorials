---
title: Déplacer vers le champ de fusion dans un document Word
linktitle: Déplacer vers le champ de fusion dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment implémenter la fonctionnalité Déplacer vers le champ de fusion dans un document Word d'Aspose.Words pour .NET à l'aide d'un guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/move-to-merge-field/
---
Dans cet exemple, nous explorerons la fonctionnalité Déplacer vers le champ de fusion dans un document Word d'Aspose.Words pour .NET. Aspose.Words est une puissante bibliothèque de manipulation de documents qui permet aux développeurs de créer, modifier et convertir des documents Word par programme. La fonctionnalité Déplacer vers un champ de fusion nous permet de naviguer pour fusionner des champs dans un document et d'effectuer diverses opérations sur ceux-ci.


## Expliquer le code source étape par étape

Passons en revue le code source étape par étape pour comprendre comment utiliser la fonctionnalité Déplacer vers un champ de fusion à l'aide d'Aspose.Words pour .NET.

## Étape 1 : initialisation du document et du générateur de documents

Tout d’abord, initialisez les objets Document et DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 Insérer un champ de fusion et ajouter du texte après celui-ci

Utilisez la méthode InsertField de la classe DocumentBuilder pour insérer un champ de fusion, puis ajoutez du texte après celui-ci :

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Étape 3 : Le curseur du constructeur se trouve actuellement à la fin du document.

```csharp
Assert.Null(builder.CurrentNode);
```
## Étape 4 : Déplacer le curseur du générateur de documents vers le champ de fusion

Pour déplacer le curseur du générateur de documents vers le champ de fusion, utilisez la méthode MoveToField de la classe DocumentBuilder :

```csharp
builder.MoveToField(field, true);
```

## Ajout de texte immédiatement après le champ de fusion

Une fois que le curseur du générateur de documents se trouve à l'intérieur du champ de fusion, vous pouvez ajouter du texte immédiatement après à l'aide de la méthode Write :

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Exemple de code source pour Déplacer vers un champ de fusion à l'aide d'Aspose.Words pour .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérez un champ à l'aide de DocumentBuilder et ajoutez une séquence de texte après celui-ci.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Le curseur du constructeur se trouve actuellement à la fin du document.
Assert.Null(builder.CurrentNode);
// Nous pouvons déplacer le constructeur vers un champ comme celui-ci, en plaçant le curseur immédiatement après le champ.
builder.MoveToField(field, true);

// Notez que le curseur se trouve après le nœud FieldEnd du champ, ce qui signifie que nous ne sommes pas réellement à l’intérieur du champ.
// Si nous souhaitons déplacer le DocumentBuilder à l'intérieur d'un champ,
// nous devrons le déplacer vers le nœud FieldStart ou FieldSeparator d'un champ à l'aide de la méthode DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Conclusion

nous avons exploré la fonctionnalité Move To Merge Field d'Aspose.Words pour .NET. Nous avons appris à naviguer pour fusionner des champs dans un document à l'aide de la classe DocumentBuilder et à effectuer des opérations sur ceux-ci. Cette fonctionnalité est utile lors du traitement de texte par programmation avec fusion

### FAQ pour déplacer le champ de fusion dans un document Word

#### Q : Quel est l'objectif de la fonctionnalité Déplacer vers un champ de fusion dans Aspose.Words pour .NET ?

R : La fonctionnalité Déplacer vers un champ de fusion dans Aspose.Words pour .NET permet aux développeurs de naviguer pour fusionner des champs dans un document Word et d'effectuer diverses opérations sur ceux-ci par programme. Les champs de fusion sont des espaces réservés spéciaux utilisés dans les documents Word pour les opérations de publipostage.

#### Q : Comment puis-je insérer un champ de fusion dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Vous pouvez utiliser la méthode InsertField de la classe DocumentBuilder pour insérer un champ de fusion dans le document. Après avoir inséré le champ de fusion, vous pouvez ajouter du contenu, tel que du texte, avant ou après le champ à l'aide de la méthode Write.

#### Q : Comment déplacer le curseur du générateur de documents vers un champ de fusion spécifique ?

R : Pour déplacer le curseur du générateur de documents vers un champ de fusion spécifique, utilisez la méthode MoveToField de la classe DocumentBuilder et transmettez le champ en tant que paramètre. Cela placera le curseur immédiatement après le champ de fusion.

#### Q : Puis-je ajouter du texte dans un champ de fusion à l'aide de la fonctionnalité Déplacer vers le champ de fusion ?

R : Non, la fonctionnalité Déplacer vers le champ de fusion place le curseur du générateur de documents immédiatement après le champ de fusion. Pour ajouter du texte à l'intérieur du champ de fusion, vous pouvez utiliser la méthode DocumentBuilder.MoveTo pour déplacer le curseur vers le nœud FieldStart ou FieldSeparator du champ de fusion.

#### Q : Comment puis-je effectuer des opérations de publipostage à l'aide d'Aspose.Words pour .NET ?

R : Aspose.Words for .NET offre une prise en charge étendue des opérations de publipostage. Vous pouvez utiliser la classe MailMerge pour effectuer un publipostage à l'aide de données provenant de diverses sources telles que des tableaux, des ensembles de données ou des sources de données personnalisées.