---
title: Remplacer les hyperliens
linktitle: Remplacer les hyperliens
second_title: Référence de l'API Aspose.Words pour .NET
description: Remplacez les liens hypertexte dans les documents Word à l'aide d'Aspose.Words pour .NET. Instructions pas à pas pour remplacer les hyperliens.
type: docs
weight: 10
url: /fr/net/working-with-fields/replace-hyperlinks/
---

Voici un guide étape par étape pour expliquer le code source C # suivant pour remplacer les liens hypertexte à l'aide de la fonctionnalité Aspose.Words pour .NET. Assurez-vous d'avoir inclus la bibliothèque Aspose.Words dans votre projet avant d'utiliser ce code.

## Étape 1 : Définir le chemin du répertoire de documents

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Assurez-vous de spécifier le chemin d'accès correct à votre répertoire de documents contenant les`Hyperlinks.docx` déposer.

## Étape 2 : Chargez le document contenant les liens hypertexte

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Ici, nous créons une instance de`Document` class à partir du fichier spécifié.

## Étape 3 : Parcourir les champs pour rechercher des hyperliens

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Certains hyperliens peuvent être locaux (liens vers des signets à l'intérieur du document), nous les ignorons.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com" ;
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Cette boucle parcourt tous les champs du document à la recherche de champs de type`FieldType.FieldHyperlink` . Une fois qu'un champ de ce type est trouvé, nous vérifions s'il s'agit d'un lien local en cochant la`SubAddress` propriété. Sinon, nous remplaçons l'adresse du lien par`"http://www.aspose.com"`et le résultat avec`"Aspose - The .NET & Java Component Editor"`.

## Étape 4 : Enregistrer le document modifié

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Enfin, nous enregistrons le document modifié avec les hyperliens remplacés vers un fichier spécifié.

### Exemple de code source pour remplacer les hyperliens par Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Certains hyperliens peuvent être locaux (liens vers des signets à l'intérieur du document), nous les ignorons.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com" ;
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Ceci est un exemple de code source pour remplacer les liens hypertexte dans un document à l'aide d'Aspose.Words pour .NET.