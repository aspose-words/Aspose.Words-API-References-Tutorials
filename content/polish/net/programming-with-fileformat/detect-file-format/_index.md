---
title: Wykryj format pliku dokumentu
linktitle: Wykryj format pliku dokumentu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący wykrywania formatu pliku dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-fileformat/detect-file-format/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący korzystania z funkcji wykrywania formatu pliku dokumentu w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz w stanie zrozumieć, jak wykryć format różnych plików dokumentów.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj katalogi

 Na początek musisz zdefiniować katalogi, w których chcesz przechowywać pliki, zgodnie z ich formatem. Zastępować`"YOUR DOCUMENT DIRECTORY"` rzeczywistą ścieżką do katalogu dokumentów. Tworzymy katalogi „Obsługiwane”, „Nieznane”, „Zaszyfrowane” i „Pre97”, jeśli jeszcze nie istnieją.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Utwórz katalogi, jeśli jeszcze nie istnieją.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Krok 2: Przeglądaj pliki

 Następnie używamy`GetFiles` metoda`Directory` class, aby uzyskać listę plików w określonym katalogu. Używamy również A`Where` klauzula wykluczająca określony plik o nazwie „Uszkodzony dokument.docx”.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Krok 3: Wykryj format każdego pliku

 Przeglądamy każdy plik na liście i używamy metody`DetectFileFormat` metoda`FileFormatUtil` class, aby wykryć format pliku. Wyświetlamy także wykryty typ dokumentu.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Wyświetl typ dokumentu
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
// ... Dodaj przypadki dla innych obsługiwanych formatów dokumentów
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

To wszystko ! Pomyślnie wykrył format różnych plików dokumentów przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy do wykrywania formatu pliku za pomocą Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Utwórz katalogi, jeśli jeszcze nie istnieją.
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

		// Wyświetl typ dokumentu
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

### Często zadawane pytania dotyczące wykrywania formatu pliku dokumentu

#### Jak wykryć format pliku dokumentu za pomocą Aspose.Words dla .NET?

 Aby wykryć format pliku dokumentu za pomocą Aspose.Words dla .NET, możesz wykonać kroki opisane w samouczku. Używając`DetectFileFormat` metoda`FileFormatUtil` class pozwoli Ci wykryć format pliku dokumentu. Umożliwi to określenie, czy jest to dokument programu Microsoft Word 97-2003, szablon, dokument Office Open XML WordprocessingML, czy też inny obsługiwany format. Kod podany w samouczku przeprowadzi Cię przez proces wdrażania tej funkcji.

#### Jakie formaty dokumentów obsługuje Aspose.Words dla .NET?

Aspose.Words dla .NET obsługuje różne formaty dokumentów, w tym dokumenty Microsoft Word 97-2003 (DOC), szablony (DOT), dokumenty Office Open XML WordprocessingML (DOCX), dokumenty Office Open XML WordprocessingML z makrami (DOCM), Office Open Szablony XML WordprocessingML bez makr (DOTX), szablony Office Open XML WordprocessingML z makrami (DOTM), dokumenty Flat OPC, dokumenty RTF, dokumenty Microsoft Word 2003 WordprocessingML, dokumenty HTML, dokumenty MHTML (archiwum internetowe), dokumenty OpenDocument Text (ODT), Szablony OpenDocument Text (OTT), dokumenty MS Word 6 lub Word 95 i nieznane formaty dokumentów.

#### Jak obsługiwać zaszyfrowane pliki dokumentów podczas wykrywania formatu?

 Podczas wykrywania formatu pliku dokumentu możesz użyć metody`IsEncrypted` własność`FileFormatInfo` obiekt, aby sprawdzić, czy plik jest zaszyfrowany. Jeśli plik jest zaszyfrowany, możesz podjąć dodatkowe kroki, aby obsłużyć ten konkretny przypadek, np. skopiować plik do katalogu przeznaczonego na zaszyfrowane dokumenty. Możesz skorzystać z`File.Copy` metodę, aby to zrobić.

#### Jakie działania należy podjąć, gdy format dokumentu nie jest znany?

Gdy format dokumentu nie jest znany, możesz zdecydować się na obsługę go w sposób specyficzny dla Twojej aplikacji. W przykładzie podanym w tutorialu dokument kopiowany jest do określonego katalogu dedykowanego dokumentom o nieznanym formacie. Możesz dostosować tę akcję do swoich konkretnych potrzeb.

#### Czy są jakieś inne funkcje Aspose.Words dla .NET, których można używać w połączeniu z wykrywaniem formatu dokumentu?

Tak, Aspose.Words dla .NET oferuje wiele innych funkcji do przetwarzania i manipulowania dokumentami Word. Biblioteki można na przykład używać do wyodrębniania tekstu, obrazów lub metadanych z dokumentów, stosowania zmian w formatowaniu, scalania dokumentów, konwertowania dokumentów do różnych formatów i nie tylko.