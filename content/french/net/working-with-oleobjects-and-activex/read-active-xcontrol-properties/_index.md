---
title: Lire les propriétés XControl actives à partir d'un fichier Word
linktitle: Lire les propriétés XControl actives à partir d'un fichier Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment lire les propriétés du contrôle ActiveX à partir de fichiers Word à l'aide d'Aspose.Words for .NET dans un guide étape par étape. Améliorez vos compétences en automatisation de documents.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## Introduction

À l’ère numérique d’aujourd’hui, l’automatisation est essentielle pour améliorer la productivité. Si vous travaillez avec des documents Word contenant des contrôles ActiveX, vous devrez peut-être lire leurs propriétés à diverses fins. Les contrôles ActiveX, tels que les cases à cocher et les boutons, peuvent contenir des données importantes. En utilisant Aspose.Words pour .NET, vous pouvez extraire et manipuler efficacement ces données par programme.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1.  Aspose.Words for .NET Library : vous pouvez le télécharger à partir de[ici](https://releases.aspose.com/words/net/).
2. Visual Studio ou n’importe quel IDE C# : pour écrire et exécuter votre code.
3. Un document Word avec des contrôles ActiveX : par exemple, "ActiveX CONTROLS.docx".
4. Connaissance de base de C# : Une connaissance de la programmation C# est nécessaire pour suivre.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires pour travailler avec Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## Étape 1 : Charger le document Word

Pour commencer, vous devrez charger le document Word contenant les contrôles ActiveX.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## Étape 2 : initialiser une chaîne pour contenir les propriétés

Ensuite, initialisez une chaîne vide pour stocker les propriétés des contrôles ActiveX.

```csharp
string properties = "";
```

## Étape 3 : Parcourir les formes du document

Nous devons parcourir toutes les formes du document pour trouver les contrôles ActiveX.

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        // Traiter le contrôle ActiveX
    }
}
```

## Étape 4 : Extraire les propriétés des contrôles ActiveX

Dans la boucle, vérifiez si le contrôle est un Forms2OleControl. Si tel est le cas, lancez-le et extrayez les propriétés.

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## Étape 5 : Compter le nombre total de contrôles ActiveX

Après avoir parcouru toutes les formes, comptez le nombre total de contrôles ActiveX trouvés.

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## Étape 6 : Afficher les propriétés

Enfin, imprimez les propriétés extraites sur la console.

```csharp
Console.WriteLine("\n" + properties);
```

## Conclusion

Et voilà ! Vous avez appris avec succès à lire les propriétés du contrôle ActiveX à partir d'un document Word à l'aide d'Aspose.Words pour .NET. Ce didacticiel couvrait le chargement d'un document, l'itération dans les formes et l'extraction des propriétés des contrôles ActiveX. En suivant ces étapes, vous pouvez automatiser l'extraction de données importantes de vos documents Word, améliorant ainsi l'efficacité de votre flux de travail.

## FAQ

### Que sont les contrôles ActiveX dans les documents Word ?
Les contrôles ActiveX sont des objets interactifs intégrés dans des documents Word, tels que des cases à cocher, des boutons et des champs de texte, utilisés pour créer des formulaires et automatiser des tâches.

### Puis-je modifier les propriétés des contrôles ActiveX à l’aide d’Aspose.Words for .NET ?
Oui, Aspose.Words for .NET vous permet de modifier les propriétés des contrôles ActiveX par programme.

### L’utilisation d’Aspose.Words pour .NET est-elle gratuite ?
 Aspose.Words for .NET propose un essai gratuit, mais vous devrez acheter une licence pour une utilisation continue. Vous pouvez obtenir un essai gratuit[ici](https://releases.aspose.com/).

### Puis-je utiliser Aspose.Words pour .NET avec d’autres langages .NET autres que C# ?
Oui, Aspose.Words for .NET peut être utilisé avec n'importe quel langage .NET, y compris VB.NET et F#.

### Où puis-je trouver plus de documentation sur Aspose.Words pour .NET ?
 Vous pouvez trouver une documentation détaillée[ici](https://reference.aspose.com/words/net/).