---
title: Créer un en-tête de pied de page
linktitle: Créer un en-tête de pied de page
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter et personnaliser des en-têtes et des pieds de page dans des documents Word à l'aide d'Aspose.Words pour .NET. Ce guide étape par étape garantit un formatage professionnel des documents.
type: docs
weight: 10
url: /fr/net/working-with-headers-and-footers/create-header-footer/
---

L'ajout d'en-têtes et de pieds de page à vos documents peut améliorer leur professionnalisme et leur lisibilité. Avec Aspose.Words pour .NET, vous pouvez facilement créer et personnaliser des en-têtes et des pieds de page pour vos documents Word. Dans ce didacticiel, nous vous guiderons pas à pas tout au long du processus, afin de vous assurer que vous pouvez mettre en œuvre ces fonctionnalités de manière transparente.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

-  Aspose.Words pour .NET : téléchargez et installez à partir du[lien de téléchargement](https://releases.aspose.com/words/net/).
- Environnement de développement : tel que Visual Studio, pour écrire et exécuter votre code.
- Connaissance de base de C# : Compréhension de C# et du framework .NET.
- Exemple de document : un exemple de document pour appliquer les en-têtes et les pieds de page, ou en créer un nouveau, comme indiqué dans le didacticiel.

## Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires pour accéder aux classes et méthodes Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## Étape 1 : Définir le répertoire des documents

Définissez le répertoire dans lequel votre document sera enregistré. Cela aide à gérer efficacement le chemin.

```csharp
// Le chemin d'accès au répertoire des documents
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## Étape 2 : Créer un nouveau document

 Créez un nouveau document et un`DocumentBuilder` pour faciliter l’ajout de contenu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : configurer la mise en page

Configurez les paramètres de la page, notamment si la première page aura un en-tête/pied de page différent.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## Étape 4 : ajouter un en-tête à la première page

Accédez à la section d’en-tête de la première page et configurez le texte d’en-tête.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## Étape 5 : ajouter un en-tête principal

Accédez à la section d’en-tête principale et insérez une image et du texte.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Insérer une image dans l'en-tête
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## Étape 6 : ajouter un pied de page principal

Accédez à la section de pied de page principale et créez un tableau pour formater le contenu du pied de page.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Ajouter une numérotation des pages
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();
```

## Étape 7 : ajouter du contenu et des sauts de page

Accédez à la fin du document, ajoutez un saut de page et créez une nouvelle section avec des paramètres de page différents.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## Étape 8 : Copier les en-têtes et les pieds de page de la section précédente

Si vous souhaitez réutiliser les en-têtes et pieds de page d'une section précédente, copiez-les et appliquez les modifications nécessaires.

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## Conclusion

En suivant ces étapes, vous pouvez ajouter et personnaliser efficacement des en-têtes et des pieds de page dans vos documents Word à l'aide d'Aspose.Words pour .NET. Cela améliore l'apparence et le professionnalisme de votre document, le rendant plus lisible et plus attrayant.

## FAQ

### Q1 : Qu'est-ce qu'Aspose.Words pour .NET ?

Aspose.Words for .NET est une bibliothèque qui permet aux développeurs de créer, modifier et convertir des documents Word par programme dans des applications .NET.

### Q2 : Puis-je ajouter des images à l’en-tête ou au pied de page ?

 Oui, vous pouvez facilement ajouter des images à l'en-tête ou au pied de page en utilisant le`DocumentBuilder.InsertImage` méthode.

### Q3 : Comment définir différents en-têtes et pieds de page pour la première page ?

 Vous pouvez définir différents en-têtes et pieds de page pour la première page en utilisant le`DifferentFirstPageHeaderFooter` propriété du`PageSetup` classe.

### Q4 : Où puis-je trouver plus de documentation sur Aspose.Words ?

 Vous pouvez trouver une documentation complète sur le[Page de documentation de l'API Aspose.Words](https://reference.aspose.com/words/net/).

### Q5 : Existe-t-il une assistance disponible pour Aspose.Words ?

 Oui, Aspose offre une assistance via son[forum d'entraide](https://forum.aspose.com/c/words/8).
