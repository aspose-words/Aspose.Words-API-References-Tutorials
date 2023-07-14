---
title: Rappel de césure
linktitle: Rappel de césure
second_title: API de traitement de documents Aspose.Words
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

### FAQ

#### Q : Qu'est-ce qu'un rappel de syllabation dans Aspose.Words ?

R : Un rappel de syllabation dans Aspose.Words est une fonctionnalité qui vous permet de personnaliser la manière dont les mots sont syllabisés dans vos documents. En utilisant un rappel de syllabation, vous pouvez spécifier des règles personnalisées pour la syllabation des mots, ce qui peut être utile pour des langues spécifiques ou des scénarios particuliers où la syllabation par défaut ne produit pas les résultats souhaités.

#### Q : Comment définir un rappel de syllabation dans Aspose.Words ?

 R : Pour définir un rappel de césure dans Aspose.Words, vous devez créer une classe qui implémente le`HyphenationCallback` interfacer et implémenter`HandleWord()` méthode. Cette méthode sera appelée pour chaque mot rencontré lors de la syllabation. Vous pouvez lui appliquer des règles de syllabisation personnalisées et renvoyer le mot syllabisé. Ensuite, vous pouvez lier votre rappel de césure en utilisant le`Document.HyphenationCallback` propriété de votre document.

#### Q : Quel est l'avantage d'utiliser un rappel de syllabation dans Aspose.Words ?

R : L'avantage d'utiliser un rappel de syllabation dans Aspose.Words est la possibilité de personnaliser la façon dont les mots sont syllabisés dans vos documents. Cela vous donne plus de contrôle sur la syllabation, en particulier pour des langues ou des scénarios spécifiques où la syllabation par défaut ne donne pas les résultats souhaités. Vous pouvez appliquer des règles spécifiques à chaque mot pour obtenir une syllabation précise selon vos besoins.

#### Q : Quels sont les scénarios courants où l'utilisation d'un rappel de syllabation peut être utile ?

R : L'utilisation d'un booster de syllabation peut être utile dans plusieurs scénarios, tels que :
- Syllabisation de mots dans des langues spécifiques qui ont des règles de syllabation particulières.
- L'application de règles de syllabation personnalisées pour les acronymes ou les mots techniques.
- Adaptation de la syllabation selon les préférences stylistiques ou les normes typographiques.

#### Q : Comment puis-je tester la syllabisation personnalisée avec un rappel de syllabation dans Aspose.Words ?

R : Pour tester la syllabation personnalisée avec un rappel de syllabation dans Aspose.Words, vous pouvez créer un document de test contenant des mots pour lesquels vous souhaitez appliquer des règles de syllabation personnalisées. Ensuite, vous pouvez définir votre rappel de syllabisation personnalisé, appeler le`Document.Range.Replace()` méthode pour remplacer les mots dans le document, et utilisez la méthode`Hyphenate()` méthode de la`Hyphenation` class pour obtenir la syllabation des mots. Vous pouvez ensuite formater les mots syllabés selon vos besoins, par exemple en ajoutant des tirets entre les syllabes.