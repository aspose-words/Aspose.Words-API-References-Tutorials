---
title: Déplacer vers le paragraphe
linktitle: Déplacer vers le paragraphe
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser Aspose.Words pour la fonctionnalité Déplacer vers le paragraphe de .NET pour parcourir et manipuler les paragraphes dans les documents Word par programmation.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/move-to-paragraph/
---

Dans cet exemple étape par étape, nous allons explorer la fonction Déplacer vers le paragraphe de Aspose.Words pour .NET. Cette fonctionnalité permet aux développeurs de naviguer et de manipuler les paragraphes dans un document Word par programmation. En suivant ce guide, vous apprendrez à mettre en œuvre et à utiliser efficacement la fonctionnalité Déplacer vers le paragraphe.

Le code ci-dessus illustre l'utilisation de la fonctionnalité Déplacer vers le paragraphe. Comprenons chaque étape en détail:

## Étape 1 : Chargement du document

 Nous commençons par charger le document Word dans une instance du`Document` classe. Le`MyDir`représente le chemin du répertoire où se trouve le document. Vous devez le remplacer par le chemin de répertoire réel ou modifier le code en conséquence.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
```

## Étape 2 : Initialisation de DocumentBuilder

 Ensuite, nous créons un`DocumentBuilder` objet et associez-le au document chargé. Le`DocumentBuilder` La classe fournit diverses méthodes et propriétés pour manipuler le contenu du document.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Passer à un paragraphe spécifique

 Le`MoveToParagraph` La méthode est utilisée pour positionner le générateur de document à un paragraphe spécifique dans le document. Il prend deux paramètres : l'index du paragraphe cible et la position du caractère dans ce paragraphe (0 représente le début du paragraphe).

Dans l'exemple fourni, nous passons au troisième paragraphe (index 2) du document :

```csharp
builder.MoveToParagraph(2, 0);
```

## Étape 4 : Modifier le contenu du paragraphe

 Une fois le constructeur positionné au niveau du paragraphe souhaité, nous pouvons utiliser le`Writeln`méthode pour ajouter ou modifier le contenu de ce paragraphe. Dans ce cas, nous ajoutons le texte "Ceci est le 3ème paragraphe."

```csharp
builder.Writeln("This is the 3rd paragraph.");
```

### Exemple de code source pour déplacer vers le paragraphe en utilisant Aspose.Words pour .NET

Vous trouverez ci-dessous l'exemple de code source complet pour implémenter la fonctionnalité Déplacer vers le paragraphe à l'aide de Aspose.Words pour .NET :

```csharp

	Document doc = new Document(MyDir + "Paragraphs.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToParagraph(2, 0);
	builder.Writeln("This is the 3rd paragraph.");
	
```

En suivant ce guide et en utilisant la fonction Déplacer vers le paragraphe, vous pouvez manipuler par programmation des paragraphes dans des documents Word à l'aide d'Aspose.Words pour .NET.

