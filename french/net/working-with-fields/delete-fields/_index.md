---
title: Supprimer les champs
linktitle: Supprimer les champs
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour supprimer des champs de fusion dans vos documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/delete-fields/
---

Pour expliquer comment utiliser la fonctionnalité "Supprimer les champs" dans Aspose. Words for .NET, nous avons créé un guide étape par étape ci-dessous. 

Il est important de suivre chaque étape de près afin d'obtenir les résultats souhaités. 

## Étape 1 : Création d'un nouveau document

Dans cet extrait de code, nous commençons par créer un nouveau document vide en utilisant la ligne suivante : 

```csharp
Document doc = new Document();
```

## Étape 2 : supprimer les champs de fusion

 Pour supprimer tous les champs de fusion présents dans le document, nous utilisons le`DeleteFields()` fonction. 

Ceci est particulièrement utile si vous souhaitez conserver uniquement le contenu statique et supprimer toute information de fusion. 

### Exemple de code source pour supprimer des champs avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document existant.
Document doc = new Document(dataDir + "YourDocument.docx");

// Supprimer les champs de fusion.
doc.MailMerge.DeleteFields();

// Enregistrez le document modifié.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 Dans notre exemple, nous chargeons d'abord un document existant avant d'appeler`DeleteFields()`. Enfin, nous enregistrons le document modifié avec un nouveau nom de fichier. 

Afin de supprimer efficacement les champs de fusion d'un document à l'aide de la fonctionnalité "Supprimer les champs" d'Aspose.Words pour .NET, inspirez-vous de cet exemple. 

N'oubliez pas de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par votre chemin de répertoire spécifique. 

Notre guide sur la mise en œuvre de la fonctionnalité "Supprimer les champs" via Aspose.Words pour .NET est ainsi terminé.