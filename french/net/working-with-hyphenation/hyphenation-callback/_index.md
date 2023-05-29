---
title: Rappel de césure
linktitle: Rappel de césure
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser le rappel de césure dans Aspose.Words pour .NET pour gérer la césure des mots.
type: docs
weight: 10
url: /fr/net/working-with-hyphenation/hyphenation-callback/
---

Dans ce tutoriel étape par étape, nous allons vous montrer comment utiliser la fonction de rappel de césure dans Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas déjà fait, téléchargez et installez la bibliothèque à partir du site officiel.

## Étape 1 : Enregistrer le rappel de césure

 Tout d'abord, nous allons enregistrer le rappel de césure à l'aide d'un`CustomHyphenationCallback` classe. Cela nous permettra de gérer la césure des mots selon nos propres règles :

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Assurez-vous d'avoir implémenté le`CustomHyphenationCallback`classe selon vos besoins spécifiques.

## Étape 2 : Chargement du document et application de la césure

Ensuite, chargez votre document à partir du répertoire spécifié et coupez les mots à l'aide de Aspose.Words :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Étape 3 : Gérer les erreurs de dictionnaire manquantes

S'il manque un dictionnaire de césure, nous intercepterons l'exception correspondante et afficherons un message d'erreur :

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Étape 4 : Nettoyer et désactiver le rappel de césure

Enfin, pour plus de propreté et pour désactiver le rappel de césure, effectuez les étapes suivantes :

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Cela nettoie et désactive le rappel de césure après avoir terminé le traitement.

Donc ! Vous avez utilisé avec succès le rappel de césure dans Aspose.Words pour .NET.

### Exemple de code source pour le rappel de césure avec Aspose.Words pour .NET

```csharp
try
{
	 // Enregistrez le rappel de césure.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.