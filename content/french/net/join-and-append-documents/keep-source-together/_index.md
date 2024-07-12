---
title: Gardez la source ensemble
linktitle: Gardez la source ensemble
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment fusionner des documents Word à l'aide d'Aspose.Words pour .NET tout en préservant le formatage. Ce guide complet couvre tout, de la configuration à l'exécution.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/keep-source-together/
---
## Introduction

À l’ère numérique d’aujourd’hui, la manipulation de documents Word par programmation est essentielle dans divers secteurs. Aspose.Words for .NET permet aux développeurs d'automatiser efficacement les tâches de gestion des documents. Ce guide complet vous guidera tout au long du processus de fusion de documents tout en préservant le formatage source à l'aide d'Aspose.Words for .NET.

## Conditions préalables

Avant de vous lancer dans la fusion de documents avec Aspose.Words for .NET, assurez-vous de disposer des éléments suivants :

- Visual Studio : environnement de développement intégré (IDE) pour le développement .NET.
- Aspose.Words pour .NET : installé et configuré dans votre environnement de développement.
- Familiarité avec C# : Compréhension de base du langage de programmation C#.

## Importer des espaces de noms

Pour commencer, importez les espaces de noms nécessaires :

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Étape 1 : Charger les documents

 Tout d'abord, chargez les documents source et de destination dans Aspose.Words`Document` objets.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR_DOCUMENT_DIRECTORY/";

// Charger les documents source et destination
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Étape 2 : Définir le début de la section

Configurez le début de la section pour garantir que le contenu du document source circule en continu après le document de destination.

```csharp
// Définir le document source pour qu'il apparaisse juste après le contenu du document de destination
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Étape 3 : Gardez les paragraphes ensemble

Pour conserver l'intégrité du formatage, marquez chaque paragraphe du document source pour conserver le paragraphe suivant.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Étape 4 : Joindre des documents

 Fusionnez les documents à l'aide du`AppendDocument` méthode, en veillant à conserver la mise en forme du document source.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : Enregistrer le document fusionné

Enfin, enregistrez le document fusionné à l'emplacement souhaité.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

## Conclusion

En conclusion, Aspose.Words for .NET simplifie la tâche de fusion de documents Word tout en préservant de manière transparente le formatage d'origine. Cette capacité est cruciale pour les applications nécessitant un traitement automatisé des documents.

## FAQ

### Aspose.Words for .NET peut-il fusionner des documents de différents formats ?
Oui, il peut fusionner des documents quel que soit leur format, en conservant le formatage source.

### Aspose.Words for .NET prend-il en charge la fusion efficace de documents volumineux ?
Absolument, il gère les documents volumineux avec des performances optimales.

### Existe-t-il une version d’essai disponible pour Aspose.Words pour .NET ?
 Oui, vous pouvez télécharger un essai gratuit[ici](https://releases.aspose.com/).

### Comment puis-je obtenir une assistance technique pour Aspose.Words pour .NET ?
 L'assistance technique est disponible via le[Forum Aspose.Words](https://forum.aspose.com/c/words/8).

### Puis-je acheter une licence temporaire pour Aspose.Words pour .NET ?
 Oui, vous pouvez acquérir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).