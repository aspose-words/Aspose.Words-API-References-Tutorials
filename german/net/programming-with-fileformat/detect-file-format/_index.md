---
title: Dokumentdateiformat erkennen
linktitle: Dokumentdateiformat erkennen
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erkennen des Dokumentdateiformats mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-fileformat/detect-file-format/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zur Erkennung von Dokumentdateiformaten mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie das Format verschiedener Dokumentdateien erkennen.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Verzeichnisse definieren

 Zunächst müssen Sie die Verzeichnisse definieren, in denen Sie die Dateien entsprechend ihrem Format speichern möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis. Wir erstellen die Verzeichnisse „Supported“, „Unknown“, „Encrypted“ und „Pre97“, sofern diese noch nicht vorhanden sind.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Erstellen Sie die Verzeichnisse, falls sie noch nicht vorhanden sind.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Schritt 2: Dateien durchsuchen

 Dann verwenden wir die`GetFiles` Methode der`Directory` Klasse, um die Liste der Dateien im angegebenen Verzeichnis abzurufen. Wir verwenden auch a`Where` -Klausel, um eine bestimmte Datei mit dem Namen „Beschädigtes Dokument.docx“ auszuschließen.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Schritt 3: Ermitteln Sie das Format jeder Datei

 Wir durchlaufen jede Datei in der Liste und verwenden die`DetectFileFormat` Methode der`FileFormatUtil` Klasse, um das Format der Datei zu erkennen. Wir zeigen auch den erkannten Dokumenttyp an.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Zeigen Sie den Dokumenttyp an
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
// ... Fälle für andere unterstützte Dokumentformate hinzufügen
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

Das ist alles ! Sie haben das Format verschiedener Dokumentdateien mit Aspose.Words für .NET erfolgreich erkannt.

### Beispielquellcode zur Dateiformaterkennung mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Erstellen Sie die Verzeichnisse, falls sie noch nicht vorhanden sind.
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

		// Zeigen Sie den Dokumenttyp an
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

### FAQ zur Erkennung von Dokumentdateiformaten

#### Wie erkennt man das Format einer Dokumentdatei mit Aspose.Words für .NET?

 Um das Format einer Dokumentdatei mit Aspose.Words für .NET zu erkennen, können Sie die im Tutorial bereitgestellten Schritte befolgen. Verwendung der`DetectFileFormat` Methode der`FileFormatUtil` Mit der Klasse können Sie das Format der Dokumentdatei erkennen. Dadurch können Sie feststellen, ob es sich um ein Microsoft Word 97-2003-Dokument, eine Vorlage, ein Office Open XML WordprocessingML-Dokument oder andere unterstützte Formate handelt. Der im Tutorial bereitgestellte Code führt Sie durch die Implementierung dieser Funktion.

#### Welche Dokumentformate unterstützt Aspose.Words für .NET?

Aspose.Words für .NET unterstützt eine Vielzahl von Dokumentformaten, darunter Microsoft Word 97-2003-Dokumente (DOC), Vorlagen (DOT), Office Open XML WordprocessingML-Dokumente (DOCX), Office Open XML WordprocessingML-Dokumente mit Makros (DOCM) und Office Open XML WordprocessingML-Vorlagen ohne Makros (DOTX), Office Open XML WordprocessingML-Vorlagen mit Makros (DOTM), flache OPC-Dokumente, RTF-Dokumente, Microsoft Word 2003 WordprocessingML-Dokumente, HTML-Dokumente, MHTML-Dokumente (Webarchiv), OpenDocument Text-Dokumente (ODT), OpenDocument Text (OTT)-Vorlagen, MS Word 6- oder Word 95-Dokumente und unbekannte Dokumentformate.

#### Wie gehe ich bei der Formaterkennung mit verschlüsselten Dokumentdateien um?

 Wenn Sie das Format einer Dokumentdatei ermitteln möchten, können Sie Folgendes verwenden`IsEncrypted` Eigentum der`FileFormatInfo` Objekt, um zu prüfen, ob die Datei verschlüsselt ist. Wenn die Datei verschlüsselt ist, können Sie zusätzliche Schritte unternehmen, um diesen speziellen Fall zu behandeln, z. B. das Kopieren der Datei in ein Verzeichnis, das für verschlüsselte Dokumente vorgesehen ist. Du kannst den ... benutzen`File.Copy` Methode, um dies zu tun.

#### Welche Maßnahmen sollten ergriffen werden, wenn das Format eines Dokuments unbekannt ist?

Wenn das Format eines Dokuments unbekannt ist, können Sie es auf eine für Ihre Anwendung spezifische Weise behandeln. In dem im Tutorial bereitgestellten Beispiel wird das Dokument in ein bestimmtes Verzeichnis kopiert, das für Dokumente unbekannten Formats vorgesehen ist. Sie können diese Aktion an Ihre spezifischen Bedürfnisse anpassen.

#### Gibt es weitere Funktionen von Aspose.Words für .NET, die in Verbindung mit der Dokumentformaterkennung verwendet werden können?

Ja, Aspose.Words für .NET bietet viele weitere Funktionen zum Verarbeiten und Bearbeiten von Word-Dokumenten. Sie können die Bibliothek beispielsweise verwenden, um Text, Bilder oder Metadaten aus Dokumenten zu extrahieren, Formatierungsänderungen anzuwenden, Dokumente zusammenzuführen, Dokumente in verschiedene Formate zu konvertieren und vieles mehr.