---
title: Insérer un champ TOA sans Document Builder
linktitle: Insérer un champ TOA sans Document Builder
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour insérer un champ TOA sans Document Builder en utilisant Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-toafield-without-document-builder/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "TOA Field Insertion" d'Aspose.Words pour .NET. Suivez attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et du paragraphe

Nous commençons par créer un nouveau document et initialiser un paragraphe.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Étape 3 : Insertion du champ TA

Nous utilisons la classe FieldTA pour insérer un champ TA dans le paragraphe.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Étape 4 : Ajouter le paragraphe au corps du document

Nous ajoutons le paragraphe contenant le champ TA au corps du document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Étape 5 : Création du paragraphe pour le champ TOA

Nous créons un nouveau paragraphe pour le champ TOA.

```csharp
para = new Paragraph(doc);
```

## Étape 6 : Insertion du champ TOA

Nous utilisons la classe FieldToa pour insérer un champ TOA dans le paragraphe.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Étape 7 : Ajouter le paragraphe au corps du document

Nous ajoutons le paragraphe contenant le champ TOA au corps du document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Étape 8 : Mettre à jour le champ TOA

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ TOA.

```csharp
fieldToa.Update();
```

### Exemple de code source pour l'insertion de champ TOA sans Document Builder avec Aspose.Words pour .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Nous voulons insérer les champs TA et TOA comme ceci :
// { TA \c 1 \l "Valeur 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```
