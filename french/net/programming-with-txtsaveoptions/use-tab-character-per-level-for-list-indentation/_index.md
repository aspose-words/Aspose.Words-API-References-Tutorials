---
title: Utiliser le caractère de tabulation par niveau pour l'indentation de la liste
linktitle: Utiliser le caractère de tabulation par niveau pour l'indentation de la liste
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser les listes de retrait avec la fonction de caractères de tabulation dans Aspose.Words pour .NET. Gagnez du temps et améliorez votre flux de travail avec cette fonctionnalité puissante.
type: docs
weight: 10
url: /fr/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

Dans ce didacticiel, nous allons explorer le code source C # fourni pour la fonctionnalité "Utiliser un caractère de tabulation par niveau pour l'indentation de la liste" avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'appliquer des caractères de tabulation pour l'indentation des listes à chaque niveau, offrant une plus grande flexibilité et un meilleur contrôle sur l'apparence de vos documents.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words pour .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Etape 2 : Création du document et du générateur

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dans cette étape, nous créons un nouveau`Document` objet et un objet associé`DocumentBuilder` objet. Ces objets nous permettront de manipuler et de générer notre document.

## Étape 3 : Création d'une liste avec trois niveaux d'indentation

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

 Dans cette étape, nous appliquons le format par défaut des numéros de liste en utilisant le`ApplyNumberDefault()` méthode du formateur de liste. Ensuite, nous ajoutons trois éléments à notre liste en utilisant le générateur de documents`Writeln()` et`Write()` méthodes. Nous utilisons le`ListIndent()` méthode pour incrémenter l'indentation à chaque niveau.

## Étape 4 : Configurer les options d'enregistrement

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 Dans cette étape, nous configurons les options d'enregistrement du document. Nous créons un nouveau`TxtSaveOptions` objet et définissez le`ListIndentation.Count`propriété sur 1 pour spécifier le nombre de caractères de tabulation par niveau d'indentation. Nous fixons également le`ListIndentation.Character` propriété à '\t' pour spécifier que nous voulons utiliser des caractères de tabulation.

## Étape 5 : Enregistrez le document

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 Dans cette dernière étape, nous enregistrons le document avec les options d'enregistrement spécifiées. Nous utilisons le`Save()` méthode du document en passant le chemin complet du fichier de sortie et les options d'enregistrement.


Vous pouvez maintenant exécuter le code source pour générer un document avec une indentation de liste à l'aide de caractères de tabulation. Le fichier de sortie sera enregistré dans le répertoire spécifié avec le nom "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt".

### Exemple de source de code pour la fonctionnalité Utiliser un caractère de tabulation par niveau pour l'indentation de la liste avec Aspose.Words pour .NET :

```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Créer une liste avec trois niveaux d'indentation
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

Maintenant que vous avez fini de générer votre document avec une indentation de liste à l'aide de caractères de tabulation, vous pouvez utiliser Markdown pour formater le contenu de votre article. Assurez-vous d'utiliser les balises de mise en forme appropriées pour mettre en évidence les titres, les sous-titres et le code source inclus.