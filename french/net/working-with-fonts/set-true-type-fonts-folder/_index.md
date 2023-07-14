---
title: Définir le dossier des polices True Type
linktitle: Définir le dossier des polices True Type
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour définir le dossier des polices True Type lors du rendu d'un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-true-type-fonts-folder/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus de définition du dossier de polices True Type lors du rendu d'un document à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment spécifier un dossier personnalisé contenant les polices True Type à utiliser lors du rendu de vos documents à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document rendu modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document à afficher
 Ensuite, vous devez charger le document à rendre à l'aide de la`Document` classe. Assurez-vous de spécifier le bon chemin d'accès au document.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Définir le dossier des polices True Type
Vous pouvez désormais spécifier le dossier des polices True Type à utiliser lors du rendu en créant une instance de`FontSettings` classe et en utilisant la`SetFontsFolder()` méthode pour définir le dossier des polices. Vous pouvez spécifier un dossier personnalisé contenant vos polices True Type. Le deuxième paramètre à`SetFontsFolder()` indique si vous souhaitez également rechercher les sous-dossiers du dossier spécifié.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Étape 4 : Enregistrer le document rendu
 Enfin, vous pouvez enregistrer le document rendu dans un fichier à l'aide de la`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Exemple de code source pour le dossier Set True Type Fonts à l'aide de Aspose.Words pour .NET 

```csharp
//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Notez que ce paramètre remplacera toutes les sources de polices par défaut qui sont recherchées par défaut. Désormais, seuls ces dossiers seront recherchés
// Polices lors du rendu ou de l'incorporation de polices. Pour ajouter une source de police supplémentaire tout en conservant les sources de police système, utilisez à la fois FontSettings.GetFontSources et
// FontSettings.SetFontSources à la place
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Définir les paramètres de police
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir le dossier des polices True Type lors du rendu d'un document à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement spécifier un dossier personnalisé contenant les polices True Type à utiliser lors du rendu de vos documents. Aspose.Words propose une API puissante et flexible pour le traitement de mots avec des polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser les polices utilisées lors du rendu de vos documents selon vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je configurer le dossier des polices TrueType dans Aspose.Words ?

 R : Pour configurer le dossier des polices TrueType dans Aspose.Words, vous pouvez utiliser le`SetTrueTypeFontsFolder` méthode de la`Fonts` classe spécifiant l'emplacement du dossier contenant les polices TrueType.

#### Q : Quels types de polices sont considérés comme des polices TrueType ?

R : Les polices TrueType sont un format de police populaire. Ils sont souvent utilisés dans les documents Word et ont une extension de fichier .ttf ou .ttc.

#### Q : Puis-je spécifier plusieurs dossiers de polices TrueType dans Aspose.Words ?

R : Oui, vous pouvez spécifier plusieurs dossiers de polices TrueType dans Aspose.Words à l'aide du`SetTrueTypeFontsFolder` méthode de la`Fonts` classe avec une liste d'emplacements de dossiers.

#### Q : Comment puis-je vérifier le dossier des polices TrueType configuré dans Aspose.Words ?

 A: Pour vérifier le dossier TrueType Fonts configuré dans Aspose.Words, vous pouvez utiliser le`GetTrueTypeFontsFolder` méthode de la`Fonts` class pour obtenir l'emplacement du dossier TrueType Fonts configuré.

#### Q : Pourquoi est-il important de configurer le dossier des polices TrueType dans Aspose.Words ?

R : La configuration du dossier des polices TrueType dans Aspose.Words est importante car elle aide Aspose.Words à localiser les polices nécessaires lors du traitement des documents Word. Cela garantit la cohérence de la mise en forme et de l'apparence des documents, même sur différents systèmes.