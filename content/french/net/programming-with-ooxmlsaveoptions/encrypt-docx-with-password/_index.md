---
title: Chiffrer Docx avec un mot de passe
linktitle: Chiffrer Docx avec un mot de passe
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment chiffrer un fichier DOCX avec un mot de passe à l'aide d'Aspose.Words pour .NET. Tutoriel complet sur la sécurité des documents.
type: docs
weight: 10
url: /fr/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
Dans ce didacticiel, nous explorerons le code source C# fourni pour chiffrer un fichier DOCX avec un mot de passe à l'aide d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de protéger votre document en le rendant accessible uniquement avec un mot de passe spécifié.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words for .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Chargement du document

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` et en transmettant le chemin d'accès au fichier DOCX à charger.

## Étape 3 : Configuration des options de sauvegarde OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

Dans cette étape, nous configurons les options de sauvegarde OOXML en créant un nouveau`OoxmlSaveOptions` objet. Nous précisons le mot de passe souhaité pour crypter le document en définissant le`Password` propriété à votre mot de passe personnalisé.

## Étape 4 : Cryptage du document avec mot de passe

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 Dans cette dernière étape, nous sauvegardons le document en utilisant le`Save` méthode et en passant le chemin d'accès au fichier de sortie avec le`.docx` extension, ainsi que les options de sauvegarde spécifiées.

Vous pouvez maintenant exécuter le code source pour crypter votre document DOCX avec un mot de passe. Le fichier résultant sera enregistré dans le répertoire spécifié sous le nom "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx". Assurez-vous de conserver votre mot de passe en sécurité, car il sera nécessaire pour ouvrir le document crypté.

### Exemple de code source pour chiffrer Docx avec mot de passe à l'aide d'Aspose.Words pour .NET 

```csharp

//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de cryptage d'un fichier DOCX avec un mot de passe à l'aide d'Aspose.Words pour .NET. Nous avons appris à protéger nos documents en les rendant accessibles uniquement avec un mot de passe spécifié.

Le cryptage des documents est une mesure de sécurité essentielle pour protéger les informations sensibles. Grâce à Aspose.Words for .NET, nous pouvons facilement ajouter cette fonctionnalité à nos applications.

En suivant les étapes fournies, vous pouvez intégrer le cryptage des mots de passe dans vos projets Aspose.Words for .NET et garantir la confidentialité de vos documents.

N'hésitez pas à expérimenter d'autres fonctionnalités proposées par Aspose.Words for .NET pour enrichir vos applications avec des fonctionnalités avancées de manipulation de documents.
