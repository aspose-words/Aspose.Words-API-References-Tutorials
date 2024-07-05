---
title: PDF 문서에서 사용자 정의 속성 내보내기
linktitle: PDF 문서에서 사용자 정의 속성 내보내기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 PDF로 변환할 때 사용자 정의 속성을 내보내는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/custom-properties-export/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서의 사용자 정의 속성을 PDF 문서로 내보내는 단계를 안내합니다. 사용자 정의 속성을 내보내면 생성된 PDF 문서에 추가 정보를 포함할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 생성 및 사용자 정의 속성 추가

Document 클래스의 인스턴스를 생성하여 시작합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2단계: 사용자 정의 속성 추가
 다음으로 원하는 사용자 정의 속성을 추가합니다. 예를 들어 값이 "Aspose"인 "회사" 속성을 추가하려면`Add` CustomDocumentProperties 컬렉션의 메서드:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

필요한 만큼 사용자 정의 속성을 추가할 수 있습니다.

## 3단계: PDF 내보내기 옵션 설정

PdfSaveOptions 클래스의 인스턴스를 만들고 사용자 정의 속성을 내보내는 방법을 지정합니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

이 옵션은 PDF로 변환할 때 사용자 정의 속성 내보내기를 제어합니다.

## 4단계: 문서를 PDF로 변환

 사용`Save` 변환 옵션을 지정하여 문서를 PDF로 변환하는 방법:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

변환된 PDF를 저장할 올바른 경로를 지정했는지 확인하세요.

### .NET용 Aspose.Words를 사용하여 사용자 정의 속성 내보내기에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 문서에서 사용자 정의 속성을 내보내는 전체 소스 코드입니다.


```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 PDF로 변환할 때 문서의 사용자 정의 속성을 쉽게 내보낼 수 있습니다.


## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서의 사용자 정의 속성을 PDF 문서로 내보내는 방법을 설명했습니다. 설명된 단계를 따르면 문서의 사용자 정의 속성을 내보내 생성된 PDF 문서에 추가 정보를 쉽게 포함할 수 있습니다. Aspose.Words for .NET의 기능을 활용하여 사용자 정의 속성을 내보내 PDF 문서를 개인화하고 풍부하게 만드세요.

### 자주 묻는 질문

#### Q: 사용자 정의 속성을 PDF 문서로 내보내는 것이 무엇입니까?
A: 사용자 정의 속성을 PDF 문서로 내보내면 생성된 PDF 문서에 추가 정보를 포함할 수 있습니다. 사용자 정의 속성은 태그, 키워드 또는 자격 증명과 같은 문서와 관련된 메타데이터입니다. 이러한 사용자 정의 속성을 내보내면 PDF 문서를 볼 때 사용자가 해당 속성을 사용할 수 있습니다.

#### Q: .NET용 Aspose.Words를 사용하여 문서의 사용자 정의 속성을 PDF 문서로 내보내려면 어떻게 해야 합니까?
A: .NET용 Aspose.Words를 사용하여 문서의 사용자 정의 속성을 PDF 문서로 내보내려면 다음 단계를 따르십시오.

 인스턴스를 생성합니다.`Document` 수업.

 다음을 사용하여 원하는 사용자 정의 속성을 추가합니다.`CustomDocumentProperties` 수집. 예를 들어`Add` 값이 "Aspose"인 "회사" 속성을 추가하는 메서드입니다.

 인스턴스를 생성합니다.`PdfSaveOptions` 클래스를 사용하여 사용자 정의 속성을 내보내는 방법을 지정합니다.`CustomPropertiesExport` 재산. 그만큼`PdfCustomPropertiesExport.Standard` 값은 기본 설정에 따라 사용자 정의 속성을 내보냅니다.

 사용`Save` 의 방법`Document` 변환 옵션을 지정하여 문서를 PDF로 변환하는 클래스입니다.

#### Q: PDF 문서의 사용자 정의 속성에 어떻게 액세스할 수 있습니까?
A: PDF 문서의 사용자 정의 속성에 액세스하려면 문서 속성 보기를 지원하는 호환 PDF 리더를 사용할 수 있습니다. Adobe Acrobat Reader와 같은 가장 일반적인 PDF 리더는 PDF 문서의 메타데이터 및 속성에 대한 액세스를 제공합니다. 일반적으로 이러한 옵션은 "파일" 메뉴에서 찾거나 문서를 마우스 오른쪽 버튼으로 클릭하고 "속성"을 선택하여 찾을 수 있습니다.