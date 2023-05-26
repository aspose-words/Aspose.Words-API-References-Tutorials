---
title: Obtenir le type de protection
linktitle: Obtenir le type de protection
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser la fonction Obtenir le type de protection d'Aspose.Words pour .NET pour déterminer le type de protection d'un document.
type: docs
weight: 10
url: /fr/net/document-protection/get-protection-type/
---

Bienvenue dans ce guide étape par étape qui explique le code source C# pour la fonctionnalité Obtenir le type de protection d'Aspose.Words pour .NET. Dans cet article, nous allons vous montrer comment utiliser cette fonctionnalité puissante pour déterminer le type de protection d'un document. La protection des documents est essentielle pour assurer la confidentialité et l'intégrité de vos fichiers. Nous vous guiderons à travers les étapes nécessaires pour intégrer Aspose.Words pour .NET et utiliser la fonctionnalité Obtenir le type de protection.

## Étape 1 : Chargement du document

La première étape pour utiliser la fonctionnalité Obtenir le type de protection consiste à télécharger le document sur lequel vous souhaitez travailler. Vous pouvez le faire en utilisant la classe Document fournie par Aspose.Words pour .NET. Voici un exemple de code pour charger un document à partir d'un fichier :

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

Assurez-vous de spécifier le chemin d'accès correct à votre fichier de document.

## Étape 2 : Récupération du type de protection

Une fois le document téléchargé, vous pouvez utiliser la propriété ProtectionType de l'objet Document pour récupérer le type de protection appliqué au document. Voici comment procéder :

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Exemple de code source pour obtenir le type de protection à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonction Obtenir le type de protection à l'aide d'Aspose.Words pour .NET :

```csharp

	Document doc = new Document(MyDir + "Document.docx");
	ProtectionType protectionType = doc.ProtectionType;

```

## Conclusion

Dans cet article, nous avons expliqué comment utiliser la fonction Obtenir le type de protection d'Aspose.Words pour .NET pour déterminer le type de protection d'un document. En suivant les étapes décrites, vous pourrez facilement intégrer cette fonctionnalité dans vos propres projets C# et manipuler efficacement les documents protégés. Aspose.Words pour .NET offre une grande flexibilité

