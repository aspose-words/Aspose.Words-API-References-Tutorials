---
title: Autoriser uniquement la protection des champs de formulaire dans un document Word
linktitle: Autoriser uniquement la protection des champs de formulaire dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment utiliser Aspose.Words for .NET pour protéger un document Word et autoriser uniquement la modification des champs de formulaire.
type: docs
weight: 10
url: /fr/net/document-protection/allow-only-form-fields-protect/
---
La protection des documents est une fonctionnalité essentielle lors du traitement de texte avec des fichiers au sein de votre application C#. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement protéger vos documents et autoriser uniquement la modification des champs de formulaire. Dans ce guide étape par étape, nous vous expliquerons comment utiliser le code source C# pour autoriser uniquement la modification des champs de formulaire à l'aide de la fonctionnalité Autoriser uniquement la protection des champs de formulaire d'Aspose.Words pour .NET.

## Étape 1 : Définition du répertoire de documents

La première étape consiste à définir le répertoire de votre document. Vous devez spécifier le chemin où vous souhaitez enregistrer le document protégé. Par exemple :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents.

## Étape 2 : Insérer des sections et du texte

Ensuite, vous devez insérer des sections et du texte dans votre document. Utilisez la classe DocumentBuilder fournie par Aspose.Words pour créer le contenu de votre document. Voici un exemple simple :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Dans cet exemple, nous créons un nouveau document vierge, puis utilisons DocumentBuilder pour ajouter une ligne de texte.

## Étape 3 : Activation de la protection des documents

 La protection des documents ne fonctionne que lorsque la protection des documents est activée. Vous pouvez activer la protection des documents à l'aide de l'outil`Protect` méthode de la classe Document. Voici comment:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Dans cet exemple, nous activons la protection des documents en spécifiant le type de protection `

AllowOnlyFormFields` et définition d’un mot de passe.

## Étape 4 : Autoriser uniquement les champs de formulaire

Maintenant que la protection des documents est activée, nous devons préciser que seule la modification des champs du formulaire est autorisée. Cela garantit que les utilisateurs ne peuvent modifier que les parties du document qui sont des champs de formulaire. Voici comment:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Assurez-vous de remplacer « mot de passe » par le mot de passe que vous avez défini précédemment.

## Étape 5 : Enregistrement du document protégé

 Enfin, vous pouvez enregistrer le document protégé à l'aide du`Save` méthode de la classe Document. Spécifiez le chemin complet du fichier et le nom du fichier souhaité. Par exemple :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Assurez-vous de remplacer "dataDir" par le chemin d'accès à votre répertoire de documents.

### Exemple de code source pour la fonctionnalité Autoriser uniquement la protection des champs de formulaire à l'aide d'Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Insérez deux sections avec du texte.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Une protection de document ne fonctionne que lorsque la protection de document est activée et seule la modification dans les champs de formulaire est autorisée.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Enregistrez le document protégé.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser la bibliothèque Aspose.Words pour .NET pour protéger un document et autoriser uniquement la modification des champs de formulaire. En suivant les étapes fournies, vous pouvez facilement implémenter cette fonctionnalité dans votre application C#. La protection des documents est essentielle pour assurer la sécurité et la confidentialité de vos documents.

### FAQ pour autoriser uniquement la protection des champs de formulaire dans un document Word

#### Q : Qu'est-ce que la protection des documents dans Aspose.Words pour .NET ?

: La protection des documents dans Aspose.Words for .NET est une fonctionnalité qui vous permet de sécuriser vos documents en restreignant certaines actions, telles que l'édition, le formatage ou la modification du contenu. Il aide à maintenir l’intégrité et la confidentialité de vos documents en empêchant les modifications non autorisées.

#### Q : Comment puis-je protéger un document et autoriser uniquement la modification des champs de formulaire à l'aide d'Aspose.Words pour .NET ?

R : Pour protéger un document et autoriser uniquement la modification des champs de formulaire à l'aide d'Aspose.Words for .NET, vous pouvez suivre ces étapes :
1. Définissez le chemin du répertoire de votre document.
2.  Insérez des sections et du texte dans votre document à l'aide du`DocumentBuilder` classe.
3.  Activez la protection des documents à l'aide de l'outil`Protect` méthode du`Document` classe, en spécifiant le type de protection comme`AllowOnlyFormFields` et fournir un mot de passe.
4.  Enregistrez le document protégé à l'aide du`Save` méthode du`Document` classe.

#### Q : Puis-je insérer des champs de formulaire dans un document protégé à l'aide d'Aspose.Words pour .NET ?

 : Oui, vous pouvez insérer des champs de formulaire dans un document protégé à l'aide d'Aspose.Words for .NET. La protection des documents avec le`AllowOnlyFormFields` type permet aux utilisateurs de modifier uniquement les champs du formulaire tout en protégeant le reste du contenu du document. Vous pouvez utiliser le`DocumentBuilder` classe pour insérer des champs de formulaire dans le document avant d’activer la protection.

#### Q : Puis-je supprimer la protection d'un document protégé ?

 R : Oui, vous pouvez supprimer la protection d'un document protégé à l'aide d'Aspose.Words for .NET. Pour supprimer la protection, vous pouvez utiliser le`Unprotect` méthode du`Document` classe et fournissez le mot de passe correct. Cela supprimera la protection et permettra une modification sans restriction du document.

#### Q : Est-il possible de protéger un document avec plusieurs types de protection ?

 R : Non, Aspose.Words for .NET ne permet d'appliquer qu'un seul type de protection à un document à la fois. Cependant, le`AllowOnlyFormFields` Le type de protection peut restreindre efficacement la modification aux champs de formulaire tout en autorisant d'autres types de protection, tels que`AllowOnlyComments` ou`AllowOnlyRevisions`à combiner avec la protection des champs de formulaire.

#### Q : Puis-je définir différents mots de passe pour différents types de protection dans un document ?

R : Non, Aspose.Words for .NET vous permet de définir un mot de passe unique pour la protection des documents, quel que soit le type de protection. Le même mot de passe sera utilisé pour activer et désactiver la protection des documents.