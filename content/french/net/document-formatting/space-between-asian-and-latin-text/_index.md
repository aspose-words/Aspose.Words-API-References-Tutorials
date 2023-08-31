---
title: Espace entre le texte asiatique et latin dans un document Word
linktitle: Espace entre le texte asiatique et latin dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajuster automatiquement l'espace entre le texte asiatique et latin dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/space-between-asian-and-latin-text/
---
Dans ce didacticiel, nous allons vous montrer comment utiliser la fonctionnalité Espace entre le texte asiatique et latin dans la fonctionnalité de document Word avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Création et configuration du document

Pour commencer, créez un nouveau document et un objet DocumentBuilder associé. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Définir l'espace entre le texte asiatique et latin

Nous allons maintenant configurer l'espace entre le texte asiatique et latin en utilisant les propriétés de l'objet ParagraphFormat. Voici comment:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Étape 3 : Sauvegarde du document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide du`Save` méthode. Assurez-vous de fournir le chemin de fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Exemple de code source pour l'espace entre le texte asiatique et latin utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Espace entre texte asiatique et latin avec Aspose.Words pour .NET :


```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

Avec ce code, vous pourrez ajuster automatiquement l'espace entre le texte asiatique et latin dans votre document à l'aide d'Aspose.Words pour .NET.

## Conclusion

Dans ce didacticiel, nous avons exploré le processus d'utilisation de la fonctionnalité Espace pour ajuster l'espacement entre le texte asiatique et latin dans un document Word avec Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez garantir un espacement et un alignement appropriés, particulièrement utiles lorsqu'il s'agit de contenu mixte asiatique et latin.

### FAQ

#### Q : Qu'est-ce que la fonctionnalité Espace entre le texte asiatique et latin dans un document Word ?

R : La fonctionnalité Espace entre le texte asiatique et latin dans un document Word fait référence à la possibilité d'ajuster automatiquement l'espacement entre le texte écrit dans différentes écritures, telles que l'asiatique (par exemple, le chinois, le japonais) et le latin (par exemple, l'anglais).

#### Q : Pourquoi est-il important d'ajuster l'espace entre les textes asiatiques et latins ?

R : Ajuster l'espace entre le texte asiatique et latin est crucial pour garantir que les différentes écritures se fondent harmonieusement dans le document. Un espacement approprié améliore la lisibilité et l’apparence visuelle globale, empêchant le texte de paraître trop à l’étroit ou étalé.

#### Q : Puis-je personnaliser les ajustements d’espace entre différents scripts ?

 R : Oui, vous pouvez personnaliser les ajustements d'espace entre différents scripts à l'aide du`AddSpaceBetweenFarEastAndAlpha` et`AddSpaceBetweenFarEastAndDigit` propriétés. En activant ou en désactivant ces propriétés, vous pouvez contrôler l'espace entre le texte asiatique et latin, ainsi qu'entre le texte asiatique et les chiffres.

#### Q : Aspose.Words pour .NET prend-il en charge d'autres fonctionnalités de formatage de documents ?

: Oui, Aspose.Words for .NET offre une prise en charge étendue de diverses fonctionnalités de formatage de documents. Il comprend des fonctionnalités pour les styles de police, les paragraphes, les tableaux, les images, etc. Vous pouvez manipuler et formater efficacement vos documents Word par programmation.

#### Q : Où puis-je trouver des ressources et de la documentation supplémentaires pour Aspose.Words pour .NET ?

 R : Pour obtenir des ressources et une documentation complètes sur l'utilisation d'Aspose.Words pour .NET, visitez[Référence de l'API Aspose.Words](https://reference.aspose.com/words/net/). Vous y trouverez des guides détaillés, des didacticiels, des exemples de code et des références d'API pour vous aider à utiliser efficacement les puissantes fonctionnalités d'Aspose.Words for .NET.