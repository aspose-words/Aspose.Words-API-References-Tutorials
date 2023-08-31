---
title: Modifier la source de la culture de mise à jour du champ
linktitle: Modifier la source de la culture de mise à jour du champ
second_title: API de traitement de documents Aspose.Words
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

### FAQ

#### Q : Comment puis-je modifier la source de culture de mise à jour de champ dans Aspose.Words pour .NET ?

 R : Pour modifier la source de culture de mise à jour de champ dans Aspose.Words pour .NET, vous pouvez utiliser le`Document.FieldOptions.CultureSource` propriété et définissez sa valeur sur`FieldCultureSource.FieldCode` ou`FieldCultureSource.CurrentThread` . Par exemple, vous pouvez utiliser`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` pour utiliser la culture définie dans le code de champ.

#### Q : Comment puis-je spécifier une culture spécifique pour la mise à jour des champs dans Aspose.Words pour .NET ?

 : Pour spécifier une culture spécifique pour la mise à jour des champs dans Aspose.Words pour .NET, vous pouvez utiliser le`Document.FieldOptions.FieldUpdateCultureInfo` propriété et définissez la`CultureInfo` objet correspondant à la culture recherchée. Par exemple, vous pouvez utiliser`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` pour préciser la culture française (France).

#### Q : Est-il possible de désactiver la mise à jour automatique des champs dans Aspose.Words pour .NET ?

 R : Oui, il est possible de désactiver la mise à jour automatique des champs dans Aspose.Words pour .NET. Vous pouvez utiliser le`Document.FieldOptions.UpdateFields` propriété et définissez-la sur`false` pour empêcher la mise à jour automatique des champs. Cela vous permet de contrôler manuellement la mise à jour des champs selon vos besoins.

#### Q : Comment puis-je mettre à jour manuellement les champs de document dans Aspose.Words pour .NET ?

 R : Pour mettre à jour manuellement les champs d'un document dans Aspose.Words pour .NET, vous pouvez utiliser le`Field.Update` méthode pour chaque champ individuellement. Par exemple, vous pouvez utiliser`field.Update()` pour mettre à jour le champ spécifique.