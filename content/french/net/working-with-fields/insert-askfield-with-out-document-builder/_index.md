---
title: Insérer ASKField sans Document Builder
linktitle: Insérer ASKField sans Document Builder
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un champ ASK dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité « Insérer un champ ASK sans DocumentBuilder » d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez préciser le répertoire de vos documents. Remplacez la valeur « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et du paragraphe

Nous commençons par créer un nouveau document et récupérer le premier paragraphe.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Étape 3 : Insérer le champ ASK

 Nous utilisons le`AppendField()` méthode pour insérer un champ ASK dans le paragraphe.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

On configure ensuite les différentes propriétés du champ ASK en précisant les valeurs souhaitées.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ.

```csharp
field. Update();
```

### Exemple de code source pour insérer un champ ASK sans DocumentBuilder avec Aspose.Words pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Création de documents.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insérez le champ ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Dans cet exemple, nous avons créé un nouveau document, inséré un champ ASK sans utiliser DocumentBuilder, configuré les différentes propriétés du champ et enregistré le document sous un nom de fichier spécifié.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité « Insérer un champ ASK sans DocumentBuilder » avec Aspose.Words pour .NET.

### FAQ

#### Q : Qu'est-ce qu'un champ ASK dans Aspose.Words ?

R : Un champ ASK dans Aspose.Words est utilisé pour poser une question à l'utilisateur lors de l'ouverture d'un document. Il est souvent utilisé pour demander des informations ou des commentaires spécifiques qui peuvent varier d'un utilisateur à l'autre.

#### Q : Comment insérer le champ ASK dans un document Word sans utiliser Document Builder dans Aspose.Words ?

R : Pour insérer un champ ASK dans un document Word sans utiliser Document Builder dans Aspose.Words, vous pouvez suivre ces étapes :

1. Importez les classes Document et Field à partir de l’espace de noms Aspose.Words.Fields.
2. Créez une instance de Document en chargeant votre document existant.
3. Utilisez la méthode InsertField pour insérer un champ ASK en spécifiant le nom de la question.
4. Enregistrez le document.

#### Q : Comment puis-je obtenir la réponse de l'utilisateur pour un champ ASK dans un document Word ?

: Pour obtenir la réponse de l'utilisateur pour un champ ASK dans un document Word, vous pouvez utiliser la méthode GetFieldNames disponible dans la classe Document. Cette méthode renvoie une liste des noms des champs présents dans le document. Vous pouvez alors vérifier si le nom du champ ASK est présent dans la liste et récupérer la réponse associée.

#### Q : Le champ ASK peut-il être utilisé pour demander plus d’informations à l’utilisateur ?

R : Oui, le champ ASK peut être utilisé pour demander plusieurs informations à l'utilisateur. Vous pouvez insérer plusieurs champs ASK dans votre document, chacun avec une question différente. A l'ouverture du document, l'utilisateur sera invité à fournir les réponses correspondantes.