---
title: Déplacer le nœud dans le document suivi
linktitle: Déplacer le nœud dans le document suivi
second_title: Référence de l'API Aspose.Words pour .NET
description: Déplacez les nœuds dans un document suivi avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/move-node-in-tracked-document/
---

Dans ce guide étape par étape, nous vous expliquerons comment déplacer un nœud dans un document Word suivi à l'aide de Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : Création du document

La première étape consiste à créer un nouveau document et à ajouter des paragraphes.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Étape 2 : Suivre les révisions

Nous allons activer le suivi des révisions dans le document.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Étape 3 : Déplacer un nœud

Nous allons déplacer un nœud (paragraphe) d'une position à une autre tout en générant des révisions.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Étape 4 : Arrêtez de suivre les avis

Nous arrêterons de suivre les révisions dans le document.

```csharp
doc.StopTrackRevisions();
```

## Étape 5 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Exemple de code source pour Déplacer le nœud dans le document suivi à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour déplacer un nœud dans un document suivi à l'aide d'Aspose.Words pour .NET :


```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Commencez à suivre les révisions.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Générez des révisions lors du déplacement d'un nœud d'un emplacement à un autre.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Arrêtez le processus de suivi des révisions.
doc.StopTrackRevisions();

// Il y a 3 paragraphes supplémentaires dans la plage de départ.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

