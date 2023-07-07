---
title: Vérifier le document Word crypté
linktitle: Vérifier le document Word crypté
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour vérifier qu'un document Word est crypté avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-fileformat/verify-encrypted-document/
---

Cet article fournit un guide étape par étape sur l'utilisation de la fonctionnalité de vérification de document Word crypté avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment vérifier si un document est crypté.

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

## Questions fréquemment posées

### Q : Quelles sont les étapes pour vérifier un document Word chiffré ?

Les étapes pour vérifier un document Word crypté sont les suivantes :

Définissez le répertoire des documents.

Détecter le format de fichier.

Vérifiez si le document est crypté.

### Q : Comment puis-je définir le répertoire de documents ?
 Pour définir le répertoire des documents, vous devez remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire de documents dans le code suivant :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Q : Comment détecter le format de fichier ?
 Vous pouvez utiliser le`DetectFileFormat` méthode de la`FileFormatUtil` classe pour détecter les informations de format de fichier. Dans l'exemple suivant, nous supposons que le document chiffré s'appelle "Encrypted.docx" et se trouve dans le répertoire de documents spécifié :

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### Q : Comment vérifier si le document est crypté ?
 Vous pouvez utiliser le`IsEncrypted` propriété de la`FileFormatInfo` objet pour vérifier si le document est crypté. Cette propriété renvoie`true` si le document est crypté, sinon il renvoie`false`. Le résultat s'affiche dans la console :

```csharp
Console.WriteLine(info.IsEncrypted);
```

### Q : Comment vérifier si un document est crypté avec Aspose.Words pour .NET ?
En suivant les étapes mentionnées dans ce didacticiel et en exécutant le code source fourni, vous pouvez vérifier si un document est chiffré à l'aide de Aspose.Words pour .NET.
