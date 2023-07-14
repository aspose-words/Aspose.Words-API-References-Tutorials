---
title: Utiliser le caractère d'espace par niveau pour l'indentation de la liste
linktitle: Utiliser le caractère d'espace par niveau pour l'indentation de la liste
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour l'utilisation d'un espace par niveau pour l'indentation de liste dans Aspose.Words pour .NET. Créez facilement des documents Word bien structurés.
type: docs
weight: 10
url: /fr/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words pour .NET est une bibliothèque puissante pour créer, éditer et manipuler des documents Word dans une application C#. Parmi les fonctionnalités offertes par Aspose.Words figure la possibilité d'utiliser un espace par niveau pour l'indentation des listes. Dans ce guide, nous allons vous montrer comment utiliser le code source C# de Aspose.Words pour .NET pour implémenter cette fonctionnalité.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque populaire qui rend le traitement de mots avec des documents Word simple et efficace. Il offre un large éventail de fonctionnalités pour créer, modifier et manipuler des documents Word, y compris la gestion des listes et de l'indentation.

## Création du document et ajout de contenu

La première étape consiste à créer un nouveau document et à y ajouter du contenu. Utilisez la classe Document pour créer une nouvelle instance de document. Utilisez ensuite la classe DocumentBuilder pour ajouter du texte et créer une liste avec plusieurs niveaux d'indentation. Voici un exemple :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Créer une liste avec trois niveaux d'indentation
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

Dans cet exemple, nous créons un nouveau document et utilisons le DocumentBuilder pour ajouter du texte et créer une liste avec trois niveaux d'indentation. Nous avons ajouté trois éléments à la liste, chaque élément étant mis en retrait d'un niveau supplémentaire.

## Utilisation d'un espace par niveau pour l'indentation de la liste

Une fois le contenu ajouté, nous pouvons maintenant configurer l'indentation des listes en utilisant un espace par niveau. Pour cela nous utilisons la classe TxtSaveOptions et nous définissons la propriété ListIndentation.Count sur le nombre de niveaux d'indentation et la propriété ListIndentation.Character sur le caractère espace à utiliser. Voici comment:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

Dans cet exemple, nous créons une instance de TxtSaveOptions et définissons la propriété ListIndentation.Count sur 3 pour indiquer qu'il existe trois niveaux d'indentation dans la liste. Nous définissons également la propriété ListIndentation.Character sur le caractère d'espacement (' ') que nous voulons utiliser pour l'indentation.

### Exemple de code source pour la fonctionnalité "Utiliser un espace par niveau pour l'indentation de la liste" avec Aspose.Words pour .NET

Voici l'exemple de code source complet pour la fonctionnalité "Utiliser un espace par niveau pour l'indentation de la liste" avec Aspose.Words pour .NET :

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Chemin d'accès à votre répertoire de documents
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Créer le document et ajouter du contenu
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Créer une liste avec trois niveaux d'indentation
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Utilisez un espace par niveau pour l'indentation de la liste
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Enregistrez le document avec les options spécifiées
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser Aspose.Words pour .NET pour appliquer la fonctionnalité "Utiliser un espace par niveau pour l'indentation de la liste". En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement configurer l'indentation des listes dans vos documents Word en utilisant un espace par niveau. Aspose.Words offre une flexibilité et une puissance considérables pour le traitement de mots avec le formatage du texte et la gestion des listes, vous permettant de créer des documents bien structurés dans votre application C#.

### Questions fréquemment posées

#### Q : Qu'est-ce qu'Aspose.Words pour .NET ?
Aspose.Words pour .NET est une bibliothèque puissante pour créer, éditer et manipuler des documents Word dans une application C#. Il offre de nombreuses fonctionnalités pour le traitement de texte avec des documents Word, notamment la possibilité d'utiliser un espace par niveau pour l'indentation des listes.

#### Q : Comment puis-je utiliser un espace par niveau pour l'indentation de liste avec Aspose.Words pour .NET ?
Vous pouvez utiliser un espace par niveau pour l'indentation de la liste en suivant ces étapes :

 Créez un nouveau document à l'aide de`Document` classe.

 Utilisez le`DocumentBuilder`classe pour ajouter du contenu au document et créer une liste avec plusieurs niveaux d'indentation.

 Une fois que vous avez ajouté le contenu et configuré l'indentation de la liste, utilisez le`TxtSaveOptions`classe et définissez la`ListIndentation.Count` propriété au nombre de niveaux d'indentation et à la`ListIndentation.Character` propriété sur l'espace (`' '`) utiliser.

 Enregistrez le document avec les options spécifiées à l'aide de la`Save` méthode de la`Document` classe.

#### Q : Aspose.Words prend-il en charge d'autres caractères pour l'indentation de la liste ?
Oui, Aspose.Words prend en charge d'autres caractères pour les listes d'indentation. Vous pouvez utiliser des caractères non blancs, tels que des tabulations (`'\t'` ) ou d'autres caractères spéciaux, en définissant le`ListIndentation.Character` propriété au caractère désiré.

#### Q : Est-il possible de personnaliser le nombre d'espaces par niveau pour l'indentation de la liste ?
 Oui, vous pouvez personnaliser le nombre d'espaces par niveau pour l'indentation de la liste en modifiant la valeur de`ListIndentation.Count` propriété dans le`TxtSaveOptions` classe. Vous pouvez spécifier le nombre d'espaces souhaité pour chaque niveau d'indentation.

#### Q : Quelles autres fonctionnalités Aspose.Words offre-t-il pour la gestion des listes ?
Aspose.Words offre de nombreuses fonctionnalités pour gérer les listes dans les documents Word. Vous pouvez créer des listes numérotées ou à puces, définir des niveaux d'indentation, personnaliser le style des listes, ajouter des éléments de liste, etc.