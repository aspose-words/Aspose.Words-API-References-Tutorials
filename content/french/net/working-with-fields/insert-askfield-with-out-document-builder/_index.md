---
title: Insérer ASKField sans Document Builder
linktitle: Insérer ASKField sans Document Builder
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un champ ASK sans utiliser Document Builder dans Aspose.Words pour .NET. Suivez ce guide pour améliorer dynamiquement vos documents Word.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-askfield-with-out-document-builder/
---
## Introduction

Cherchez-vous à maîtriser l’automatisation des documents avec Aspose.Words pour .NET ? Vous êtes arrivé au bon endroit! Aujourd'hui, nous allons vous expliquer comment insérer un champ ASK sans utiliser de Document Builder. Il s'agit d'une fonctionnalité intéressante lorsque vous souhaitez que votre document invite les utilisateurs à effectuer des saisies spécifiques, rendant ainsi vos documents Word plus interactifs et dynamiques. Alors allons-y et rendons vos documents plus intelligents !

## Conditions préalables

Avant de nous salir les mains avec du code, assurons-nous que tout est configuré :

1.  Aspose.Words pour .NET : assurez-vous que cette bibliothèque est installée. Sinon, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : un IDE approprié comme Visual Studio.
3. .NET Framework : assurez-vous que .NET Framework est installé.

Super! Maintenant que nous sommes tous prêts, commençons par importer les espaces de noms nécessaires.

## Importer des espaces de noms

Tout d’abord, nous devons importer l’espace de noms Aspose.Words pour accéder à toutes les fonctionnalités d’Aspose.Words pour .NET. Voici comment procéder :

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

## Étape 1 : Créer un nouveau document

Avant de pouvoir insérer un champ ASK, nous avons besoin d'un document avec lequel travailler. Voici comment créer un nouveau document :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Création de documents.
Document doc = new Document();
```

Cet extrait de code configure un nouveau document Word dans lequel nous ajouterons notre champ ASK.

## Étape 2 : accéder au nœud de paragraphe

Dans un document Word, le contenu est organisé en nœuds. Nous devons accéder au premier nœud de paragraphe où nous insérerons notre champ ASK :

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

Cette ligne de code récupère le premier paragraphe du document, prêt pour l'insertion de notre champ ASK.

## Étape 3 : Insérez le champ ASK

Passons maintenant à l'événement principal : l'insertion du champ ASK. Ce champ invitera l'utilisateur à entrer des données lors de l'ouverture du document.

```csharp
// Insérez le champ ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Ici, nous ajoutons un champ ASK au paragraphe. Simple, non ?

## Étape 4 : configurer le champ ASK

Nous devons définir certaines propriétés pour définir le comportement du champ ASK. Configurons le nom du signet, le texte de l'invite, la réponse par défaut et le comportement de publipostage :

```csharp
field.BookmarkName = "Test1";
field.PromptText = "Please enter your response:";
field.DefaultResponse = "Default response";
field.PromptOnceOnMailMerge = true;
```

- BookmarkName : un identifiant unique pour le champ ASK.
- PromptText : texte qui invite l'utilisateur à effectuer une saisie.
- DefaultResponse : la réponse pré-remplie que l'utilisateur peut modifier.
- PromptOnceOnMailMerge : détermine si l'invite apparaît une seule fois lors d'un publipostage.

## Étape 5 : Mettre à jour le champ

Après avoir configuré le champ ASK, nous devons le mettre à jour pour garantir que tous les paramètres sont appliqués correctement :

```csharp
field.Update();
```

Cette commande garantit que notre champ ASK est prêt et correctement configuré dans le document.

## Étape 6 : Enregistrez le document

Enfin, sauvegardons le document dans notre répertoire spécifié :

```csharp
doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Cette ligne enregistre le document avec le champ ASK inséré. Et voilà, votre document est désormais équipé d’un champ ASK dynamique !

## Conclusion

Toutes nos félicitations! Vous venez d'ajouter un champ ASK à un document Word à l'aide d'Aspose.Words pour .NET sans Document Builder. Cette fonctionnalité peut améliorer considérablement l'interaction de l'utilisateur avec vos documents, les rendant plus flexibles et conviviaux. Continuez à expérimenter différents champs et propriétés pour libérer tout le potentiel d’Aspose.Words. Bon codage !

## FAQ

### Qu'est-ce qu'un champ ASK dans Aspose.Words ?
Un champ ASK dans Aspose.Words est un champ qui invite l'utilisateur à effectuer une saisie spécifique lors de l'ouverture du document, permettant ainsi la saisie dynamique de données.

### Puis-je utiliser plusieurs champs ASK dans un seul document ?
Oui, vous pouvez insérer plusieurs champs ASK dans un document, chacun avec des invites et des réponses uniques.

###  Quel est le but du`PromptOnceOnMailMerge` property?
 Le`PromptOnceOnMailMerge` La propriété détermine si l'invite ASK apparaît une seule fois lors d'une opération de publipostage ou à chaque fois.

### Dois-je mettre à jour le champ ASK après avoir défini ses propriétés ?
Oui, la mise à jour du champ ASK garantit que toutes les propriétés sont correctement appliquées et que le champ fonctionne comme prévu.

### Puis-je personnaliser le texte de l'invite et la réponse par défaut ?
Absolument! Vous pouvez définir un texte d'invite personnalisé et des réponses par défaut pour adapter le champ ASK à vos besoins spécifiques.