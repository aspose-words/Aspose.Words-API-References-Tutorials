---
title: Vérifier le document crypté
linktitle: Vérifier le document crypté
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour vérifier qu'un document est crypté avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-fileformat/verify-encrypted-document/
---

Cet article fournit un guide étape par étape sur l'utilisation de la fonctionnalité de vérification de document crypté avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment vérifier si un document est crypté.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Détecter le format de fichier

 Ensuite, nous utilisons le`DetectFileFormat` méthode de la`FileFormatUtil` classe pour détecter les informations de format de fichier. Dans cet exemple, nous supposons que le document crypté s'appelle "Encrypted.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Étape 3 : Vérifiez si le document est crypté

 Nous utilisons le`IsEncrypted` propriété de la`FileFormatInfo` objet pour vérifier si le document est crypté. Cette propriété renvoie`true` si le document est crypté, sinon il renvoie`false`. Nous affichons le résultat dans la console.

```csharp
Console.WriteLine(info.IsEncrypted);
```

C'est tout ! Vous avez vérifié avec succès si un document est crypté à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour vérifier les documents chiffrés avec Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```
