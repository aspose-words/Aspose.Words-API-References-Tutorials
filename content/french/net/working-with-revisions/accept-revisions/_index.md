---
title: Accepter les révisions
linktitle: Accepter les révisions
second_title: API de traitement de documents Aspose.Words
description: Apprenez à accepter les révisions d'un document Word à l'aide d'Aspose.Words pour .NET
type: docs
weight: 10
url: /fr/net/working-with-revisions/accept-revisions/
---

Dans ce didacticiel, nous vous expliquerons comment accepter les révisions d'un document Word à l'aide de la fonctionnalité Accepter les révisions d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et accepter les modifications apportées au document.

## Étape 1 : Ajouter et modifier le contenu du document

Dans cet exemple, nous créons un document et ajoutons du contenu. Nous utilisons plusieurs paragraphes pour illustrer les changements et les révisions. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//Ajoutez du texte au premier paragraphe, puis ajoutez deux autres paragraphes.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Étape 2 : Suivre les avis et ajouter des avis

Nous activons le suivi des révisions et ajoutons une révision au document. Voici comment:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Ce paragraphe est une révision et aura l'indicateur "IsInsertRevision" correspondant défini.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Étape 3 : Supprimer un paragraphe et gérer les révisions

Nous supprimons un paragraphe et vérifions les révisions enregistrées. Voici comment:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Comme nous suivons les révisions, le paragraphe existe toujours dans le document, l'indicateur "IsDeleteRevision" sera défini
// et seront affichés sous forme de révision dans Microsoft Word, jusqu'à ce que nous acceptions ou rejetions toutes les révisions.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Étape 4 : Accepter les modifications

Nous acceptons toutes les modifications apportées au document. Voici comment:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Étape 5 : Arrêtez le suivi des avis

Nous allons arrêter le suivi des révisions afin que les modifications apportées au document n'apparaissent plus comme des révisions. Voici comment:

```csharp
doc.StopTrackRevisions();
```
## Étape 6 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Exemple de code source pour Accepter les révisions à l'aide de Aspose.Words pour .NET

Voici le code source complet pour accepter les modifications dans un document à l'aide d'Aspose.Words pour .NET :


```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//Ajoutez du texte au premier paragraphe, puis ajoutez deux autres paragraphes.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// Nous avons trois paragraphes, dont aucun n'est enregistré comme un type de révision
// Si nous ajoutons/supprimons du contenu dans le document lors du suivi des révisions,
// ils seront affichés tels quels dans le document et pourront être acceptés/rejetés.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Ce paragraphe est une révision et aura le drapeau "IsInsertRevision" correspondant défini.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Obtenez la collection de paragraphes du document et supprimez un paragraphe.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Étant donné que nous suivons les révisions, le paragraphe existe toujours dans le document, aura l'ensemble "IsDeleteRevision"
// et sera affiché en tant que révision dans Microsoft Word, jusqu'à ce que nous acceptions ou rejetions toutes les révisions.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Le paragraphe de suppression de révision est supprimé une fois que nous acceptons les modifications.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// L'arrêt du suivi des révisions fait apparaître ce texte comme du texte normal.
//Les révisions ne sont pas comptées lorsque le document est modifié.
doc.StopTrackRevisions();

// Enregistrez le document.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Conclusion

Dans ce didacticiel, nous avons appris à accepter les révisions dans un document Word à l'aide de la fonctionnalité Accepter les révisions d'Aspose.Words pour .NET. Nous avons suivi les étapes pour ajouter et modifier le contenu du document, suivre les révisions, supprimer un paragraphe révisé, accepter toutes les modifications et arrêter le suivi des révisions. Vous pouvez désormais appliquer ces connaissances pour gérer efficacement les révisions de vos propres documents Word à l'aide d'Aspose.Words pour .NET.

### FAQ

#### Q : Comment activer le suivi des révisions dans Aspose.Words pour .NET ?

#### Solution 1 :

 R : Pour activer le suivi des révisions dans Aspose.Words pour .NET, utilisez le`StartTrackRevisions` méthode de la`Document` objet et spécifiez le nom de l'auteur et la date de début du suivi des révisions.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Solution 2 :

 R : Vous pouvez également activer le suivi des révisions à l'aide de`Document` constructeur qui accepte`trackRevisions` et`author` paramètres.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Q : Comment accepter toutes les modifications dans un document avec Aspose.Words pour .NET ?

 R : Utilisez le`AcceptAllRevisions` méthode de la`Document` objet pour accepter toutes les modifications apportées au document.

```csharp
doc.AcceptAllRevisions();
```

#### Q : Comment enregistrer un document modifié avec les révisions acceptées ?

 Utilisez le`Save` méthode de la`Document` objet pour enregistrer le document modifié avec les révisions acceptées. Assurez-vous de fournir le chemin de fichier correct.

```csharp
doc.Save("path/to/the/document.docx");
```

#### Q : Comment arrêter le suivi des révisions dans Aspose.Words pour .NET ?

 R : Utilisez le`StopTrackRevisions` méthode de la`Document` objet pour arrêter le suivi des révisions.

```csharp
doc.StopTrackRevisions();
```

#### Q : Comment supprimer un paragraphe révisé dans un document avec Aspose.Words pour .NET ?

 R : Pour supprimer un paragraphe révisé dans un document, vous pouvez utiliser le`Remove` méthode de collecte des paragraphes.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```