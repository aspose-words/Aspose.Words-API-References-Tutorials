---
title: Définir la position horizontale ou verticale relative
linktitle: Définir la position horizontale ou verticale relative
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir la position relative horizontale ou verticale d'un tableau dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

Dans ce didacticiel, nous allons apprendre à définir la position relative horizontale ou verticale d'un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de définir la position relative horizontale ou verticale de votre tableau dans vos documents Word.

## Étape 1 : Configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargement du document
Pour démarrer le traitement de texte avec le document, procédez comme suit :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents et fournissez le nom de fichier correct.

## Étape 3 : Définition de la position relative de la table
Ensuite, nous définirons la position relative horizontale ou verticale du tableau. Utilisez le code suivant :

```csharp
// Récupérer le tableau
Table table = doc.FirstSection.Body.Tables[0];

//Définition de la position horizontale relative de la table
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Définir la position verticale relative de la table
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Ici, nous utilisons le document pour récupérer le premier tableau du corps de la première section. Ensuite, nous définissons la position horizontale relative de la table avec le`HorizontalAnchor` propriété en utilisant le`RelativeHorizontalPosition.Column` valeur. De même, nous définissons la position verticale relative de la table avec le`VerticalAnchor` propriété en utilisant le`RelativeVerticalPosition.Page` valeur.

## Étape 4 : Sauvegarde du document modifié
Enfin, nous devons enregistrer le document modifié avec la position relative du tableau définie. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour définir la position horizontale ou verticale relative à l'aide d'Aspose.Words pour .NET 

```csharp
//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir la position horizontale ou verticale relative d'un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez appliquer cette position relative à vos tableaux dans vos documents Word.