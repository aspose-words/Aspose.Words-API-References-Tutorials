---
title: Определить формат файла документа
linktitle: Определить формат файла документа
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по определению формата файла документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-fileformat/detect-file-format/
---

В этой статье представлено пошаговое руководство по использованию функции определения формата файла документа в Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как определять формат различных файлов документов.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на сайте Aspose.

## Шаг 1. Определите каталоги

 Для начала вам необходимо определить каталоги, в которых вы хотите хранить файлы, в соответствии с их форматом. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов. Создаем каталоги «Поддерживаемые», «Неизвестные», «Зашифрованные» и «Pre97», если они еще не существуют.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Создайте каталоги, если они еще не существуют.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Шаг 2. Просмотрите файлы

 Затем мы используем`GetFiles` метод`Directory` class, чтобы получить список файлов в указанном каталоге. Мы также используем`Where`предложение для исключения определенного файла с именем «Поврежденный документ.docx».

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Шаг 3. Определите формат каждого файла.

 Мы просматриваем каждый файл в списке и используем`DetectFileFormat` метод`FileFormatUtil` класс для определения формата файла. Мы также отображаем обнаруженный тип документа.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Отображение типа документа
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
// ...Добавьте дела для других поддерживаемых форматов документов.
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

Вот и все! Вы успешно определили формат различных файлов документов, используя Aspose.Words для .NET.

### Пример исходного кода для определения формата файла с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Создайте каталоги, если они еще не существуют.
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

		// Отображение типа документа
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

### Часто задаваемые вопросы по определению формата файла документа

#### Как определить формат файла документа с помощью Aspose.Words для .NET?

 Чтобы определить формат файла документа с помощью Aspose.Words для .NET, вы можете выполнить шаги, представленные в руководстве. Используя`DetectFileFormat` метод`FileFormatUtil`class позволит вам определить формат файла документа. Это позволит вам определить, является ли это документом Microsoft Word 97-2003, шаблоном, документом Office Open XML WordprocessingML или другими поддерживаемыми форматами. Код, представленный в руководстве, поможет вам реализовать эту функцию.

#### Какие форматы документов поддерживает Aspose.Words for .NET?

Aspose.Words for .NET поддерживает различные форматы документов, включая документы Microsoft Word 97-2003 (DOC), шаблоны (DOT), документы Office Open XML WordprocessingML (DOCX), документы Office Open XML WordprocessingML с макросами (DOCM), Office Open Шаблоны XML WordprocessingML без макросов (DOTX), шаблоны Office Open OpenDocument Text (OTT), документы MS Word 6 или Word 95 и неизвестные форматы документов.

#### Как обращаться с зашифрованными файлами документов во время определения формата?

 При определении формата файла документа вы можете использовать`IsEncrypted` собственность`FileFormatInfo` объект, чтобы проверить, зашифрован ли файл. Если файл зашифрован, вы можете предпринять дополнительные действия для обработки этого конкретного случая, например скопировать файл в каталог, предназначенный для зашифрованных документов. Вы можете использовать`File.Copy` способ сделать это.

#### Какие действия следует предпринять, если формат документа неизвестен?

Если формат документа неизвестен, вы можете решить обработать его способом, специфичным для вашего приложения. В примере, приведенном в руководстве, документ копируется в определенный каталог, предназначенный для документов неизвестного формата. Вы можете настроить это действие в соответствии со своими потребностями.

#### Существуют ли какие-либо другие функции Aspose.Words для .NET, которые можно использовать в сочетании с определением формата документа?

Да, Aspose.Words для .NET предлагает множество других функций для обработки и управления документами Word. Например, вы можете использовать библиотеку для извлечения текста, изображений или метаданных из документов, применения изменений форматирования, объединения документов, преобразования документов в разные форматы и многого другого.