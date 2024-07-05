---
title: Insérer un champ Inclure du texte sans Document Builder
linktitle: Insérer FieldIncludeText sans Document Builder
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un champ FieldIncludeText dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité « Insérer un champ FieldIncludeText » d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez préciser le répertoire de vos documents. Remplacez la valeur « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et du paragraphe

Nous commençons par créer un nouveau document et initialiser un paragraphe.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Étape 3 : Insertion du champ FieldIncludeText

 Nous utilisons le`AppendField()` méthode pour insérer un champ FieldIncludeText dans le paragraphe.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

On configure ensuite les propriétés du champ FieldIncludeText en précisant le nom du signet et le nom du fichier source.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Ensuite, nous ajoutons le paragraphe au corps du document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ.

```csharp
fieldIncludeText.Update();
```

### Exemple de code source pour insérer un champ FieldIncludeText avec Aspose.Words pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et le paragraphe.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Insérez le champ FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

Dans cet exemple, nous avons créé un nouveau document, initialisé un paragraphe, inséré un FieldIncludeTexten spécifiant le nom du signet et le nom du fichier source, et enregistré le document avec un nom de fichier spécifié.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité « Insérer un FieldIncludeText » avec Aspose.Words pour .NET.

### FAQ

#### Q : Comment puis-je spécifier le fichier source pour le champ d'inclusion de texte dans Aspose.Words pour .NET ?

 R : Pour spécifier le fichier source du champ d'inclusion de texte dans Aspose.Words for .NET, vous pouvez utiliser le`FieldIncludeText.SourceFullName`propriété pour définir le chemin complet du fichier source. Assurez-vous que le fichier source est accessible et contient le contenu que vous souhaitez inclure dans le champ d'inclusion de texte.

#### Q : Puis-je inclure le texte d'une macro dans le champ d'inclusion de texte avec Aspose.Words pour .NET ?

 R : Oui, vous pouvez inclure le texte d'une macro dans le champ d'inclusion de texte avec Aspose.Words for .NET. Vous pouvez utiliser le`FieldIncludeText.IncludeText` propriété pour spécifier le nom de la macro dont le contenu doit être inclus dans le champ.

#### Q : L'insertion d'un champ d'inclusion de texte sans le générateur de documents affecte-t-elle la structure du document Word avec Aspose.Words pour .NET ?

R : L'insertion d'un champ d'inclusion de texte sans le générateur de document n'affecte pas directement la structure du document Word. Cependant, il ajoute un nouvel élément field au contenu du document. Vous pouvez manipuler la structure du document en ajoutant, supprimant ou modifiant les éléments existants selon vos besoins.

#### : Puis-je personnaliser l'apparence du champ d'inclusion de texte dans un document Word avec Aspose.Words pour .NET ?

R : Le champ d'inclusion de texte ne personnalise pas directement son apparence dans un document Word. Toutefois, vous pouvez formater le texte inclus à l'aide des propriétés de paragraphe, des propriétés de police et d'autres objets de mise en forme disponibles dans Aspose.Words for .NET.