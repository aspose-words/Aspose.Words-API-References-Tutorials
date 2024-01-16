---
title: 암호화된 Word 문서 확인
linktitle: 암호화된 Word 문서 확인
second_title: Aspose.Words 문서 처리 API
description: Word 문서가 .NET용 Aspose.Words로 암호화되었는지 확인하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-fileformat/verify-encrypted-document/
---

이 문서에서는 Aspose.Words for .NET에서 암호화된 Word 문서 확인 기능을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 문서가 암호화되었는지 확인하는 방법을 이해할 수 있습니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리를 설치하고 구성했는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: 문서 디렉터리 정의

 시작하려면 문서가 있는 디렉터리의 경로를 정의해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 파일 형식 감지

 다음으로 우리는`DetectFileFormat` 의 방법`FileFormatUtil` 파일 형식 정보를 감지하는 클래스입니다. 이 예에서는 암호화된 문서가 "Encrypted.docx"라고 하며 지정된 문서 디렉터리에 있다고 가정합니다.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## 3단계: 문서가 암호화되었는지 확인

 우리는`IsEncrypted` 의 재산`FileFormatInfo`문서가 암호화되었는지 확인하는 개체입니다. 이 속성은 다음을 반환합니다.`true` 문서가 암호화되어 있으면 그렇지 않으면 반환됩니다.`false`. 콘솔에 결과를 표시합니다.

```csharp
Console.WriteLine(info.IsEncrypted);
```

그게 다야 ! .NET용 Aspose.Words를 사용하여 문서가 암호화되었는지 성공적으로 확인했습니다.

### .NET용 Aspose.Words를 사용하여 암호화된 문서를 확인하기 위한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## 자주 묻는 질문

### Q: 암호화된 Word 문서를 확인하는 단계는 무엇입니까?

암호화된 Word 문서를 확인하는 단계는 다음과 같습니다.

문서 디렉터리를 정의합니다.

파일 형식을 감지합니다.

문서가 암호화되어 있는지 확인하세요.

### Q: 문서 디렉토리는 어떻게 설정하나요?
 문서 디렉토리를 설정하려면 다음을 바꿔야 합니다.`"YOUR DOCUMENT DIRECTORY"` 다음 코드에서 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Q: 파일 형식을 감지하는 방법은 무엇입니까?
 당신은 사용할 수 있습니다`DetectFileFormat` 의 방법`FileFormatUtil`파일 형식 정보를 감지하는 클래스입니다. 다음 예에서는 암호화된 문서의 이름이 "Encrypted.docx"이고 지정된 문서 디렉터리에 있다고 가정합니다.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### Q: 문서가 암호화되었는지 어떻게 확인하나요?
 당신은 사용할 수 있습니다`IsEncrypted` 의 재산`FileFormatInfo`문서가 암호화되었는지 확인하는 개체입니다. 이 속성은 다음을 반환합니다.`true` 문서가 암호화되어 있으면 그렇지 않으면 반환됩니다.`false`. 결과가 콘솔에 표시됩니다.

```csharp
Console.WriteLine(info.IsEncrypted);
```

### Q: .NET용 Aspose.Words를 사용하여 문서가 암호화되었는지 확인하는 방법은 무엇입니까?
이 튜토리얼에 언급된 단계를 따르고 제공된 소스 코드를 실행하면 Aspose.Words for .NET을 사용하여 문서가 암호화되었는지 확인할 수 있습니다.
