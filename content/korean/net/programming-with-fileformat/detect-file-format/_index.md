---
title: 문서 파일 형식 감지
linktitle: 문서 파일 형식 감지
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서 파일 형식을 감지하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-fileformat/detect-file-format/
---

이 문서에서는 Aspose.Words for .NET에서 문서 파일 형식 감지 기능을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 다양한 문서 파일의 형식을 감지하는 방법을 이해할 수 있습니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리를 설치하고 구성했는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: 디렉터리 정의

 시작하려면 파일 형식에 따라 파일을 저장할 디렉터리를 정의해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"`문서 디렉토리의 실제 경로를 사용하세요. "지원됨", "알 수 없음", "암호화됨" 및 "Pre97" 디렉터리가 아직 없으면 생성합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// 디렉토리가 아직 존재하지 않는 경우 디렉토리를 생성하십시오.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## 2단계: 파일 찾아보기

 그런 다음 우리는`GetFiles` 의 방법`Directory` 지정된 디렉터리의 파일 목록을 가져오는 클래스입니다. 우리는 또한`Where` "Corrupted document.docx"라는 특정 파일을 제외하는 절입니다.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## 3단계: 각 파일의 형식 감지

 목록의 각 파일을 반복하고 다음을 사용합니다.`DetectFileFormat` 의 방법`FileFormatUtil` 파일의 형식을 감지하는 클래스입니다. 감지된 문서 유형도 표시됩니다.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// 문서 유형 표시
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
// ... 기타 지원되는 문서 형식에 대한 사례 추가
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

그게 다야 ! .NET용 Aspose.Words를 사용하여 다양한 문서 파일의 형식을 성공적으로 감지했습니다.

### .NET용 Aspose.Words를 사용한 파일 형식 감지를 위한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// 디렉토리가 아직 존재하지 않는 경우 디렉토리를 작성하십시오.
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

		// 문서 유형 표시
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

### 문서 파일 형식 감지에 대한 FAQ

#### .NET용 Aspose.Words를 사용하여 문서 파일 형식을 감지하는 방법은 무엇입니까?

 .NET용 Aspose.Words를 사용하여 문서 파일 형식을 감지하려면 튜토리얼에 제공된 단계를 따르세요. 사용하여`DetectFileFormat` 의 방법`FileFormatUtil` 클래스를 사용하면 문서 파일의 형식을 감지할 수 있습니다. 이를 통해 Microsoft Word 97-2003 문서, 템플릿, Office Open XML WordprocessingML 문서 또는 기타 지원되는 형식인지 확인할 수 있습니다. 튜토리얼에 제공된 코드는 이 기능을 구현하는 과정을 안내합니다.

#### .NET용 Aspose.Words는 어떤 문서 형식을 지원합니까?

Aspose.Words for .NET은 Microsoft Word 97-2003 문서(DOC), 템플릿(DOT), Office Open XML WordprocessingML 문서(DOCX), 매크로가 포함된 Office Open XML WordprocessingML 문서(DOCM), Office Open을 포함한 다양한 문서 형식을 지원합니다. 매크로가 없는 XML WordprocessingML 템플릿(DOTX), 매크로가 있는 Office Open XML WordprocessingML 템플릿(DOTM), Flat OPC 문서, RTF 문서, Microsoft Word 2003 WordprocessingML 문서, HTML 문서, MHTML(웹 아카이브) 문서, OpenDocument Text(ODT) 문서, OTT(OpenDocument Text) 템플릿, MS Word 6 또는 Word 95 문서 및 알 수 없는 문서 형식입니다.

#### 형식 감지 중 암호화된 문서 파일을 처리하는 방법은 무엇입니까?

 문서 파일의 형식을 감지할 때 다음을 사용할 수 있습니다.`IsEncrypted` 의 재산`FileFormatInfo` 파일이 암호화되었는지 확인하는 개체입니다. 파일이 암호화된 경우 암호화된 문서 전용 디렉터리에 파일을 복사하는 등 특정 사례를 처리하기 위한 추가 단계를 수행할 수 있습니다. 당신은 사용할 수 있습니다`File.Copy` 이를 수행하는 방법.

#### 문서의 형식을 알 수 없는 경우 어떤 조치를 취해야 합니까?

문서 형식을 알 수 없는 경우 애플리케이션에 맞는 방식으로 처리하도록 결정할 수 있습니다. 튜토리얼에 제공된 예에서 문서는 알 수 없는 형식의 문서 전용 디렉터리에 복사됩니다. 특정 요구 사항에 맞게 이 작업을 사용자 정의할 수 있습니다.

#### 문서 형식 감지와 함께 사용할 수 있는 .NET용 Aspose.Words의 다른 기능이 있습니까?

예, Aspose.Words for .NET은 Word 문서 처리 및 조작을 위한 다양한 기능을 제공합니다. 예를 들어 라이브러리를 사용하여 문서에서 텍스트, 이미지 또는 메타데이터를 추출하고, 서식 변경 사항을 적용하고, 문서를 병합하고, 문서를 다른 형식으로 변환하는 등의 작업을 수행할 수 있습니다.