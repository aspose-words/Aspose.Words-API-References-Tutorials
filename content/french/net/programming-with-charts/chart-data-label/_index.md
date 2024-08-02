---
title: Personnaliser l'étiquette des données du graphique
linktitle: Personnaliser l'étiquette des données du graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment personnaliser les étiquettes de données de graphiques à l’aide d’Aspose.Words for .NET dans un guide étape par étape. Parfait pour les développeurs .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/chart-data-label/
---
## Introduction

Cherchez-vous à améliorer vos applications .NET avec des capacités de traitement de documents dynamiques et personnalisées ? Aspose.Words pour .NET pourrait bien être votre réponse ! Dans ce guide, nous approfondirons la personnalisation des étiquettes de données de graphiques à l'aide d'Aspose.Words pour .NET, une puissante bibliothèque permettant de créer, de modifier et de convertir des documents Word. Que vous soyez un développeur chevronné ou débutant, ce didacticiel vous guidera à travers chaque étape, vous assurant de comprendre comment utiliser efficacement cet outil.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Visual Studio : installez Visual Studio 2019 ou version ultérieure.
2. .NET Framework : assurez-vous que vous disposez de .NET Framework 4.0 ou version ultérieure.
3.  Aspose.Words for .NET : téléchargez et installez Aspose.Words for .NET à partir du[lien de téléchargement](https://releases.aspose.com/words/net/).
4. Connaissance de base de C# : Une connaissance de la programmation C# est essentielle.
5.  Une licence valide : obtenez une[permis temporaire](https://purchase.aspose.com/temporary-license/) ou achetez-en un chez[acheter un lien](https://purchase.aspose.com/buy).

## Importer des espaces de noms

Pour commencer, vous devez importer les espaces de noms nécessaires dans votre projet C#. Cette étape est cruciale car elle garantit que vous avez accès à toutes les classes et méthodes fournies par Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Charts;
```

## Étape 1 : initialiser le document et DocumentBuilder

Pour créer et manipuler des documents Word, nous devons d'abord initialiser une instance du`Document` classe et un`DocumentBuilder` objet.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Explication

- Document doc : crée une nouvelle instance de la classe Document.
- Générateur DocumentBuilder : Le DocumentBuilder aide à insérer du contenu dans l'objet Document.

## Étape 2 : Insérer un graphique

 Ensuite, nous insérerons un graphique à barres dans le document à l'aide de l'option`DocumentBuilder` objet.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

### Explication

- Forme de forme : représente le graphique sous forme de forme dans le document.
- builder.InsertChart(ChartType.Bar, 432, 252) : insère un graphique à barres avec les dimensions spécifiées.

## Étape 3 : Accédez à la série de graphiques

Pour personnaliser les étiquettes de données, nous devons d'abord accéder aux séries dans le graphique.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
```

### Explication

- ChartSeries series0 : Récupère la première série du graphique, que nous personnaliserons.

## Étape 4 : Personnaliser les étiquettes de données

Les étiquettes de données peuvent être personnalisées pour afficher diverses informations. Nous allons configurer les étiquettes pour afficher la clé de légende, le nom de la série et la valeur, tout en masquant le nom de la catégorie et le pourcentage.

```csharp
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

### Explication

- Étiquettes ChartDataLabelCollection : accède aux étiquettes de données de la série.
- labels.ShowLegendKey : affiche la clé de la légende.
- labels.ShowLeaderLines : affiche les lignes de repère pour les étiquettes de données positionnées bien en dehors des points de données.
- labels.ShowCategoryName : masque le nom de la catégorie.
- labels.ShowPercentage : masque la valeur en pourcentage.
- labels.ShowSeriesName : affiche le nom de la série.
- labels.ShowValue : affiche la valeur des points de données.
- labels.Separator : définit le séparateur pour les étiquettes de données.

## Étape 5 : Enregistrez le document

Enfin, enregistrez le document dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Explication

- doc.Save : enregistre le document sous le nom spécifié dans le répertoire fourni.

## Conclusion

 Toutes nos félicitations! Vous avez personnalisé avec succès les étiquettes de données de graphique à l’aide d’Aspose.Words pour .NET. Cette bibliothèque offre une solution robuste pour gérer les documents Word par programmation, permettant aux développeurs de créer plus facilement des applications de traitement de documents sophistiquées et dynamiques. Plongez dans le[Documentation](https://reference.aspose.com/words/net/) pour explorer plus de fonctionnalités et de capacités.

## FAQ

### Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une puissante bibliothèque de traitement de documents qui permet aux développeurs de créer, modifier et convertir des documents Word par programme.

### Comment installer Aspose.Words pour .NET ?
 Vous pouvez le télécharger et l'installer à partir du[lien de téléchargement](https://releases.aspose.com/words/net/). Suivez les instructions d'installation fournies.

### Puis-je essayer Aspose.Words pour .NET gratuitement ?
 Oui, vous pouvez obtenir un[essai gratuit](https://releases.aspose.com/) ou un[permis temporaire](https://purchase.aspose.com/temporary-license/)pour évaluer le produit.

### Aspose.Words pour .NET est-il compatible avec .NET Core ?
Oui, Aspose.Words pour .NET est compatible avec .NET Core, .NET Standard et .NET Framework.

### Où puis-je obtenir de l’assistance pour Aspose.Words pour .NET ?
 Vous pouvez visiter le[forum d'entraide](https://forum.aspose.com/c/words/8) pour l’aide et l’assistance de la communauté Aspose et des experts.
