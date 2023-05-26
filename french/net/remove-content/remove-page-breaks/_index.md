---
title: Supprimer les sauts de page
linktitle: Supprimer les sauts de page
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à supprimer les sauts de page dans un document à l'aide de la bibliothèque Aspose.Words pour .NET. Suivez notre guide étape par étape pour une mise en page transparente.
type: docs
weight: 10
url: /fr/net/remove-content/remove-page-breaks/
---
Dans ce didacticiel, nous allons explorer comment supprimer les sauts de page d'un document à l'aide de la bibliothèque Aspose.Words pour .NET. Les sauts de page peuvent parfois interférer avec la mise en forme et la mise en page d'un document, et il peut être nécessaire de les supprimer par programmation. Nous vous fournirons un guide étape par étape pour vous aider à comprendre le processus et à l'implémenter dans vos propres projets C#.

## Exigences

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Connaissance de base du langage de programmation C#
- Bibliothèque Aspose.Words pour .NET installée
- Visual Studio ou tout autre environnement de développement C# configuré

## Étape 1 : Configuration de l'environnement

Pour commencer, créez un nouveau projet C# dans votre environnement de développement préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est correctement référencée dans votre projet.

## Étape 2 : Chargement du document

Pour supprimer les sauts de page d'un document, nous devons d'abord charger le document en mémoire. Le code suivant montre comment charger un document à partir d'un répertoire spécifique :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Charger le document
Document doc = new Document(dataDir + "your-document.docx");
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre document.

## Étape 3 : Suppression des sauts de page

Une fois le document chargé, nous pouvons commencer à supprimer les sauts de page. L'extrait de code ci-dessous montre comment parcourir tous les paragraphes du document, vérifier les sauts de page et les supprimer :

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
     // Si le paragraphe a un saut de page avant, alors effacez-le
     if (para.ParagraphFormat.PageBreakBefore)
         para.ParagraphFormat.PageBreakBefore = false;

     // Vérifiez toutes les séquences du paragraphe pour les sauts de page et supprimez-les
     foreach(Run run in para.Runs)
     {
         if (run.Text.Contains(ControlChar.PageBreak))
             run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
     }
}
```

L'extrait de code ci-dessus parcourt tous les paragraphes du document et vérifie si chaque paragraphe est précédé d'un saut de page. Si un saut de page est détecté, il est effacé. Ensuite, il vérifie chaque exécution dans le paragraphe pour les sauts de page et les supprime.

## Étape 4 : Enregistrer le document modifié

Après avoir supprimé les sauts de page, nous devons enregistrer le document modifié. Le code suivant montre comment enregistrer le document modifié à un emplacement spécifique :

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 Remplacer`"modified-document.docx"` avec le nom souhaité pour votre document modifié.

### Exemple de code source pour supprimer les sauts de page à l'aide de Aspose.Words pour .NET 
```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
//Charger le document
Document doc = new Document(dataDir + "your-document.docx");

NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
	// Si le paragraphe a un saut de page avant l'ensemble, effacez-le.
	if (para.ParagraphFormat.PageBreakBefore)
		para.ParagraphFormat.PageBreakBefore = false;

	//Vérifiez toutes les séquences du paragraphe pour les sauts de page et supprimez-les.
	foreach (Run run in para.Runs)
	{
		if (run.Text.Contains(ControlChar.PageBreak))
			run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
	}
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);        

```

## Conclusion

Dans ce didacticiel, nous avons appris à supprimer les sauts de page d'un document à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant le guide étape par étape, vous devriez maintenant être en mesure d'implémenter cette fonctionnalité dans vos propres projets C#. La suppression des sauts de page peut vous aider à conserver une mise en page et une mise en forme cohérentes dans vos documents.
