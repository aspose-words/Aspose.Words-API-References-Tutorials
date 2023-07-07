---
title: Modifier les paramètres régionaux
linktitle: Modifier les paramètres régionaux
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment modifier les paramètres régionaux pour la mise en forme des dates et des nombres dans les documents Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/change-locale/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de modification des paramètres régionaux dans les documents Word à l'aide de Aspose.Words pour .NET. En modifiant les paramètres régionaux, vous pouvez contrôler la mise en forme des dates et des nombres lors des opérations de fusion et publipostage. Nous vous fournirons le code source C# nécessaire et des instructions étape par étape pour y parvenir.

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

## Étape 2 : Insérer un champ
Ensuite, insérez un champ de fusion dans le document à l'aide de la méthode InsertField :

```csharp
builder.InsertField("MERGEFIELD Date");
```

Dans le code ci-dessus, nous insérons un champ de fusion nommé "Date" dans le document.

## Étape 3 : Modifier les paramètres régionaux
Pour modifier les paramètres régionaux de formatage des dates et des nombres, vous pouvez modifier la culture actuelle du thread. Dans cet exemple, nous allons définir les paramètres régionaux sur l'allemand ("de-DE") :

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

Dans le code ci-dessus, nous stockons la culture actuelle, puis définissons la culture du thread actuel sur l'allemand.

## Étape 4 : effectuer un publipostage
Effectuez une opération de fusion et publipostage et indiquez la valeur de date pour le champ "Date" :

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

Dans cet extrait de code, nous exécutons l'opération de fusion et publipostage et fournissons la date actuelle comme valeur pour le champ "Date".

## Étape 5 : restaurer les paramètres régionaux d'origine
Une fois le publipostage terminé, restaurez la culture d'origine du fil :

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

Dans le code ci-dessus, nous restaurons la culture d'origine du thread.

## Étape 6 : Enregistrer le document
Enregistrez le document modifié dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Exemple de code source pour changer de paramètres régionaux à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour modifier les paramètres régionaux dans les documents Word à l'aide d'Aspose.Words pour .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment modifier les paramètres régionaux dans les documents Word à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais contrôler le formatage des dates et des nombres lors des opérations de fusion et publipostage. Personnalisez les paramètres régionaux en fonction de vos besoins pour garantir un formatage précis et cohérent dans vos documents.

### FAQ

#### Q : Aspose.Words est-il compatible avec différentes versions de Microsoft Word ?

R : Oui, Aspose.Words est compatible avec différentes versions de Microsoft Word, notamment Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 et Word 2019.

#### Q : Aspose.Words prend-il en charge les structures de champs complexes ?

R : Absolument ! Aspose.Words offre une prise en charge étendue des structures de champs complexes, y compris les champs imbriqués, les calculs et les expressions conditionnelles. Vous pouvez utiliser cette puissante API pour travailler avec n'importe quel type de structure de champ.

#### Q : Aspose.Words prend-il en charge les opérations de mise à jour des champs ?

R : Oui, Aspose.Words vous permet de mettre à jour les champs selon un calendrier. Vous pouvez facilement mettre à jour les valeurs des champs, actualiser les calculs et effectuer d'autres opérations liées aux champs à l'aide de l'API.

#### Q : Est-il possible de convertir des champs en texte brut à l'aide d'Aspose.Words ?

R : Certainement ! Aspose.Words fournit des méthodes pour convertir les champs en texte brut. Cela peut être utile lorsque vous devez extraire le contenu sans aucune mise en forme ou fonctionnalité liée aux champs.

#### Q : Est-il possible de générer des documents Word avec des champs dynamiques à l'aide d'Aspose.Words ?

R : Absolument ! Aspose.Words offre des fonctionnalités robustes pour générer des documents Word avec des champs dynamiques. Vous pouvez créer des modèles avec des champs prédéfinis et les remplir avec des données de manière dynamique, offrant une solution flexible et efficace pour la génération de documents.