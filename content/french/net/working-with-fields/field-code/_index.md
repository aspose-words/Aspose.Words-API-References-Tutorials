---
title: Code de champ
linktitle: Code de champ
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour obtenir le code de champ et le résultat du champ dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/field-code/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité « Obtenir le code de champ » d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez préciser le répertoire de vos documents. Remplacez la valeur « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargement du document

La première étape consiste à télécharger le document dans lequel vous souhaitez obtenir les codes de champ.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Assurez-vous de remplacer "Hyperlinks.docx" par le nom de votre propre fichier.

## Étape 3 : Parcourir les champs du document

 Nous utilisons un`foreach`loop pour parcourir tous les champs présents dans le document.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 A chaque itération de la boucle, on obtient le code du champ en utilisant le`GetFieldCode()` méthode. Nous stockons également le résultat du champ dans une variable.

### Exemple de code source pour obtenir le code de champ avec Aspose.Words pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chargez le document.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Parcourez les champs du document.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Faites quelque chose avec le code et le résultat du champ.
}
```

Dans cet exemple, nous avons chargé un document puis parcouru tous les champs présents dans le document. A chaque itération, nous obtenions le code et le résultat du champ. Vous pouvez ajouter votre propre logique pour traiter les champs de code et de résultat selon vos besoins.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité « Obtenir le code de champ » avec Aspose.Words pour .NET.

### FAQ

#### Q : Comment puis-je insérer un champ dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour insérer un champ dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`DocumentBuilder.InsertField` méthode spécifiant le code de champ approprié. Par exemple, vous pouvez utiliser`builder.InsertField("MERGEFIELD CustomerName")`pour insérer un champ de fusion dans le document.

#### Q : Comment puis-je mettre à jour les champs d'un document à l'aide d'Aspose.Words pour .NET ?

 R : Pour mettre à jour les champs du document à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`Document.UpdateFields` méthode. Cela mettra à jour tous les champs présents dans le document, tels que les champs de fusion, les champs de date, etc.

#### Q : Comment puis-je récupérer la valeur d'un champ spécifique dans Aspose.Words pour .NET ?

 R : Pour récupérer la valeur d'un champ spécifique dans Aspose.Words for .NET, vous pouvez utiliser le`Field.GetResult` méthode en spécifiant l'index du champ dans la`Document.Range.Fields` collection. Par exemple, vous pouvez utiliser`string value = document.Range.Fields[0].GetResult()` pour récupérer la valeur du premier champ du document.

#### Q : Comment puis-je supprimer un champ d'un document à l'aide d'Aspose.Words pour .NET ?

 R : Pour supprimer un champ d'un document à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`Field.Remove` méthode spécifiant le`Field` objet que vous souhaitez supprimer. Cela supprimera le champ du document.