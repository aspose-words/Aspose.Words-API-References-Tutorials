---
title: Wmf 글꼴을 메타파일 크기로 조정하여 PDF 크기 줄이기
linktitle: Wmf 글꼴을 메타파일 크기로 조정하여 PDF 크기 줄이기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF로 변환할 때 wmf 글꼴 크기를 메타파일 크기로 축소하여 PDF 크기를 줄이는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

이 문서에서는 .NET용 Aspose.Words를 사용하여 wmf 글꼴을 메타파일 크기로 조정하여 PDF 크기를 줄이는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 PDF로 변환할 때 WMF 글꼴 크기 조정을 활성화하거나 비활성화하는 방법을 이해할 수 있습니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리를 설치하고 구성했는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: 문서 디렉터리 정의

 시작하려면 문서가 있는 디렉터리의 경로를 정의해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 업로드

다음으로 처리하려는 문서를 로드해야 합니다. 이 예에서는 문서가 "WMF with text.docx"이고 지정된 문서 디렉터리에 있다고 가정합니다.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## 3단계: 메타파일 렌더링 옵션 구성

 메타파일 크기에 맞게 WMF 글꼴 크기 조정을 활성화하거나 비활성화하려면 다음을 구성해야 합니다.`MetafileRenderingOptions`물체. 이 예에서는 다음을 설정하여 글꼴 크기 조정을 비활성화합니다.`ScaleWmfFontsToMetafileSize`재산`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## 4단계: 메타파일 렌더링 옵션을 사용하여 PDF로 저장 옵션 구성

마지막으로 앞서 구성한 메타파일 렌더링 옵션을 사용하여 PDF로 저장 옵션을 구성할 수 있습니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## 5단계: 메타파일 렌더링 옵션을 사용하여 문서를 PDF로 저장

이전에 구성한 저장 옵션을 사용하여 문서를 PDF 형식으로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

그게 다야 ! 변환할 때 메타파일 크기에 맞게 WMF 글꼴 크기 조정을 성공적으로 활성화 또는 비활성화했습니다.

.NET용 Aspose.Words를 사용하는 PDF 문서.

### .NET용 Aspose.Words를 사용하여 WMF 글꼴을 메타파일 크기로 조정하는 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Aspose.Words가 일부 메타파일 레코드를 벡터 그래픽으로 올바르게 렌더링할 수 없는 경우
	// 그런 다음 Aspose.Words는 이 메타파일을 비트맵으로 렌더링합니다.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 PDF 문서에서 WMF 글꼴 크기를 메타파일 크기로 조정하거나 비활성화하는 방법을 설명했습니다. 설명된 단계를 수행하면 PDF 문서로 변환할 때 메타파일 크기에 맞게 WMF 글꼴 크기를 조정해야 하는지 여부를 쉽게 제어할 수 있습니다. 이렇게 하면 생성된 PDF 파일의 크기를 줄이고 렌더링 성능을 향상시키는 데 도움이 될 수 있습니다. 문서의 올바른 경로를 지정하고 필요에 따라 메타파일 렌더링 옵션을 구성하십시오.

### 자주 묻는 질문

#### 질문: PDF 문서에서 WMF 글꼴 크기를 메타파일 크기로 조정한다는 것은 무엇입니까?
A: PDF 문서에서 WMF 글꼴 크기를 메타파일 크기로 조정하는 것은 PDF 문서로 변환할 때 메타파일 크기에 맞게 WMF 글꼴 크기를 조정해야 하는지 여부를 제어하는 기능입니다. 이 기능을 활성화하면 WMF 글꼴의 크기가 메타파일 크기에 맞게 조정되어 생성된 PDF 문서의 크기가 줄어들 수 있습니다.

#### Q: .NET용 Aspose.Words를 사용하여 PDF 문서의 메타파일 크기에 맞게 WMF 글꼴 크기 조정을 활성화하거나 비활성화하려면 어떻게 해야 합니까?
A: .NET용 Aspose.Words를 사용하여 PDF 문서에서 WMF 글꼴 크기를 메타파일 크기로 조정하거나 비활성화하려면 다음 단계를 따르세요.

 교체하여 문서가 있는 디렉토리 경로를 설정하십시오.`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로로.

 다음을 사용하여 처리하려는 문서를 로드합니다.`Document` 클래스를 지정하고 지정된 문서 디렉터리에 있는 Word 문서의 경로를 지정합니다.

 인스턴스를 생성하여 메타파일 렌더링 옵션을 구성합니다.`MetafileRenderingOptions` 수업과 설정`ScaleWmfFontsToMetafileSize`재산`true` WMF 글꼴을 메타파일 크기로 조정하거나`false` 이 기능을 비활성화하려면

 인스턴스를 생성하여 PDF로 저장 옵션을 구성합니다.`PdfSaveOptions` 클래스를 사용하고 이전에 구성한 메타파일 렌더링 옵션을 사용합니다.

 다음을 사용하여 문서를 PDF 형식으로 저장합니다.`Save` 의 방법`Document` 경로와 저장 옵션을 지정하는 클래스입니다.

#### 질문: PDF 문서에서 WMF 글꼴 크기를 메타파일 크기로 조정하면 어떤 이점이 있습니까?
A: PDF 문서에서 WMF 글꼴 크기를 메타파일 크기로 조정하면 다음과 같은 이점이 있습니다.

PDF 파일 크기 감소: WMF 글꼴 크기를 메타파일 크기로 조정하면 글꼴 크기를 메타파일 요구 사항에 맞게 조정하여 생성된 PDF 문서의 크기를 줄일 수 있습니다.

향상된 성능: WMF 글꼴 크기를 메타파일 크기에 맞게 조정하면 PDF 문서 렌더링이 더 빠르고 효율적일 수 있습니다.