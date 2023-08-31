---
title: Obtenir le type de protection dans un document Word
linktitle: Obtenir le type de protection dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser la fonction Obtenir le type de protection dans le document Word d'Aspose.Words pour .NET pour déterminer le type de protection d'un document.
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

### FAQ

#### Q : Qu'est-ce que la propriété ProtectionType dans Aspose.Words pour .NET ?

 R : Le`ProtectionType` La propriété dans Aspose.Words pour .NET est une fonctionnalité qui vous permet de déterminer le type de protection appliqué à un document Word. Il fournit des informations sur le niveau de protection du document, par exemple si le document est protégé contre les commentaires, les révisions, les formulaires ou d'autres types de restrictions.

#### Q : Comment puis-je récupérer le type de protection d'un document à l'aide d'Aspose.Words pour .NET ?

R : Pour récupérer le type de protection d'un document à l'aide d'Aspose.Words pour .NET, vous pouvez suivre ces étapes :
1.  Chargez le document à l'aide de la`Document` classe.
2.  Accéder au`ProtectionType` propriété de la`Document`objet pour récupérer le type de protection.

#### Q : Puis-je déterminer si un document est protégé pour les formulaires ou les champs de formulaire à l'aide de la propriété ProtectionType ?

 R : Oui, vous pouvez déterminer si un document est protégé pour les formulaires ou les champs de formulaire à l'aide de la`ProtectionType` propriété dans Aspose.Words pour .NET. Si le type de protection est réglé sur`AllowOnlyFormFields`, cela indique que le document est protégé et que seuls les champs du formulaire peuvent être modifiés.

#### Q : Quels autres types de protection la propriété ProtectionType peut-elle renvoyer ?

 R : Le`ProtectionType` La propriété dans Aspose.Words pour .NET peut renvoyer différents types de protection, notamment :
- `NoProtection`: Le document n'est pas protégé.
- `AllowOnlyRevisions`: Le document est protégé et seules des révisions peuvent être effectuées.
- `AllowOnlyComments`: Le document est protégé et seuls des commentaires peuvent être ajoutés.
- `AllowOnlyFormFields`: Le document est protégé et seuls les champs du formulaire peuvent être modifiés.
- `ReadOnly`: Le document est protégé et défini en lecture seule.

#### Q : Puis-je modifier le type de protection d'un document à l'aide de la propriété ProtectionType ?

 R : Non, le`ProtectionType`La propriété dans Aspose.Words pour .NET est une propriété en lecture seule. Il vous permet de récupérer le type de protection actuel d'un document mais ne fournit pas de moyens directs pour modifier le type de protection. Pour modifier le type de protection, vous devez utiliser d'autres méthodes et propriétés disponibles dans le`Document` classe, comme`Protect` ou`Unprotect`.

#### Q : Est-il possible de protéger un document avec plusieurs types de protection simultanément ?

R : Non, Aspose.Words pour .NET n'autorise qu'un seul type de protection à appliquer à un document à la fois. Cependant, vous pouvez combiner différents types de protection en activant la protection, en définissant un type, en désactivant la protection, puis en la réactivant avec un autre type.

