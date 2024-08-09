---
title: Exporter le champ du formulaire de saisie de texte sous forme de texte
linktitle: Exporter le champ du formulaire de saisie de texte sous forme de texte
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment exporter les champs d'un formulaire de saisie de texte sous forme de texte brut à l'aide d'Aspose.Words pour .NET avec ce guide complet étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## Introduction

Alors, vous plongez dans le monde d'Aspose.Words pour .NET ? Super choix ! Si vous cherchez à apprendre à exporter un champ de formulaire de saisie de texte sous forme de texte, vous êtes au bon endroit. Que vous débutiez ou perfectionniez vos compétences, ce guide vous guidera à travers tout ce que vous devez savoir. Commençons, d'accord ?

## Conditions préalables

Avant de plonger dans le vif du sujet, assurons-nous que vous disposez de tout ce dont vous avez besoin pour suivre le processus en douceur :

-  Aspose.Words pour .NET : téléchargez et installez la dernière version à partir de[ici](https://releases.aspose.com/words/net/).
- IDE : Visual Studio ou tout environnement de développement C#.
- Connaissances de base en C# : Compréhension de la syntaxe de base C# et des concepts de programmation orientée objet.
- Document : un exemple de document Word (`Rendering.docx`) avec des champs de formulaire de saisie de texte.

## Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires. Ce sont comme les éléments de base qui permettent à tout de fonctionner de manière transparente.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

Très bien, maintenant que nos espaces de noms sont prêts, passons à l'action !

## Étape 1 : configurer le projet

Avant d'entrer dans le code, assurons-nous que notre projet est correctement configuré.

## Création du projet

1. Ouvrez Visual Studio : commencez par ouvrir Visual Studio ou votre environnement de développement C# préféré.
2.  Créer un nouveau projet : accédez à`File > New > Project` . Sélectionner`Console App (.NET Core)` ou tout autre type de projet pertinent.
3.  Nommez votre projet : donnez à votre projet un nom significatif, quelque chose comme`AsposeWordsExportExample`.

## Ajout d'Aspose.Words

1.  Gérer les packages NuGet : cliquez avec le bouton droit sur votre projet dans l'Explorateur de solutions et sélectionnez`Manage NuGet Packages`.
2.  Recherchez Aspose.Words : dans le gestionnaire de packages NuGet, recherchez`Aspose.Words`.
3.  Installer Aspose.Words : Cliquez sur`Install` pour ajouter la bibliothèque Aspose.Words à votre projet.

## Étape 2 : Charger le document Word

Maintenant que notre projet est configuré, chargeons le document Word qui contient les champs du formulaire de saisie de texte.

1. Spécifiez le répertoire du document : définissez le chemin d'accès au répertoire dans lequel votre document est stocké.
2.  Chargez le document : utilisez le`Document` classe pour charger votre document Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : préparer le répertoire d'exportation

Avant d'exporter, assurons-nous que notre répertoire d'exportation est prêt. C'est ici que notre fichier HTML et nos images seront enregistrés.

1. Définir le répertoire d'exportation : Spécifiez le chemin où les fichiers exportés seront enregistrés.
2. Vérifiez et nettoyez le répertoire : assurez-vous que le répertoire existe et est vide.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## Étape 4 : Configurer les options d'enregistrement

C'est ici que la magie opère. Nous devons configurer nos options de sauvegarde pour exporter le champ du formulaire de saisie de texte sous forme de texte brut.

1.  Créer des options de sauvegarde : initialiser un nouveau`HtmlSaveOptions` objet.
2.  Définir l'option d'exportation du texte : configurez le`ExportTextInputFormFieldAsText`propriété à`true`.
3. Définir le dossier des images : définissez le dossier dans lequel les images seront enregistrées.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## Étape 5 : Enregistrez le document au format HTML

Enfin, enregistrons le document Word en tant que fichier HTML à l'aide de nos options d'enregistrement configurées.

1. Définir le chemin de sortie : Spécifiez le chemin où le fichier HTML sera enregistré.
2.  Enregistrez le document : utilisez le`Save` méthode du`Document`classe pour exporter le document.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## Conclusion

Et voilà ! Vous avez exporté avec succès un champ de formulaire de saisie de texte sous forme de texte brut à l'aide d'Aspose.Words pour .NET. Ce guide aurait dû vous donner une approche claire, étape par étape, pour accomplir cette tâche. N'oubliez pas que la pratique rend parfait, alors continuez à expérimenter différentes options et paramètres pour voir ce que vous pouvez faire d'autre avec Aspose.Words.

## FAQ

### Puis-je exporter d’autres types de champs de formulaire en utilisant la même méthode ?

 Oui, vous pouvez exporter d'autres types de champs de formulaire en configurant différentes propriétés du`HtmlSaveOptions` classe.

### Que faire si mon document contient des images ?

 Les images seront enregistrées dans le dossier d'images spécifié. Assurez-vous de définir le`ImagesFolder` propriété dans le`HtmlSaveOptions`.

### Ai-je besoin d’une licence pour Aspose.Words ?

 Oui, vous pouvez bénéficier d'un essai gratuit[ici](https://releases.aspose.com/) ou acheter une licence[ici](https://purchase.aspose.com/buy).

### Puis-je personnaliser le HTML exporté ?

 Absolument! Aspose.Words propose diverses options pour personnaliser la sortie HTML. Référez-vous au[documentation](https://reference.aspose.com/words/net/) pour plus de détails.

### Aspose.Words est-il compatible avec .NET Core ?

Oui, Aspose.Words est compatible avec .NET Core, .NET Framework et d'autres plates-formes .NET.
