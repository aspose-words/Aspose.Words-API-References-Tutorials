---
title: Insérer un champ de fusion à l'aide de DOM
linktitle: Insérer un champ de fusion à l'aide de DOM
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer des champs de fusion de champs personnalisés dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-merge-field-using-dom/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous qui utilise la fonctionnalité « Insérer un champ de fusion de champ » d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez préciser le répertoire de vos documents. Remplacez la valeur « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et de DocumentBuilder

Nous commençons par créer un nouveau document et initialiser un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Déplacer le curseur vers le paragraphe

 Nous utilisons le`MoveTo()` méthode du DocumentBuilder pour déplacer le curseur sur le paragraphe où nous voulons insérer le champ de fusion de champs.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Étape 4 : Insérer le champ de fusion de champs

 Nous utilisons le logiciel DocumentBuilder`InsertField()` méthode pour insérer un champ de fusion de champs dans le paragraphe.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Nous configurons ensuite les propriétés du champ de fusion de champs en spécifiant les options appropriées, telles que le nom du champ, le texte avant et après le champ et les options de formatage vertical.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ.

```csharp
field. Update();
```

### Exemple de code source pour insérer un champ de fusion de champs avec Aspose.Words for .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et le DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Déplacez le curseur sur le paragraphe.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Insérer un champ de fusion de champs.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Mettez à jour le champ.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

Dans cet exemple, nous avons créé un nouveau document, déplacé le curseur vers le paragraphe souhaité, puis inséré un champ de fusion de champs dans le document.

### FAQ

#### Q : Comment puis-je insérer un champ de fusion dans un document Word à l'aide d'Aspose.Words for .NET avec le DOM ?

R : Pour insérer un champ de fusion dans un document Word à l'aide d'Aspose.Words for .NET avec DOM, vous pouvez suivre ces étapes :

1. Accédez au paragraphe dans lequel vous souhaitez insérer le champ de fusion.
2.  Créer un`FieldMergeField` objet.
3. Définissez les propriétés du champ de fusion, telles que le nom du champ et les options de formatage.
4.  Ajoutez le champ de fusion au paragraphe à l'aide du`Paragraph.AppendChild` méthode.

#### Q : Comment puis-je spécifier les données source pour le champ de fusion dans Aspose.Words for .NET ?

R : Pour spécifier les données source du champ de fusion dans Aspose.Words for .NET, vous pouvez utiliser l'outil`FieldMergeField.FieldName` pour définir le nom du champ de fusion, qui est le nom d'un champ dans une source de données externe telle qu'un fichier CSV, une base de données, etc. Vous pouvez également utiliser la méthode`FieldMergeField.Text` méthode pour définir directement la valeur du champ de fusion.

#### Q : Puis-je personnaliser l'apparence du champ de fusion dans un document Word avec Aspose.Words pour .NET ?

 R : Oui, vous pouvez personnaliser l'apparence du champ de fusion dans un document Word avec Aspose.Words pour .NET. Vous pouvez définir les options de formatage telles que la casse, la police, la couleur, etc. en utilisant les propriétés du`FieldMergeField` objet.

#### Q : Comment puis-je vérifier si un champ de fusion a été inséré avec succès dans un document Word avec Aspose.Words pour .NET ?

 R : Pour vérifier si un champ de fusion a été inséré avec succès, vous pouvez parcourir le contenu du document et rechercher des instances de champ de fusion. Vous pouvez utiliser les méthodes et propriétés du`Document` objet pour accéder aux paragraphes, champs et autres éléments du document.

#### Q : L'insertion d'un champ de fusion à l'aide de DOM affecte-t-elle la structure du document Word avec Aspose.Words pour .NET ?

R : L'insertion d'un champ de fusion à l'aide du DOM n'affecte pas directement la structure du document Word. Cependant, il ajoute un nouvel élément field au contenu du document. Vous pouvez manipuler la structure du document en ajoutant, supprimant ou modifiant les éléments existants selon vos besoins.