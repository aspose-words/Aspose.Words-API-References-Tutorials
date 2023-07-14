---
title: Remplacer les hyperliens
linktitle: Remplacer les hyperliens
second_title: API de traitement de documents Aspose.Words
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

 Cette boucle parcourt tous les champs du document à la recherche de champs de type`FieldType.FieldHyperlink` . Une fois qu'un champ de ce type est trouvé, nous vérifions s'il s'agit d'un lien local en cochant la`SubAddress` propriété. Sinon, nous remplaçons l'adresse du lien par`"http://www.aspose.com"` et le résultat avec`"Aspose - The .NET & Java Component Editor"`.

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

### FAQ

#### Q : Comment puis-je remplacer des liens hypertexte dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour remplacer des liens hypertexte dans un document Word à l'aide d'Aspose.Words pour .NET, vous pouvez utiliser le`Document.Range.Replace`méthode spécifiant le texte à rechercher et le texte de remplacement. Veillez à utiliser les options appropriées pour définir les paramètres de recherche et de remplacement.

#### Q : Est-il possible de remplacer uniquement certains hyperliens dans un document Word par Aspose.Words pour .NET ?

R : Oui, il est possible de remplacer uniquement certains hyperliens dans un document Word avec Aspose.Words pour .NET. Vous pouvez filtrer les hyperliens à remplacer à l'aide de critères spécifiques, tels que l'URL du lien, le texte du lien ou toute autre propriété pertinente. Ensuite, vous pouvez appliquer le remplacement uniquement aux hyperliens correspondants.

#### Q : Comment puis-je ignorer les liens hypertexte dans les en-têtes, les pieds de page ou les notes de bas de page lors du remplacement par Aspose.Words pour .NET ?

R : Pour ignorer les liens hypertexte dans les en-têtes, les pieds de page ou les notes de bas de page lors du remplacement par Aspose.Words pour .NET, vous pouvez utiliser les options de recherche avancées et spécifier les limites de recherche appropriées. Par exemple, vous pouvez limiter la recherche aux principales sections du document et exclure les en-têtes, les pieds de page ou les notes de bas de page.

#### Q : Est-il possible de remplacer les hyperliens par des liens internes vers d'autres parties du document ?

 R : Oui, il est possible de remplacer les hyperliens par des liens internes vers d'autres parties du document avec Aspose.Words pour .NET. Vous pouvez utiliser des ancres ou des identifiants de texte pour créer des liens internes, puis les remplacer à l'aide de la`Document.Range.Replace` méthode avec les options appropriées.

#### Q : Le remplacement des liens hypertexte par Aspose.Words pour .NET préserve-t-il les propriétés des liens, telles que les couleurs ou les styles ?

R : Oui, lors du remplacement des liens hypertexte par Aspose.Words pour .NET, les propriétés des liens telles que les couleurs ou les styles sont conservées. Vous pouvez spécifier les mêmes propriétés de formatage dans le texte de remplacement pour obtenir un résultat cohérent.