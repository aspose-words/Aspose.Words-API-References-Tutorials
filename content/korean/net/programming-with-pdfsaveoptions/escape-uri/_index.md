---
title: PDF 문서의 이스케이프 URI
linktitle: PDF 문서의 이스케이프 URI
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF 문서에서 URI를 이스케이프하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/escape-uri/
---

이 문서에서는 .NET용 Aspose.Words를 사용하여 PDF 문서에서 URI를 이스케이프하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 문서에 이스케이프된 Uri가 포함된 하이퍼링크를 삽입하는 방법을 이해할 수 있을 것입니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리를 설치하고 구성했는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: 문서 디렉터리 정의

 시작하려면 문서가 있는 디렉터리의 경로를 정의해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 및 DocumentBuilder 만들기

 다음으로 새 항목을 만들어야 합니다.`Document` 객체와`DocumentBuilder` 문서를 빌드하는 개체입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 이스케이프된 Uri를 사용하여 하이퍼링크 삽입

 사용`InsertHyperlink` 의 방법`DocumentBuilder` 문서에 하이퍼링크를 삽입하는 개체입니다. Uri는 다음을 사용하여 이스케이프해야 합니다.`Uri.EscapeUriString` 형식 오류를 방지하는 기능입니다.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), 거짓);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), 거짓);
```

## 4단계: 문서를 PDF로 저장

 마지막으로 다음을 사용하여 문서를 PDF로 저장할 수 있습니다.`Save` 의 방법`Document` 물체. 출력 파일 이름을 지정합니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

그게 다야 ! Aspose.Words for .NET을 사용하여 문서에 이스케이프된 Uri가 포함된 하이퍼링크를 성공적으로 삽입했습니다.

### .NET용 Aspose.Words를 사용하여 이스케이프하는 Uri의 샘플 소스 코드


```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", 거짓);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", 거짓);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 PDF 문서에서 URI를 이스케이프하는 방법을 다루었습니다. URI를 이스케이프하면 형식 오류를 방지하고 하이퍼링크가 PDF 문서에서 올바르게 해석되고 표시되는지 확인할 수 있습니다. 이스케이프된 URI가 포함된 하이퍼링크를 PDF 문서에 삽입하려면 설명된 단계를 따르세요. 꼭 탈출하세요.

### 자주 묻는 질문

#### Q: PDF 문서의 이스케이프 URI는 무엇이며 왜 중요한가요?
A: PDF 문서의 이스케이프 URI는 형식 오류를 방지하기 위해 URL의 특수 문자를 이스케이프 시퀀스로 변환하는 방법을 나타냅니다. URL의 특수 문자로 인해 URL 구조가 혼란스러워지고 해석이 잘못되거나 잘못된 렌더링이 발생할 수 있으므로 이는 중요합니다. 특수 문자를 이스케이프함으로써 URL이 PDF 문서에서 올바르게 해석되고 표시되도록 보장합니다.

#### Q: .NET용 Aspose.Words를 사용하여 PDF 문서의 URI를 이스케이프하려면 어떻게 해야 합니까?
A: .NET용 Aspose.Words를 사용하여 PDF 문서에서 URI를 이스케이프하려면 다음 단계를 따르세요.

 교체하여 문서가 있는 디렉토리 경로를 설정하십시오.`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로로.

 새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 문서를 빌드하는 개체입니다.

 사용`InsertHyperlink` 의 방법`DocumentBuilder` 문서에 하이퍼링크를 삽입하는 개체입니다. 다음을 사용하여 URI를 이스케이프해야 합니다.`Uri.EscapeUriString` 형식 오류를 방지하는 기능입니다.

 사용`Save` 의 방법`Document` 출력 파일의 이름을 지정하여 문서를 PDF 형식으로 저장하는 개체입니다.

#### Q: PDF 문서에서 URI를 이스케이프하면 어떤 이점이 있나요?
A: PDF 문서에서 URI 이스케이프를 수행하면 다음과 같은 이점이 있습니다.

형식 오류 방지: URI 이스케이프는 URL의 특수 문자로 인해 발생하는 형식 오류를 방지하여 URL이 PDF 문서에서 올바르게 해석되고 표시되도록 합니다.

PDF 리더와의 호환성: 이스케이프된 URI는 일반적으로 PDF 리더에서 잘 지원되므로 더 나은 호환성과 일관된 사용자 경험을 보장합니다.

#### Q: URI에서 어떤 특수 문자를 이스케이프해야 합니까?
 A: URI에서 이스케이프해야 하는 특수 문자는 공백, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.