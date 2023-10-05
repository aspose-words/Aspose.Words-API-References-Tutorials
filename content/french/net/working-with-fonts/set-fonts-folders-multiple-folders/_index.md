---
title: Définir des dossiers de polices Plusieurs dossiers
linktitle: Définir des dossiers de polices Plusieurs dossiers
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour définir plusieurs dossiers de polices lors du rendu d'un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

Dans ce didacticiel, nous vous guiderons pas à pas à travers le processus de définition de plusieurs dossiers de polices lors du rendu d'un document à l'aide d'Aspose.Words for .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment spécifier plusieurs dossiers de polices à utiliser lors du rendu de vos documents à l'aide d'Aspose.Words for .NET.

## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document rendu modifié. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document à rendre
 Ensuite, vous pouvez charger le document à restituer en utilisant le`Document` classe. Assurez-vous de spécifier le chemin d'accès correct au document.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : définir les dossiers de polices
 Vous pouvez désormais définir plusieurs dossiers de polices à l'aide du`FontSettings` la classe et le`SetFontsFolders()` méthode. Vous pouvez spécifier les chemins d'accès aux dossiers de polices que vous souhaitez utiliser dans un tableau. Dans cet exemple, nous avons spécifié deux dossiers de polices : "C:\MyFonts\" et " D:\Divers\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Étape 4 : appliquer les paramètres de police
 Ensuite, vous devez appliquer les paramètres de police à votre document à l'aide du`FontSettings` propriété du`Document` classe.

```csharp
doc.FontSettings = fontSettings;
```

## Étape 5 : Enregistrez le document rendu
 Enfin, vous pouvez enregistrer le document rendu dans un fichier à l'aide de l'option`Save()` méthode du`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Exemple de code source pour définir des dossiers de polices dans plusieurs dossiers à l'aide d'Aspose.Words pour .NET 

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Notez que ce paramètre remplacera toutes les sources de polices par défaut recherchées par défaut. Désormais, seuls ces dossiers seront recherchés
// polices lors du rendu ou de l’intégration de polices. Pour ajouter une source de police supplémentaire tout en conservant les sources de polices système, utilisez à la fois FontSettings.GetFontSources et
// FontSettings.SetFontSources à la place.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir plusieurs dossiers de polices lors du rendu d'un document à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement spécifier plusieurs dossiers de polices à utiliser lors du rendu de vos documents. Aspose.Words propose une API puissante et flexible pour le traitement de mots avec des polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser les sources de polices utilisées lors du rendu de vos documents selon vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je définir plusieurs dossiers de polices dans Aspose.Words ?

 R : Pour définir plusieurs dossiers de polices dans Aspose.Words, vous pouvez utiliser le`SetFontsFolders` méthode du`Fonts` classe fournissant une liste d’emplacements de dossiers de polices personnalisés.

#### Q : La définition de plusieurs dossiers de polices affecte-t-elle tous les documents traités avec Aspose.Words ?

R : Oui, la définition de plusieurs dossiers de polices affecte tous les documents traités avec Aspose.Words. Une fois que vous avez défini les dossiers de polices, Aspose.Words utilisera ces emplacements pour rechercher des polices dans tous les documents.

#### Q : Combien de dossiers de polices puis-je définir dans Aspose.Words ?

R : Vous pouvez définir autant de dossiers de polices que nécessaire dans Aspose.Words. Il n'y a pas de limite spécifique au nombre de dossiers de polices que vous pouvez définir.

#### Q : Comment puis-je vérifier les dossiers de polices définis dans Aspose.Words ?

 R : Pour vérifier les dossiers de polices définis dans Aspose.Words, vous pouvez utiliser le`GetFolders` méthode du`Fonts` classe pour obtenir les emplacements des dossiers de polices configurés.

#### Q : Les dossiers de polices doivent-ils contenir des polices spécifiques ?

R : Oui, les dossiers de polices doivent contenir les polices que vous souhaitez utiliser dans vos documents Word. Aspose.Words recherchera les polices dans les dossiers spécifiés lors du traitement des documents.