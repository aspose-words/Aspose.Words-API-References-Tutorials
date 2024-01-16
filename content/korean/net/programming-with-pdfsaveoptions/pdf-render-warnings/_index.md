---
title: PDF 렌더링 경고
linktitle: PDF 렌더링 경고
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF 렌더링 경고를 처리하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

이 문서에서는 Aspose.Words for .NET에서 PDF 렌더링 경고 기능을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 PDF로 변환할 때 렌더링 경고를 처리하는 방법을 이해할 수 있습니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리를 설치하고 구성했는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: 문서 디렉터리 정의

 시작하려면 문서가 있는 디렉터리의 경로를 정의해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 업로드

다음으로 처리하려는 문서를 로드해야 합니다. 이 예에서는 문서가 "WMF with image.docx"이고 지정된 문서 디렉터리에 있다고 가정합니다.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## 3단계: 렌더링 경고가 포함된 PDF로 저장 옵션 구성

 PDF로 변환할 때 렌더링 경고를 처리하려면 다음을 구성해야 합니다.`MetafileRenderingOptions` 메타파일이 렌더링되는 방식을 지정하는 개체입니다. 우리는 또한`HandleDocumentWarnings` 문서를 저장할 때 생성되는 경고를 처리하는 옵션입니다.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## 4단계: 렌더링 경고와 함께 문서를 PDF로 저장

마지막으로 이전에 구성한 저장 옵션을 사용하여 문서를 PDF 형식으로 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## 5단계: 렌더링 경고 처리

문서를 저장할 때 생성된 렌더링 경고는 사용자 정의 경고 핸들러를 사용하여 검색할 수 있습니다. 이 예에서는 단순히 각 경고에 대한 설명을 인쇄합니다.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

그게 다야 ! 문서 변환 시 렌더링 경고를 성공적으로 처리했습니다.

  .NET용 Aspose.Words를 사용하여 PDF로 변환합니다.

### .NET용 Aspose.Words를 사용한 PDF 렌더링 경고의 샘플 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	//Aspose.Words가 일부 메타파일 레코드를 올바르게 렌더링할 수 없는 경우
	// 벡터 그래픽으로 변환하면 Aspose.Words는 이 메타파일을 비트맵으로 렌더링합니다.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// 파일이 성공적으로 저장되는 동안 저장 중에 발생한 렌더링 경고가 여기에 수집됩니다.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

### 자주 묻는 질문

#### Q: .NET용 Aspose.Words의 PDF 렌더링 경고 기능은 무엇입니까?
Aspose.Words for .NET의 PDF 렌더링 경고 기능은 문서를 PDF로 변환할 때 생성되는 경고를 관리하는 데 도움이 됩니다. 변환된 문서의 품질과 무결성을 보장하기 위해 렌더링 경고를 감지하고 해결하는 방법을 제공합니다.

#### Q: .NET용 Aspose.Words에서 이 기능을 어떻게 사용할 수 있나요?
.NET용 Aspose.Words에서 이 기능을 사용하려면 다음 단계를 따르세요.

문서가 있는 디렉터리 경로를 지정하여 문서 디렉터리를 설정합니다.

 다음을 사용하여 처리할 문서를 로드합니다.`Document` 메서드를 사용하고 파일 경로를 지정합니다.

 인스턴스를 생성하여 PDF로 저장 옵션을 구성합니다.`PdfSaveOptions` 수업. 사용`MetafileRenderingOptions` 메타파일이 렌더링되는 방법을 지정하고 설정하는 클래스`MetafileRenderingOptions.RenderingMode` 에게`MetafileRenderingMode.VectorWithFallback`.

 사용`HandleDocumentWarnings` 렌더링 경고를 처리하는 클래스입니다. 세트`doc.WarningCallback` 이 클래스의 인스턴스에.

 사용`Save` 저장 옵션을 지정하여 문서를 PDF 형식으로 저장하는 방법입니다.

그런 다음 다음을 사용하여 렌더링 경고를 처리할 수 있습니다.`HandleDocumentWarnings` 수업. 예를 들어 루프를 사용하여 각 경고에 대한 설명을 표시할 수 있습니다.

#### Q: 문서를 PDF로 변환할 때 렌더링 경고가 있었는지 어떻게 알 수 있나요?
 당신은 사용할 수 있습니다`HandleDocumentWarnings` 문서를 저장할 때 생성된 렌더링 경고를 검색하는 클래스입니다. 이 클래스에는`mWarnings` 경고에 대한 정보를 저장하는 목록입니다. 이 목록을 찾아보고 설명과 같은 각 경고의 속성에 액세스하여 적절한 조치를 취할 수 있습니다.

#### Q: PDF로 변환할 때 어떤 종류의 렌더링 경고가 생성될 수 있습니까?
PDF로 변환할 때 렌더링 경고에는 레이아웃, 누락된 글꼴, 지원되지 않는 이미지, 호환성 문제 등과 관련된 경고가 포함될 수 있습니다. 구체적인 경고는 소스 문서의 내용과 사용된 변환 옵션에 따라 달라집니다.

#### Q: 사용자 정의 방식으로 렌더링 경고를 처리할 수 있습니까?
 예. 렌더링 경고 처리를 사용자 정의하여 사용자 정의할 수 있습니다.`HandleDocumentWarnings`수업. 경고 로깅, 보고서 생성, 경고 보내기 등 애플리케이션과 관련된 경고를 관리하는 추가 기능을 추가할 수 있습니다.