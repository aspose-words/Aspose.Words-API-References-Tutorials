---
title: Section non restreinte
linktitle: Section non restreinte
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à définir des sections sans restriction dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-protection/unrestricted-section/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonctionnalité de section sans restriction d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de définir des sections spécifiques dans un document Word qui ne sont pas protégées, même si le reste du document est protégé. Suivez les étapes ci-dessous :

## Étape 1 : Création du document et des sections

Commencez par créer une instance de la classe Document et un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Ajouter du contenu au document
Utilisez l'objet DocumentBuilder pour ajouter du contenu au document et insérer des sauts de section :

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Étape 3 : Protégez le document et les sections

La protection de section ne fonctionne que lorsque la protection de document est activée et que seule la modification dans les champs de formulaire est autorisée. Vous pouvez protéger le document à l'aide de la méthode Protect() de l'objet Document :

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Assurez-vous de spécifier le bon type de protection et de définir le mot de passe souhaité.

## Étape 4 : Désactivation de la protection pour une section spécifique

Par défaut, toutes les sections sont protégées, mais vous pouvez désactiver la protection de manière sélective pour une section spécifique à l'aide de la propriété ProtectedForForms de l'objet Section :

```csharp
doc.Sections[0].ProtectedForForms = false;
```

Dans cet exemple, la protection est désactivée pour la première section.

## Étape 5 : Enregistrez le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour enregistrer le document avec des sections illimitées.

### Exemple de code source pour la section sans restriction utilisant Aspose.Words pour .NET

Voici le code source complet pour la section sans restriction utilisant Aspose.Words pour .NET :


```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Insérez deux sections avec du texte.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// La protection de section ne fonctionne que lorsque la protection de document est activée et seule la modification dans les champs de formulaire est autorisée.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Par défaut, toutes les sections sont protégées, mais nous pouvons désactiver la protection de manière sélective.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

En suivant ces étapes, vous pourrez facilement définir des sections sans restriction dans votre document Word avec Aspose.Words pour .NET.

