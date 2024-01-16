---
title: 확인란 유형 콘텐츠 제어
linktitle: 확인란 유형 콘텐츠 제어
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 확인란 유형 콘텐츠 컨트롤을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/check-box-type-content-control/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 확인란 유형 콘텐츠 컨트롤을 만드는 방법을 설명합니다. 확인란 콘텐츠 제어를 통해 사용자는 문서 내의 확인란을 선택하거나 선택 취소할 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서를 저장하려는 디렉토리의 실제 경로를 사용하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 및 DocumentBuilder 만들기
 새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 문서의 내용을 작성합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 확인란 유형 콘텐츠 컨트롤 추가
 만들기`StructuredDocumentTag` ~와 함께`SdtType.Checkbox` 확인란 콘텐츠 컨트롤을 나타냅니다. 지정하다`MarkupLevel.Inline` 텍스트 안에 배치합니다.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## 4단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.CheckBoxTypeContentControl.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### .NET용 Aspose.Words를 사용하는 확인란 유형 콘텐츠 제어의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

그게 다야! Aspose.Words for .NET을 사용하여 Word 문서에 확인란 유형 콘텐츠 제어를 성공적으로 만들었습니다.