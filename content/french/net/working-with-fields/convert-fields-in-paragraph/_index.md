---
title: Convertir les champs en paragraphe
linktitle: Convertir les champs en paragraphe
second_title: API de traitement de documents Aspose.Words
description: Convertissez les champs IF en texte brut dans un paragraphe avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/convert-fields-in-paragraph/
---

Voici un didacticiel qui montre comment utiliser la fonction Convertir les champs en paragraphe avec Aspose.Words pour .NET. Ce code convertit tous les champs de type IF rencontrés dans le dernier paragraphe d'un document en texte brut. Suivez les étapes ci-dessous pour comprendre et exécuter ce code.

Assurez-vous d'avoir installé Aspose.Words pour .NET et configuré votre environnement de développement avant de commencer.

## Étape 1 : Importer des références

Pour utiliser Aspose.Words dans votre projet, vous devez ajouter les références nécessaires. Assurez-vous d'avoir ajouté une référence à la bibliothèque Aspose.Words dans votre projet.

## Étape 2 : Chargement du document

Avant de pouvoir convertir des champs, vous devez charger le document contenant les champs à convertir. Assurez-vous de spécifier le chemin d'accès correct au répertoire contenant le document. Voici comment télécharger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chargez le document.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Conversion des champs en texte

Maintenant que le document est chargé, nous pouvons procéder à la conversion des champs de type en texte brut. Dans cet exemple, nous ciblons uniquement les champs présents dans le dernier paragraphe du document. Voici le code qui effectue cette conversion :

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

Ce code utilise une combinaison de méthodes LINQ pour filtrer les champs dans le dernier paragraphe du document, puis les convertit en texte brut en appelant le`Unlink()` méthode.

## Étape 4 : Enregistrer le document modifié

 Une fois les champs convertis, vous pouvez enregistrer le document modifié. Utilisez le`Save()` méthode pour cela. Voici un exemple :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour la sauvegarde.

### Exemple de code source pour Convertir les champs en paragraphe à l'aide de Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chargez le document.
Document doc = new Document(dataDir + "Linked fields.docx");

// Convertissez les champs IF en texte brut dans le dernier paragraphe du document.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Enregistrez le document modifié.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### FAQ

#### Q : Qu'est-ce qu'un champ de conversion dans Aspose.Words ?

R : Un champ de conversion dans Aspose.Words est un type de champ qui convertit une valeur ou une expression dans un autre format ou type de données. Par exemple, vous pouvez utiliser un champ de conversion pour convertir une date dans un format spécifique, un nombre en texte ou effectuer d'autres types de conversions.

#### Q : Comment insérer un champ de conversion dans un paragraphe avec Aspose.Words ?

R : Pour insérer un champ de conversion dans un paragraphe avec Aspose.Words, vous pouvez suivre ces étapes :

1. Importez la classe Document à partir de l'espace de noms Aspose.Words.
2. Créez une instance de Document en chargeant votre document existant.
3. Obtenez le paragraphe où vous souhaitez insérer le champ de conversion.
4. Utilisez la méthode InsertField pour insérer le champ de conversion avec la syntaxe correcte.

#### Q : Quels formats de conversion Aspose.Words prend-il en charge ?

R : Aspose.Words prend en charge une large gamme de formats de conversion dans les champs, notamment les formats de date, les formats de nombre, les formats de texte, les formats de devise, les formats de pourcentage, etc. Vous pouvez consulter la documentation Aspose.Words pour une liste complète des formats de conversion disponibles.

#### Q : Comment mettre à jour un champ de conversion dans un document Word avec Aspose.Words ?

R : Pour mettre à jour un champ de conversion dans un document Word avec Aspose.Words, vous pouvez utiliser la méthode UpdateFields. Cette méthode parcourt le document et met à jour tous les champs, y compris les champs de conversion, en recalculant les valeurs en fonction des données actuelles.