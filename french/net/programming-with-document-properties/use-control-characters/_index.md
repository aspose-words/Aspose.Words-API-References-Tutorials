---
title: Utiliser les caractères de contrôle
linktitle: Utiliser les caractères de contrôle
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour l'utilisation des caractères de contrôle avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-properties/use-control-characters/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C # pour l'utilisation de caractères de contrôle avec Aspose.Words pour .NET. Cette fonction vous permet de manipuler les caractères de contrôle dans le texte.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Utiliser les caractères de contrôle

Dans cette étape, nous allons utiliser des caractères de contrôle dans un texte. Utilisez le code suivant :

```csharp
const string text = "test\r";
// Remplacez le caractère de contrôle "\r" par "\r\n".
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Ce code définit un`text` chaîne contenant le caractère de contrôle "\r" (nouvelle ligne) et utilise le`Replace` pour le remplacer par le caractère de contrôle "\r\n" (newline). ligne suivie d'un saut de ligne).

### Exemple de code source pour Utiliser des caractères de contrôle avec Aspose.Words pour .NET

```csharp

	const string text = "test\r";
	// Remplacez le caractère de contrôle "\r" par "\r\n".
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 Vous pouvez utiliser le code ci-dessus dans votre propre projet en remplaçant le`text` chaîne avec votre propre texte contenant des caractères de contrôle.

Vous avez maintenant appris à utiliser les caractères de contrôle avec Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement manipuler les caractères de contrôle dans vos propres applications.