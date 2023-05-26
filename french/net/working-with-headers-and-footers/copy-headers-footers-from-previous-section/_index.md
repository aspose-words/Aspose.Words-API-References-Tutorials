---
title: Copier les en-têtes et les pieds de page de la section précédente
linktitle: Copier les en-têtes et les pieds de page de la section précédente
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à copier les en-têtes et les pieds de page de la section précédente dans les documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment copier les en-têtes et les pieds de page de la section précédente dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Accéder à la section précédente

 Tout d'abord, récupérez la section précédente en accédant au`PreviousSibling` propriété de la section courante :

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Étape 2 : Vérification de la section précédente

Ensuite, vérifiez si une section précédente existe. S'il n'y a pas de section précédente, on retourne simplement :

```csharp
if (previousSection == null)
    return;
```

## Étape 3 : Effacer et copier les en-têtes et les pieds de page

Pour copier les en-têtes et pieds de page de la section précédente vers la section actuelle, nous effaçons les en-têtes et pieds de page existants dans la section actuelle, puis parcourons les en-têtes et pieds de page de la section précédente pour ajouter des copies clonées à la section actuelle :

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Étape 4 : Enregistrer le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save("OutputDocument.docx");
```

C'est ça! Vous avez réussi à copier les en-têtes et les pieds de page de la section précédente vers la section actuelle dans un document Word à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Copier les en-têtes de pied de page de la section précédente à l'aide de Aspose.Words pour .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.