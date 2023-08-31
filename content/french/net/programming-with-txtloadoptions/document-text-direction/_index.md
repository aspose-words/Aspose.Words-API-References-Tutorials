---
title: Sens du texte du document
linktitle: Sens du texte du document
second_title: API de traitement de documents Aspose.Words
description: Apprenez à spécifier la direction du texte dans vos documents avec Aspose.Words pour .NET. Améliorer l'affichage pour les langues de droite à gauche.
type: docs
weight: 10
url: /fr/net/programming-with-txtloadoptions/document-text-direction/
---

Dans ce didacticiel, nous allons explorer le code source C# fourni pour la fonctionnalité "Direction du texte du document" avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de spécifier la direction du texte dans un document, ce qui est particulièrement utile pour les langues qui s'écrivent de droite à gauche, telles que l'hébreu ou l'arabe.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words pour .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Configurer les options de téléchargement

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 Dans cette étape, nous configurons les options de chargement du document. Nous créons un nouveau`TxtLoadOptions` objet et définissez le`DocumentDirection` propriété à`DocumentDirection.Auto`. Cette valeur indique à Aspose.Words de déterminer automatiquement la direction du texte en fonction du contenu du document.

## Étape 3 : Chargement du document

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` méthode et en passant le chemin vers le fichier texte à charger. Nous utilisons également les options de chargement spécifiées.

## Étape 4 : Manipuler le paragraphe et afficher le sens du texte

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 Dans cette étape, nous accédons au premier paragraphe du document en utilisant le`FirstSection` et`Body` propriétés. Ensuite, nous accédons au`ParagraphFormat.Bidi` propriété pour obtenir la direction du texte du paragraphe. Nous affichons ensuite cette valeur dans la console.

## Étape 5 : Enregistrez le document

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Dans cette dernière étape, nous enregistrons le document résultant au format .docx en utilisant le`Save` méthode et en passant le chemin vers le fichier de sortie.

Vous pouvez maintenant exécuter le code source pour charger le document texte et déterminer la direction du texte. Le document résultant sera enregistré dans le répertoire spécifié avec le nom "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Exemple de code source pour la fonctionnalité de direction du texte du document avec Aspose.Words pour .NET.


```csharp

            
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de direction du texte du document dans Aspose.Words pour .NET. Nous avons appris à spécifier la direction du texte dans un document, en particulier pour les langues qui s'écrivent de droite à gauche, comme l'hébreu ou l'arabe.

Cette fonctionnalité est essentielle pour s'assurer que le texte s'affiche correctement dans les documents multilingues. En utilisant les options de chargement appropriées, Aspose.Words peut détecter automatiquement la direction du texte et l'appliquer au document.

Avec Aspose.Words, vous pouvez facilement manipuler la direction du texte dans vos documents, offrant une expérience de lecture fluide et intuitive aux utilisateurs.

Il est important de noter que cette fonctionnalité est particulièrement utile lors du traitement de texte avec des langues qui nécessitent une direction de texte spécifique. Aspose.Words facilite cette tâche en fournissant des outils puissants pour gérer la direction du texte dans vos documents.

N'oubliez pas d'utiliser les options de chargement appropriées, telles que la définition de l'orientation automatique du texte, pour obtenir les résultats souhaités dans vos documents.

Aspose.Words pour .NET offre de nombreuses fonctionnalités avancées pour la manipulation et la génération de documents. En explorant davantage la documentation et les exemples fournis par Aspose.Words, vous pourrez exploiter pleinement les capacités de cette puissante bibliothèque.

Alors, n'hésitez pas à intégrer la direction du texte du document dans vos projets Aspose.Words pour .NET et profitez de ses avantages pour créer des documents multilingues attrayants et de haute qualité.