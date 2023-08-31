---
title: Remplacer les hyperliens
linktitle: Remplacer les hyperliens
second_title: API de traitement de documents Aspose.Words
description: Remplacez les hyperliens dans les documents Word à l'aide d'Aspose.Words pour .NET. Instructions étape par étape pour remplacer les hyperliens.
type: docs
weight: 10
url: /fr/net/working-with-fields/replace-hyperlinks/
---

Voici un guide étape par étape pour expliquer le code source C# suivant pour remplacer les hyperliens à l'aide de la fonctionnalité Aspose.Words pour .NET. Assurez-vous d'avoir inclus la bibliothèque Aspose.Words dans votre projet avant d'utiliser ce code.

## Étape 1 : Définir le chemin du répertoire du document

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Assurez-vous de spécifier le chemin correct vers votre répertoire de documents contenant le`Hyperlinks.docx` déposer.

## Étape 2 : Charger le document contenant les hyperliens

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Ici, nous créons une instance du`Document` classe à partir du fichier spécifié.

## Étape 3 : Parcourir les champs pour trouver des hyperliens

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Certains hyperliens peuvent être locaux (liens vers des favoris à l'intérieur du document), nous les ignorons.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com" ;
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Cette boucle parcourt tous les champs du document à la recherche de champs de type`FieldType.FieldHyperlink` . Une fois qu'un champ de ce type est trouvé, on vérifie s'il s'agit d'un lien local en cochant la case`SubAddress` propriété. Sinon, nous remplaçons l'adresse du lien par`"http://www.aspose.com"` et le résultat avec`"Aspose - The .NET & Java Component Editor"`.

## Étape 4 : Enregistrez le document modifié

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Enfin, nous enregistrons le document modifié avec les hyperliens remplacés vers un fichier spécifié.

### Exemple de code source pour remplacer les hyperliens par Aspose.Words pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Certains hyperliens peuvent être locaux (liens vers des favoris à l'intérieur du document), nous les ignorons.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com" ;
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Il s'agit d'un exemple de code source pour remplacer les hyperliens dans un document à l'aide d'Aspose.Words pour .NET.

### FAQ

#### Q : Comment puis-je remplacer des hyperliens dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour remplacer les hyperliens dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`Document.Range.Replace`méthode spécifiant le texte à rechercher et le texte de remplacement. Assurez-vous d'utiliser les options appropriées pour définir les paramètres de recherche et de remplacement.

#### Q : Est-il possible de remplacer uniquement certains liens hypertexte dans un document Word par Aspose.Words pour .NET ?

R : Oui, il est possible de remplacer uniquement certains hyperliens dans un document Word par Aspose.Words pour .NET. Vous pouvez filtrer les hyperliens à remplacer en utilisant des critères spécifiques, tels que l'URL du lien, le texte du lien ou toute autre propriété pertinente. Vous pouvez ensuite appliquer le remplacement uniquement aux liens hypertexte correspondants.

#### Q : Comment puis-je ignorer les hyperliens dans les en-têtes, les pieds de page ou les notes de bas de page lors du remplacement par Aspose.Words pour .NET ?

R : Pour ignorer les hyperliens dans les en-têtes, les pieds de page ou les notes de bas de page lors du remplacement par Aspose.Words for .NET, vous pouvez utiliser les options de recherche avancées et spécifier les limites de recherche appropriées. Par exemple, vous pouvez limiter la recherche aux principales sections du document et exclure les en-têtes, les pieds de page ou les notes de bas de page.

#### Q : Est-il possible de remplacer les hyperliens par des liens internes vers d’autres parties du document ?

 R : Oui, il est possible de remplacer les hyperliens par des liens internes vers d'autres parties du document avec Aspose.Words pour .NET. Vous pouvez utiliser des ancres ou des identifiants de texte pour créer des liens internes, puis les remplacer à l'aide du`Document.Range.Replace` méthode avec les options appropriées.

#### Q : Le remplacement des hyperliens par Aspose.Words pour .NET préserve-t-il les propriétés des liens, telles que les couleurs ou les styles ?

R : Oui, lors du remplacement des hyperliens par Aspose.Words for .NET, les propriétés des liens telles que les couleurs ou les styles sont conservées. Vous pouvez spécifier les mêmes propriétés de mise en forme dans le texte de remplacement pour obtenir un résultat cohérent.