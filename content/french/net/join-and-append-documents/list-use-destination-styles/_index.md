---
title: Liste des styles de destination d'utilisation
linktitle: Liste des styles de destination d'utilisation
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment joindre et ajouter des documents Word tout en préservant les styles de liste du document de destination à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/list-use-destination-styles/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité List Use Destination Styles d'Aspose.Words for .NET. Cette fonctionnalité vous permet de joindre et d'ajouter des documents Word tout en utilisant les styles de liste du document de destination.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Aspose.Words pour .NET installé. Vous pouvez le télécharger depuis le site Web Aspose ou l'installer via NuGet.
2. Visual Studio ou tout autre environnement de développement C#.

## Étape 1 : initialiser les répertoires de documents

 Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. Modifier la valeur du`dataDir` variable au chemin où se trouvent vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger les documents source et de destination

Ensuite, vous devez charger les documents source et de destination à l'aide de Aspose.Words.`Document` classe. Mettez à jour les noms de fichiers dans le`Document` constructeur en fonction des noms de vos documents.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Étape 3 : Définir le document source pour qu'il continue après le document de destination

 Pour garantir que le contenu du document source continue après la fin du document de destination, vous devez définir le`SectionStart` propriété de la première section du document source à`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Étape 4 : Gérer le formatage de la liste

Pour gérer le formatage de la liste, vous parcourrez chaque paragraphe du document source et vérifierez s'il s'agit d'un élément de liste. Si tel est le cas, vous comparerez l’ID de liste avec les listes existantes dans le document de destination. Si une liste avec le même ID existe, vous créerez une copie de la liste dans le document source et mettrez à jour le format de liste du paragraphe pour utiliser la liste copiée.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Étape 5 : Ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination à l'aide du`AppendDocument` méthode du`Document` classe. Le`ImportFormatMode.UseDestinationStyles` Le paramètre garantit que les styles de liste du document de destination sont utilisés lors de l’opération d’ajout.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Étape 6 : Enregistrez le document final

Enfin, enregistrez le document fusionné avec la fonctionnalité List Use Destination Styles activée à l'aide de l'option`Save` méthode du`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Exemple de code source pour les styles de destination d'utilisation de liste à l'aide d'Aspose.Words pour .NET 

Voici le code source complet de la fonctionnalité « Liste des styles de destination d'utilisation » en C# à l'aide d'Aspose.Words pour .NET :


```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Définissez le document source pour qu'il continue juste après la fin du document de destination.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Gardez une trace des listes créées.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Vérifiez si le document de destination contient déjà une liste avec cet ID. Si c'est le cas, cela pourrait
			// faire fonctionner les deux listes ensemble. Créez plutôt une copie de la liste dans le document source.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Une liste nouvellement copiée existe déjà pour cet ID, récupérez la liste stockée,
				// et utilisez-le sur le paragraphe actuel.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Ajoutez une copie de cette liste au document et conservez-la pour référence ultérieure.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Définissez la liste de ce paragraphe sur la liste copiée.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Ajoutez le document source à la fin du document de destination.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

C'est ça! Vous avez implémenté avec succès la fonctionnalité List Use Destination Styles à l’aide d’Aspose.Words for .NET. Le document final contiendra le contenu fusionné avec les styles de liste du document de destination.