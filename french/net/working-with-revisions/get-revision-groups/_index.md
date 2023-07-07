---
title: Obtenir des groupes de révision
linktitle: Obtenir des groupes de révision
second_title: Référence de l'API Aspose.Words pour .NET
description: Obtenez des groupes de révision dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/get-revision-groups/
---

Dans ce guide étape par étape, nous allons vous expliquer comment obtenir les groupes de révision dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : Chargement du document

La première étape consiste à télécharger le document contenant les révisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Étape 2 : Parcourir les groupes de révision

Ensuite, nous allons parcourir les groupes de révision présents dans le document et afficher leurs détails, tels que l'auteur, le type de révision et le texte révisé.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Exemple de code source pour Get Revision Groups en utilisant Aspose.Words pour .NET

Voici le code source complet pour obtenir les groupes de révision dans un document utilisant Aspose.Words pour .NET :

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à obtenir les groupes de révision dans un document Word à l'aide de Aspose.Words pour .NET. Nous avons suivi les étapes pour charger le document et parcourir les groupes de révision, en affichant des détails tels que l'auteur et le type de révision. Vous pouvez maintenant appliquer ces connaissances pour analyser les révisions de votre propre document Word en utilisant Aspose.Words pour .NET.

### FAQ

#### Q : Comment télécharger un document dans Aspose.Words pour .NET ?

 R : Utilisez le`Document` classe de Aspose.Words pour .NET pour charger un document à partir d'un fichier. Vous pouvez spécifier le chemin d'accès complet au document.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q : Comment parcourir les groupes de révision dans un document dans Aspose.Words pour .NET ?

 R : Utilisez le`Groups` propriété du document`Revisions` objet pour obtenir la collection de groupes de révision. Vous pouvez ensuite utiliser une boucle pour parcourir chaque groupe de révision.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Traiter chaque groupe d'avis ici
}
```

#### Q : Comment obtenir l'auteur d'un groupe de révision dans Aspose.Words pour .NET ?

 R : Utilisez le`Author` propriété de la`RevisionGroup` objet pour obtenir l'auteur du groupe de révision.

```csharp
string author = group.Author;
```

#### Q : Comment obtenir le type de révision d'un groupe de révision dans Aspose.Words pour .NET ?

 R : Utilisez le`RevisionType` propriété de la`RevisionGroup`objet pour obtenir le type de révision du groupe.

```csharp
string revisionType = group.RevisionType;
```