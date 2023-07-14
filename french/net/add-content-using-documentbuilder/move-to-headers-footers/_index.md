---
title: Déplacer vers les en-têtes
linktitle: Déplacer vers les en-têtes
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser Aspose.Words pour .NET pour naviguer et modifier les en-têtes et les pieds de page dans les documents Word avec ce guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/move-to-headers-footers/
---

Dans cet exemple, nous allons explorer la fonctionnalité Move To Headers Footers de Aspose.Words pour .NET. Aspose.Words est une puissante bibliothèque de manipulation de documents qui permet aux développeurs de créer, modifier et convertir des documents Word par programmation. La fonction Déplacer vers les en-têtes/pieds de page nous permet de naviguer vers différents en-têtes et pieds de page dans un document et d'y ajouter du contenu.

Passons en revue le code source étape par étape pour comprendre comment utiliser la fonctionnalité Déplacer vers les en-têtes/pieds de page à l'aide de Aspose.Words pour .NET.



## Étape 1 : Initialisation du document et du générateur de documents

Tout d'abord, initialisez les objets Document et DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Configurer les en-têtes et les pieds de page

Spécifiez les paramètres d'en-tête/pied de page du document. Dans cet exemple, nous définissons les en-têtes et les pieds de page pour qu'ils soient différents pour la première page et pour les pages paires/impaires :

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Étape 3 : Créer des en-têtes pour différentes pages

Accédez à chaque type d'en-tête et ajoutez-y du contenu. Dans cet exemple, nous créons des en-têtes pour la première page, les pages paires et toutes les autres pages :

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Étape 4 : Créer des pages dans le document
Ajoutez du contenu au document pour créer plusieurs pages. Par exemple:

```csharp
// Créez deux pages dans le document.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Étape 5 : Enregistrer le document

Enregistrez le document modifié à l'emplacement souhaité :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Assurez-vous de spécifier le chemin et le format de fichier appropriés (par exemple, DOCX).

### Exemple de code source pour déplacer vers les en-têtes/pieds de page à l'aide de Aspose.Words pour .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Spécifiez que nous voulons des en-têtes et des pieds de page différents pour les premières pages, paires et impaires.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Créez les en-têtes.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Créez deux pages dans le document.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```
