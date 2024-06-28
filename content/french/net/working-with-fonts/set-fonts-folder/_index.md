---
title: Définir le dossier des polices
linktitle: Définir le dossier des polices
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir le répertoire des polices dans Aspose.Words for .NET et garantir la disponibilité des polices utilisées dans vos documents.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folder/
---
Dans ce didacticiel, nous allons vous montrer comment définir le répertoire des polices dans Aspose.Words pour .NET. Vous apprendrez à spécifier le répertoire contenant les polices utilisées dans votre document Word.

## Conditions préalables
Avant de commencer, assurez-vous de disposer des éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Définir le répertoire des documents
Commencez par définir le chemin du répertoire vers l’emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Définir le répertoire des polices
 Créez une instance du`FontSettings` classe et utiliser le`SetFontsFolder` méthode pour spécifier le répertoire contenant les polices. Remplacer`"Fonts"` avec le nom du répertoire de polices actuel.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Étape 3 : Chargez le document avec les paramètres de police
 Utilisez le`LoadOptions` classe pour spécifier les paramètres de police dans le`FontSettings` option. Utilisez ensuite le`Document` classe pour charger le document en utilisant ces options.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Exemple de code source pour définir le dossier de polices à l'aide d'Aspose.Words pour .NET 

```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusion
Félicitation ! Vous savez maintenant comment définir le répertoire des polices dans Aspose.Words for .NET. Vous pouvez utiliser cette fonctionnalité pour garantir la disponibilité des polices utilisées dans votre document et pour garantir la cohérence de l'affichage des polices.

### FAQ

#### Q : Comment puis-je définir un dossier de polices personnalisé dans Aspose.Words ?

 R : Pour définir un dossier de polices personnalisées dans Aspose.Words, vous pouvez utiliser le`FontsFolder` la classe et le`SetFontsFolders` méthode spécifiant le chemin d’accès au dossier contenant vos polices.

#### Q : Puis-je définir plusieurs dossiers de polices dans Aspose.Words ?

 R : Oui, vous pouvez définir plusieurs dossiers de polices dans Aspose.Words en appelant le`SetFontsFolders` méthode plusieurs fois avec les chemins des différents dossiers de polices que vous souhaitez utiliser.

#### Q : Que se passe-t-il si une police utilisée dans le document n'est pas présente dans les dossiers de polices définis ?

R : Si une police utilisée dans le document n'est pas présente dans les dossiers de polices définis dans Aspose.Words, une police de remplacement sera utilisée à la place. Cela garantit que le texte du document sera toujours affiché correctement, même si la police d'origine n'est pas disponible.

#### Q : Les dossiers de polices définis dans Aspose.Words ont-ils la priorité sur les polices installées sur le système ?

R : Oui, les dossiers de polices définis dans Aspose.Words ont priorité sur les polices installées sur le système. Cela signifie que si une police du même nom est présente à la fois dans les dossiers de polices définis et dans les polices système, la version du dossier de polices sera utilisée lors du traitement des documents Word.