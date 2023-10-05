---
title: Insérer une table des matières dans un document Word
linktitle: Insérer une table des matières dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer une table des matières dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-table-of-contents/
---
Dans ce didacticiel complet, vous apprendrez à insérer une table des matières dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de générer une table des matières avec les titres et les numéros de page appropriés.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer une table des matières
Ensuite, utilisez la méthode InsertTableOfContents de la classe DocumentBuilder pour insérer une table des matières. Spécifiez les options de formatage requises dans la méthode :

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Étape 3 : Ajouter le contenu du document
Après avoir inséré la table des matières, ajoutez le contenu réel du document. Définissez les styles de titre appropriés à l'aide de StyleIdentifier :

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Étape 4 : mettre à jour la table des matières
La table des matières nouvellement insérée sera initialement vide. Pour le renseigner, mettez à jour les champs du document :

```csharp
doc.UpdateFields();
```

## Étape 5 : Enregistrez le document
Après avoir inséré la table des matières et mis à jour les champs, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Exemple de code source pour insérer une table des matières à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour insérer une table des matières à l'aide d'Aspose.Words for .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialiser DocumentBuilder avec l'objet Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérer une table des matières
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Commencez le contenu réel du document sur la deuxième page.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// La table des matières nouvellement insérée sera initialement vide.
// Il doit être rempli en mettant à jour les champs du document.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment insérer une table des matières dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en utilisant le code source fourni, vous pouvez désormais générer une table des matières avec les titres et numéros de page appropriés pour vos documents.

### FAQ pour insérer une table des matières dans un document Word

#### Q : Puis-je personnaliser l’apparence de la table des matières ?

 R : Oui, vous pouvez personnaliser l'apparence de la table des matières en modifiant les options de formatage spécifiées dans le`InsertTableOfContents` méthode. Les paramètres vous permettent de contrôler les numéros de page, l'indentation et d'autres styles.

#### Q : Que faire si je souhaite inclure des niveaux de titres spécifiques dans la table des matières ?

 R : Vous pouvez spécifier les niveaux de titre souhaités à inclure dans la table des matières en ajustant la valeur dans le champ`InsertTableOfContents` méthode. Par exemple, en utilisant`"\\o \"1-3\""` comprendra les niveaux de titres 1 à 3.

#### Q : Puis-je mettre à jour automatiquement la table des matières si j'apporte des modifications au contenu du document ?

 R : Oui, vous pouvez mettre à jour automatiquement la table des matières en appelant le`UpdateFields` méthode sur le document. Cela garantira que toutes les modifications apportées au contenu du document, telles que l'ajout ou la suppression de titres, sont reflétées dans la table des matières.

#### Q : Comment puis-je styliser différemment les niveaux de titre dans la table des matières ?

 R : Vous pouvez styliser les niveaux de titre différemment en utilisant différents styles de paragraphe pour chaque niveau de titre. En attribuant différents`StyleIdentifier` valeurs à la`ParagraphFormat` de la`DocumentBuilder`, vous pouvez créer des styles distincts pour chaque niveau de titre.

#### Q : Est-il possible d'ajouter une mise en forme supplémentaire aux titres de la table des matières ?

 R : Oui, vous pouvez ajouter une mise en forme supplémentaire aux en-têtes de la table des matières, comme des styles de police, des couleurs ou d'autres propriétés. En ajustant le`Font` propriétés du`DocumentBuilder`, vous pouvez appliquer une mise en forme personnalisée aux titres.