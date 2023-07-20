---
title: Détecter le format de fichier du document
linktitle: Détecter le format de fichier du document
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour détecter le format de fichier de document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-fileformat/detect-file-format/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser la fonction de détection de format de fichier de document avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment détecter le format des différents fichiers de documents.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir les répertoires

 Pour commencer, vous devez définir les répertoires où vous souhaitez stocker les fichiers en fonction de leur format. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents. Nous créons les répertoires "Supported", "Unknown", "Encrypted" et "Pre97" s'ils n'existent pas déjà.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Créez les répertoires s'ils n'existent pas déjà.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Étape 2 : Parcourir les fichiers

 Ensuite on utilise le`GetFiles` méthode de la`Directory` classe pour obtenir la liste des fichiers dans le répertoire spécifié. Nous utilisons également un`Where`clause pour exclure un fichier spécifique nommé "Corrupted document.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Étape 3 : Détecter le format de chaque fichier

 Nous parcourons chaque fichier de la liste et utilisons le`DetectFileFormat` méthode de la`FileFormatUtil` classe pour détecter le format du fichier. Nous affichons également le type de document détecté.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Afficher le type de document
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... Ajouter des cas pour d'autres formats de document pris en charge
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

C'est tout ! Vous avez détecté avec succès le format de différents fichiers de documents à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour la détection de format de fichier avec Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Créez les répertoires s'ils n'existent pas déjà.
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// Afficher le type de document
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### FAQ pour la détection de format de fichier de document

#### Comment détecter le format d'un fichier de document en utilisant Aspose.Words pour .NET ?

 Pour détecter le format d'un fichier de document à l'aide d'Aspose.Words pour .NET, vous pouvez suivre les étapes fournies dans le didacticiel. En utilisant le`DetectFileFormat` méthode de la`FileFormatUtil`class vous permettra de détecter le format du fichier du document. Cela vous permettra de déterminer s'il s'agit d'un document Microsoft Word 97-2003, d'un modèle, d'un document Office Open XML WordprocessingML ou d'autres formats pris en charge. Le code fourni dans le didacticiel vous guidera dans l'implémentation de cette fonctionnalité.

#### Quels formats de document Aspose.Words pour .NET prend-il en charge ?

Aspose.Words pour .NET prend en charge une variété de formats de documents, notamment les documents Microsoft Word 97-2003 (DOC), les modèles (DOT), les documents Office Open XML WordprocessingML (DOCX), les documents Office Open XML WordprocessingML avec macros (DOCM), Office Open Modèles XML WordprocessingML sans macros (DOTX), modèles Office Open XML WordprocessingML avec macros (DOTM), documents OPC plats, documents RTF, documents Microsoft Word 2003 WordprocessingML, documents HTML, documents MHTML (archive Web), documents OpenDocument Text (ODT), Modèles OpenDocument Text (OTT), documents MS Word 6 ou Word 95 et formats de documents inconnus.

#### Comment gérer les fichiers de documents chiffrés lors de la détection du format ?

 Lors de la détection du format d'un fichier de document, vous pouvez utiliser le`IsEncrypted` propriété de la`FileFormatInfo` objet pour vérifier si le fichier est crypté. Si le fichier est crypté, vous pouvez prendre des mesures supplémentaires pour gérer ce cas spécifique, comme copier le fichier dans un répertoire dédié aux documents cryptés. Vous pouvez utiliser le`File.Copy` méthode pour ce faire.

#### Quelles actions entreprendre lorsque le format d'un document est inconnu ?

Lorsque le format d'un document est inconnu, vous pouvez décider de le traiter d'une manière spécifique à votre application. Dans l'exemple fourni dans le tutoriel, le document est copié dans un répertoire spécifique dédié aux documents de format inconnu. Vous pouvez personnaliser cette action en fonction de vos besoins spécifiques.

#### Existe-t-il d'autres fonctionnalités d'Aspose.Words pour .NET qui peuvent être utilisées conjointement avec la détection de format de document ?

Oui, Aspose.Words pour .NET offre de nombreuses autres fonctionnalités pour le traitement et la manipulation de documents Word. Par exemple, vous pouvez utiliser la bibliothèque pour extraire du texte, des images ou des métadonnées de documents, appliquer des modifications de mise en forme, fusionner des documents, convertir des documents dans différents formats, etc.