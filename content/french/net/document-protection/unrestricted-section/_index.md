---
title: Section sans restriction dans un document Word
linktitle: Section sans restriction dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir des sections sans restriction dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-protection/unrestricted-section/
---
Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonctionnalité de section sans restriction d'Aspose.Words for .NET. Cette fonctionnalité vous permet de définir des sections spécifiques d'un document Word qui ne sont pas protégées, même si le reste du document est protégé. Suivez les étapes ci-dessous :

## Étape 1 : Création du document et des sections

Commencez par créer une instance de la classe Document et un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Ajouter du contenu au document
Utilisez l'objet DocumentBuilder pour ajouter du contenu au document et insérer des sauts de section :

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Étape 3 : Protéger le document et les sections

La protection des sections ne fonctionne que lorsque la protection des documents est activée et seule la modification dans les champs du formulaire est autorisée. Vous pouvez protéger le document à l'aide de la méthode Protect() de l'objet Document :

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Assurez-vous de spécifier le type de protection correct et de définir le mot de passe souhaité.

## Étape 4 : Désactiver la protection pour une section spécifique

Par défaut, toutes les sections sont protégées, mais vous pouvez désactiver de manière sélective la protection d'une section spécifique à l'aide de la propriété ProtectedForForms de l'objet Section :

```csharp
doc.Sections[0].ProtectedForForms = false;
```

Dans cet exemple, la protection est désactivée pour la première section.

## Étape 5 : Enregistrez le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour enregistrer le document avec des sections sans restriction.

### Exemple de code source pour une section sans restriction utilisant Aspose.Words pour .NET

Voici le code source complet de la section sans restriction utilisant Aspose.Words pour .NET :


```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Insérez deux sections avec du texte.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// La protection des sections ne fonctionne que lorsque la protection du document est activée et seule la modification dans les champs du formulaire est autorisée.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Par défaut, toutes les sections sont protégées, mais nous pouvons désactiver la protection de manière sélective.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

En suivant ces étapes, vous pourrez facilement définir des sections sans restriction dans votre document Word avec Aspose.Words pour .NET.

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de section illimitée d'Aspose.Words pour .NET, qui permet à des sections spécifiques d'un document Word de rester non protégées tandis que le reste du document est protégé. En suivant les étapes fournies, vous pouvez facilement définir des sections dans votre document où les utilisateurs peuvent librement modifier le contenu tout en conservant la protection des autres sections. Aspose.Words for .NET offre de puissantes fonctionnalités de protection et de personnalisation des documents, vous permettant de contrôler les autorisations de modification dans vos documents Word.

### FAQ pour la section sans restriction dans un document Word

#### Q : Que sont les sections non restreintes dans Aspose.Words pour .NET ?

: Les sections non restreintes dans Aspose.Words pour .NET sont des sections spécifiques d'un document Word qui ne sont pas protégées, même si le reste du document est protégé. Ces sections permettent aux utilisateurs de modifier le contenu qu'elles contiennent tout en conservant la protection des parties restantes du document.

#### Q : Comment puis-je créer des sections sans restriction à l'aide d'Aspose.Words pour .NET ?

R : Pour créer des sections sans restriction dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez suivre ces étapes :
1.  Créez une instance du`Document` classe et un`DocumentBuilder` objet.
2.  Utilisez le`DocumentBuilder` pour ajouter du contenu au document et insérer des sauts de section.
3.  Protégez le document à l'aide du`Protect` méthode du`Document` objet, en précisant le type de protection et le mot de passe souhaités.
4.  Désactivez la protection pour une section spécifique en définissant le`ProtectedForForms` propriété du correspondant`Section` s'opposer à`false`.
5. Enregistrez le document modifié.

#### Q : Puis-je avoir plusieurs sections sans restriction dans un document Word ?

 R : Oui, vous pouvez avoir plusieurs sections sans restriction dans un document Word. En désactivant sélectivement la protection de sections spécifiques à l'aide de l'option`ProtectedForForms` propriété du`Section`objet, vous pouvez définir plusieurs sections dans lesquelles les utilisateurs peuvent librement modifier le contenu tout en gardant les autres sections protégées.

#### Q4. Puis-je supprimer la protection d’une section initialement protégée ?
 Oui, vous pouvez supprimer la protection d'une section initialement protégée en définissant l'option`ProtectedForForms` propriété du correspondant`Section` s'opposer à`false`. Cela permet aux utilisateurs de modifier le contenu de cette section spécifique sans aucune restriction.

#### Q : Quels types de protection peuvent être appliqués à un document Word ?

R : Aspose.Words for .NET fournit différents types de protection qui peuvent être appliqués à un document Word, notamment :
- NoProtection : Aucune protection n’est appliquée.
- AllowOnlyRevisions : les utilisateurs peuvent uniquement apporter des révisions au document.
- AllowOnlyComments : les utilisateurs peuvent uniquement ajouter des commentaires au document.
- AllowOnlyFormFields : les utilisateurs peuvent uniquement modifier les champs de formulaire dans le document.
- ReadOnly : le document est en lecture seule et aucune modification n'est autorisée.


