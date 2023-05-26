---
title: Modifier la source de la culture de mise à jour du champ
linktitle: Modifier la source de la culture de mise à jour du champ
second_title: Référence de l'API Aspose.Words pour .NET
description: Modifier la source de culture de mise à jour du champ, guide étape par étape pour modifier la source de culture dans Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/change-field-update-culture-source/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de modification de la source de culture de mise à jour de champ dans les documents Word à l'aide d'Aspose.Words pour .NET. En modifiant la source de culture, vous pouvez contrôler la mise en forme de la date lors des opérations de mise à jour des champs et de fusion et publipostage. Nous vous fournirons le code source C# nécessaire et des instructions étape par étape pour y parvenir.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Créer un document et DocumentBuilder
Pour commencer, créez une instance de la classe Document et un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer du contenu avec des paramètres régionaux spécifiques
Ensuite, définissez les paramètres régionaux sur l'allemand et insérez des champs avec un format de date :

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Dans le code ci-dessus, nous définissons les paramètres régionaux de la police sur l'allemand (ID de paramètres régionaux 1031) et insérons deux champs avec un formatage de date spécifique.

## Étape 3 : Modifier la source de la culture de mise à jour du champ
Pour modifier la source de la culture de mise à jour du champ, utilisez la classe FieldOptions :

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

Dans cet exemple, nous définissons la culture utilisée lors de la mise à jour du champ à choisir parmi la culture utilisée par le champ.

## Étape 4 : effectuer un publipostage
Effectuez une opération de fusion et publipostage et spécifiez la valeur de date pour le champ "Date2" :

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

Dans cet extrait de code, nous exécutons l'opération de fusion et publipostage et fournissons une valeur DateTime pour le champ "Date2".

## Étape 5 : Enregistrer le document
Enregistrez le document modifié dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Exemple de code source pour modifier la source de culture de mise à jour de champ à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour modifier la source de culture de mise à jour de champ dans les documents Word à l'aide d'Aspose.Words pour .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment modifier la source de culture de mise à jour de champ dans les documents Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais contrôler la culture utilisée pour le formatage de la date lors des opérations de mise à jour des champs et de fusion et publipostage. Personnalisez la source de culture en fonction de vos besoins pour garantir une date précise et cohérente.