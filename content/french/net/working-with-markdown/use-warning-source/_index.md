---
title: Utiliser la source d'avertissement
linktitle: Utiliser la source d'avertissement
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment utiliser la source d'avertissement avec le guide étape par étape d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/use-warning-source/
---

Dans cet exemple, nous allons vous montrer comment utiliser la source d'avertissement avec Aspose.Words pour .NET. La source de l'avertissement indique l'origine de l'avertissement lors de l'utilisation de la fonction de rappel.

## Étape 1 : Chargement du document

 Nous allons charger un document existant contenant des avertissements en utilisant le`Load` méthode du`Document` classe.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Étape 3 : Utilisation de la source d'avertissement

 Nous utiliserons la source d'avertissement en définissant le paramètre du document`WarningCallback` propriété à une collection de`WarningInfo` objets.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Étape 4 : Sauvegarde du document

Enfin, nous pouvons enregistrer le document au format souhaité.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Exemple de code source pour l'utilisation de la source d'avertissement avec Aspose.Words pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Félicitation ! Vous avez maintenant appris à utiliser la source d'avertissement avec Aspose.Words for .NET.

### FAQ

#### Q : Pouvons-nous personnaliser l'apparence de la balise « Avertissement » ?

 R : Le formatage de la balise « Avertissement » dépend du moteur de rendu Markdown utilisé. Dans la plupart des cas, vous pouvez personnaliser l'apparence en utilisant CSS pour cibler le`blockquote` balise dans votre document.

#### Q : Est-il possible d'ajouter des icônes à la balise « Avertissement » ?

 : Oui, il est possible d'ajouter des icônes à la balise « Avertissement » à l'aide du code HTML dans votre document Markdown. Vous pouvez insérer un`span` balisez avec la classe appropriée pour afficher une icône à côté du texte d’avertissement.

#### Q : La balise « Avertissement » est-elle compatible avec tous les lecteurs Markdown ?

 R : La compatibilité de la balise « Warning » dépend du rendu Markdown utilisé. La plupart des lecteurs Markdown prendront en charge le`blockquote` balise pour afficher le texte en surbrillance, mais l’apparence exacte peut varier.