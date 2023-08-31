---
title: Ne pas compresser les petits métafichiers
linktitle: Ne pas compresser les petits métafichiers
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser Aspose.Words pour .NET pour activer la fonctionnalité Ne pas compresser les petits métafichiers lors de l'enregistrement de documents.
type: docs
weight: 10
url: /fr/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

La compression des métadonnées dans un document est une fonctionnalité courante lors du traitement de texte avec des fichiers dans une application C#. Cependant, il peut être nécessaire de ne pas compresser les métadonnées des petits fichiers pour préserver leur qualité. Dans ce guide étape par étape, nous allons vous montrer comment utiliser le code source C# de Aspose.Words pour .NET pour activer la fonctionnalité "Ne pas compresser les petits métafichiers" dans les options d'enregistrement du document.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Étape 1 : Définir le répertoire de documents

La première étape consiste à définir le répertoire dans lequel vous souhaitez enregistrer le document. Vous devez spécifier le chemin d'accès complet au répertoire. Par exemple :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 2 : Insérer des sections et du texte

Ensuite, vous pouvez insérer des sections et du texte dans votre document. Utilisez la classe DocumentBuilder fournie par Aspose.Words pour créer le contenu de votre document. Voici un exemple simple :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Dans cet exemple, nous créons un nouveau document vierge, puis utilisons DocumentBuilder pour ajouter une ligne de texte.

## Étape 3 : Options de configuration

'inscription

Configurons maintenant les options de sauvegarde de notre document. Utilisez la classe DocSaveOptions pour spécifier les paramètres d'enregistrement. Par exemple :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

Dans cet exemple, nous créons un nouvel objet DocSaveOptions pour définir les options d'enregistrement.

## Étape 4 : Activer la fonctionnalité "Ne pas compresser les petits métafichiers"

 Pour activer la fonctionnalité "Ne pas compresser les petits métafichiers", vous devez définir la`Compliance` propriété de l'objet DocSaveOptions à la valeur`PdfCompliance.PdfA1a`. Voici comment:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

Cette configuration garantit que les métadonnées des petits fichiers ne sont pas compressées lors de l'enregistrement du document.

## Étape 5 : Enregistrez le document

Enfin, vous pouvez enregistrer le document à l'aide de la`Save` méthode de la classe Document. Spécifiez le chemin d'accès complet au fichier et le nom de fichier souhaité. Par exemple :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

Assurez-vous de remplacer "dataDir" par le chemin d'accès à votre répertoire de documents.

### Exemple de code source pour DocSaveOptions avec la fonctionnalité Ne pas compresser les petits métafichiers à l'aide d'Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Insérez deux sections avec du texte.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Configurez les options de sauvegarde avec la fonctionnalité "Ne pas compresser les petits métafichiers"
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// Enregistrez le document avec les options spécifiées
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser la bibliothèque Aspose.Words pour .NET pour activer la fonctionnalité "Ne pas compresser les petits métafichiers" lors de l'enregistrement d'un document. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. La préservation des métadonnées de petits fichiers non compressés peut être importante pour maintenir la qualité et l'intégrité des documents.