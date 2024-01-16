---
title: Word 문서에서 선호하는 컨트롤 유형
linktitle: Word 문서에서 선호하는 컨트롤 유형
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 HTML 문서를 로드할 때 Word 문서에서 기본 컨트롤 유형을 지정하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlloadoptions/preferred-control-type/
---
이 문서에서는 Aspose.Words for .NET에서 기본 컨트롤 유형 기능을 사용하는 방법에 대한 단계별 가이드를 제공합니다. 코드의 각 부분을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 HTML 문서를 로드할 때 선호하는 컨트롤 유형을 지정하는 방법을 이해할 수 있을 것입니다.

시작하기 전에 프로젝트에 Aspose.Words for .NET 라이브러리를 설치하고 구성했는지 확인하세요. Aspose 웹사이트에서 라이브러리와 설치 지침을 찾을 수 있습니다.

## 1단계: HTML 코드 정의

 시작하려면 문서로 로드하려는 HTML 코드를 정의해야 합니다. 이 예에서는`html` 옵션이 있는 선택기의 HTML 코드가 포함된 변수입니다.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## 2단계: HTML 로딩 옵션 설정

 다음으로 우리는`HtmlLoadOptions` 객체를 설정하고`PreferredControlType`재산`HtmlControlType.StructuredDocumentTag`. 이는 Aspose.Words가 로드할 때 HTML을 나타내기 위해 StructuredDocumentTags를 사용하도록 지시합니다.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## 3단계: 문서 로드 및 저장

 우리는`Document` 앞에서 정의한 로드 옵션을 사용하여 메모리 스트림에서 HTML 코드를 로드하는 클래스입니다. 그런 다음 지정된 디렉토리에 문서를 저장합니다.`.docx`파일 형식.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### .NET용 Aspose.Words를 사용하여 선호하는 컨트롤 유형에 대한 예제 소스 코드

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

그게 다야 ! .NET용 Aspose.Words를 사용하여 HTML 문서를 로드할 때 기본 컨트롤 유형을 성공적으로 지정했습니다.

## 결론

 이 단계별 가이드를 따라 HTML 문서를 로드할 때 Aspose.Words for .NET의 "선호 컨트롤 유형" 기능을 사용하여 원하는 컨트롤 유형을 지정하는 방법을 배웠습니다. 설정`PreferredControlType`재산`HtmlControlType.StructuredDocumentTag` Aspose.Words는 HTML 콘텐츠의 더 나은 표현과 처리를 위해 SDT(StructuredDocumentTags)를 사용할 수 있습니다. 특정 요구 사항에 맞게 다른 제어 유형도 탐색할 수 있습니다. 이 기능을 사용하면 Aspose.Words를 사용하여 C# 애플리케이션에서 HTML 문서를 정확하고 효율적으로 처리하는 데 도움이 됩니다.

### Word 문서에서 선호하는 컨트롤 유형에 대한 FAQ

#### Q: Aspose.Words for .NET의 "선호 컨트롤 유형" 기능은 무엇입니까?

A: "기본 컨트롤 유형" 기능을 사용하면 HTML 문서를 로드할 때 HTML 요소를 나타내기 위해 기본 컨트롤 유형을 지정할 수 있습니다. HTML 콘텐츠를 더 잘 표현하고 처리하기 위해 적절한 컨트롤 유형을 선택하는 데 도움이 됩니다.

#### Q: HTML 문서를 로드할 때 기본 컨트롤 유형을 어떻게 설정합니까?

 A: 선호하는 컨트롤 유형을 설정하려면`HtmlLoadOptions` 개체를 설정하고`PreferredControlType` 원하는 재산에`HtmlControlType` . 제공된 예에서는`HtmlControlType.StructuredDocumentTag` 사용.

#### Q: 기본 컨트롤 유형으로 SDT(StructuredDocumentTags)를 사용하는 것의 의미는 무엇입니까?

A: SDT(StructuredDocumentTags)는 Word 문서의 복잡한 콘텐츠와 컨트롤을 나타내는 데 사용할 수 있는 XML 기반 요소입니다. SDT를 기본 컨트롤 유형으로 사용하면 HTML 콘텐츠의 호환성과 표현이 향상될 수 있습니다.

#### Q: Aspose.Words가 HTML 문서를 로드할 때 기본 컨트롤 유형을 사용하도록 하려면 어떻게 해야 합니까?

 A: 설정함으로써`PreferredControlType`재산`HtmlControlType.StructuredDocumentTag`예제 소스 코드에 표시된 것처럼 Aspose.Words는 문서를 로드할 때 SDT를 사용하여 HTML 요소를 나타냅니다.

#### Q: 다른 컨트롤 유형을 기본 옵션으로 사용할 수 있나요?

 A: 네, 그 외에는`HtmlControlType.StructuredDocumentTag` , Aspose.Words for .NET은 다음과 같은 다른 컨트롤 유형을 지원합니다.`HtmlControlType.ContentControl` 그리고`HtmlControlType.CustomXmlMarkup`.