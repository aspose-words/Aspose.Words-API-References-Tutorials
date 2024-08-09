---
title: Insérer un objet Ole en tant qu'icône à l'aide de Stream
linktitle: Insérer un objet Ole en tant qu'icône à l'aide de Stream
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un objet OLE sous forme d'icône à l'aide d'un flux avec Aspose.Words for .NET dans ce didacticiel détaillé étape par étape.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---
## Introduction

Dans ce didacticiel, nous explorons une fonctionnalité très intéressante d'Aspose.Words for .NET : insérer un objet OLE (Object Linking and Embedding) sous forme d'icône à l'aide d'un flux. Que vous intégriez une présentation PowerPoint, une feuille de calcul Excel ou tout autre type de fichier, ce guide vous montrera exactement comment procéder. Prêt à commencer ? Allons-y!

## Conditions préalables

Avant de passer au code, vous aurez besoin de quelques éléments :

-  Aspose.Words for .NET : si vous ne l'avez pas déjà fait,[télécharger](https://releases.aspose.com/words/net/) et installez Aspose.Words pour .NET.
- Environnement de développement : Visual Studio ou tout autre environnement de développement C#.
- Fichiers d'entrée : le fichier que vous souhaitez intégrer (par exemple, une présentation PowerPoint) et une image d'icône.

## Importer des espaces de noms

Pour commencer, assurez-vous d'avoir importé les espaces de noms nécessaires dans votre projet :

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Décomposons le processus étape par étape pour le rendre facile à suivre.

## Étape 1 : Créer un nouveau document

Tout d’abord, nous allons créer un nouveau document et un générateur de documents pour l’utiliser.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Pensez à`Document` comme votre toile vierge et`DocumentBuilder` comme votre pinceau. Nous configurons nos outils pour commencer à créer notre chef-d'œuvre.

## Étape 2 : préparer le flux

Ensuite, nous devons préparer un flux mémoire contenant le fichier que nous souhaitons intégrer. Dans cet exemple, nous intégrerons une présentation PowerPoint.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes("Path_to_your_directory/Presentation.pptx")))
{
```

Cette étape revient à charger votre peinture sur le pinceau. Nous préparons notre fichier à être intégré.

## Étape 3 : Insérez l'objet OLE en tant qu'icône

Nous allons maintenant utiliser le générateur de documents pour insérer l'objet OLE dans le document. Nous spécifierons le flux du fichier, le ProgID pour le type de fichier (dans ce cas, "Package"), le chemin d'accès à l'image de l'icône et une étiquette pour le fichier intégré.

```csharp
builder.InsertOleObjectAsIcon(stream, "Package", "Path_to_your_directory/Logo icon.ico", "My embedded file");
}
```

C'est ici que la magie opère ! Nous intégrons notre fichier et l'affichons sous forme d'icône dans le document.

## Étape 4 : Enregistrez le document

Enfin, nous enregistrons le document dans un chemin spécifié.

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Cette étape revient à mettre votre tableau fini dans un cadre et à l'accrocher au mur. Votre document est maintenant prêt à être utilisé !

## Conclusion

Et voilà ! Vous avez incorporé avec succès un objet OLE sous forme d'icône dans un document Word à l'aide d'Aspose.Words pour .NET. Cette fonctionnalité puissante peut vous aider à créer facilement des documents dynamiques et interactifs. Que vous intégriez des présentations, des feuilles de calcul ou d'autres fichiers, Aspose.Words facilite la tâche. Alors n'hésitez plus, essayez-le et voyez la différence que cela peut faire dans vos documents !

## FAQ

### Puis-je intégrer différents types de fichiers en utilisant cette méthode ?
Oui, vous pouvez intégrer n'importe quel type de fichier pris en charge par OLE, notamment Word, Excel, PowerPoint, etc.

### Ai-je besoin d’une licence spéciale pour utiliser Aspose.Words pour .NET ?
 Oui, Aspose.Words for .NET nécessite une licence. Vous pouvez obtenir un[essai gratuit](https://releases.aspose.com/) ou acheter un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour les tests.

### Puis-je personnaliser l'icône utilisée pour l'objet OLE ?
 Absolument! Vous pouvez utiliser n'importe quel fichier image pour l'icône en spécifiant son chemin dans le champ`InsertOleObjectAsIcon` méthode.

### Que se passe-t-il si les chemins d'accès aux fichiers ou aux icônes sont incorrects ?
La méthode lèvera une exception. Assurez-vous que les chemins d'accès à vos fichiers sont corrects pour éviter les erreurs.

### Est-il possible de lier l’objet incorporé au lieu de l’intégrer ?
Oui, Aspose.Words vous permet d'insérer des objets OLE liés, qui référencent le fichier sans intégrer son contenu.