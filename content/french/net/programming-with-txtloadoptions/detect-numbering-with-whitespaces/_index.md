---
title: Détecter la numérotation avec des espaces
linktitle: Détecter la numérotation avec des espaces
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment détecter les numéros de liste avec des espaces blancs dans Aspose.Words for .NET. Améliorez facilement la structure de vos documents.
type: docs
weight: 10
url: /fr/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
Dans ce tutoriel, nous explorerons le code source C# fourni pour la fonctionnalité « Détection de numérotation avec espaces blancs » avec Aspose.Words for .NET. Cette fonctionnalité vous permet de détecter et de créer des listes à partir d'un document texte contenant des numéros de liste suivis d'espaces blancs.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words for .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Création du document texte

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

Dans cette étape, nous créons une chaîne de texte qui simule un document texte contenant des numéros de liste suivis d'espaces blancs. Nous utilisons différents délimiteurs de liste tels que le point, le crochet droit, la puce et les espaces blancs.

## Étape 3 : Configuration des options de téléchargement

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 Dans cette étape, nous configurons les options de chargement des documents. Nous créons un nouveau`TxtLoadOptions` objet et définissez le`DetectNumberingWithWhitespaces`propriété à`true`. Cela permettra à Aspose.Words de détecter les numéros de liste même s'ils sont suivis d'espaces blancs.

## Étape 4 : Chargement du document et sauvegarde

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Dans cette étape, nous chargeons le document en utilisant la chaîne de texte spécifiée et les options de chargement. Nous utilisons un`MemoryStream` pour convertir la chaîne de texte en flux mémoire. Ensuite, nous enregistrons le document résultant au format .docx.

### Exemple de code source pour la fonctionnalité de détection de la numérotation des espaces blancs avec Aspose.Words pour .NET.

```csharp

            
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Créez un document en texte brut sous la forme d'une chaîne avec des parties pouvant être interprétées comme des listes.
// Au chargement, les trois premières listes seront toujours détectées par Aspose.Words,
// et les objets List seront créés pour eux après le chargement.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// La quatrième liste, avec un espace entre le numéro de liste et le contenu de l'élément de liste,
// ne sera détecté comme une liste que si "DetectNumberingWithWhitespaces" dans un objet LoadOptions est défini sur true,
// pour éviter que les paragraphes commençant par des chiffres soient détectés par erreur comme des listes.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Chargez le document en appliquant LoadOptions comme paramètre et vérifiez le résultat.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Vous pouvez maintenant exécuter le code source pour charger le document texte contenant les numéros de liste avec des espaces blancs, puis créer un document .docx avec les listes détectées. Le fichier de sortie sera enregistré dans le répertoire spécifié sous le nom « WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx ».

## Conclusion
Dans ce didacticiel, nous avons exploré la fonctionnalité de détection de la numérotation des espaces dans Aspose.Words pour .NET. Nous avons appris à créer des listes à partir d'un document texte contenant des numéros de liste suivis d'espaces blancs.

Cette fonctionnalité est extrêmement utile pour traiter des documents contenant des numéros de liste formatés de différentes manières. En utilisant les options de chargement appropriées, Aspose.Words est capable de détecter ces numéros de liste, même s'ils sont suivis d'espaces blancs, et de les convertir en listes structurées dans le document final.

L'utilisation de cette fonctionnalité peut vous faire gagner du temps et améliorer l'efficacité de votre flux de travail. Vous pouvez facilement extraire des informations de documents texte et les convertir en documents bien structurés avec des listes appropriées.

N'oubliez pas de prendre en compte les options de chargement, telles que la configuration de la détection de composition d'espaces blancs, pour obtenir les résultats souhaités.

Aspose.Words for .NET offre de nombreuses fonctionnalités avancées pour la manipulation et la génération de documents. En explorant davantage la documentation et les exemples fournis par Aspose.Words, vous pourrez exploiter pleinement les capacités de cette puissante bibliothèque.

Alors n'hésitez pas à intégrer la détection de numérotation des espaces dans vos projets Aspose.Words for .NET et profitez de ses avantages pour créer des documents bien structurés et lisibles.


