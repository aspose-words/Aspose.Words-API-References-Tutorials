---
title: 콤보 상자 콘텐츠 제어
linktitle: 콤보 상자 콘텐츠 제어
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 콤보 상자 콘텐츠 컨트롤을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/combo-box-content-control/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 콤보 상자 콘텐츠 컨트롤을 만드는 방법을 설명합니다. 콤보 상자 콘텐츠 컨트롤을 사용하면 사용자가 드롭다운 목록에서 항목을 선택할 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서를 저장하려는 디렉토리의 실제 경로를 사용하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 및 StructuredDocumentTag 만들기
 새 인스턴스를 생성합니다.`Document` 수업과`StructuredDocumentTag` 콤보 상자 콘텐츠 컨트롤을 나타냅니다. 지정하다`SdtType.ComboBox` 유형과`MarkupLevel.Block` 블록 수준 콤보 상자를 만들기 위한 마크업 수준으로 사용됩니다.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## 3단계: 콤보 상자에 항목 추가
 다음을 사용하여 콤보 상자에 항목을 추가합니다.`ListItems` 의 재산`StructuredDocumentTag` 각 항목은`SdtListItem` 표시 텍스트와 값을 취하는 객체입니다. 이 예에서는 콤보 상자에 세 가지 항목을 추가합니다.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## 4단계: 문서에 StructuredDocumentTag 추가
 다음을 사용하여 문서 본문에 콤보 상자 콘텐츠 컨트롤을 추가합니다.`AppendChild` 문서의 첫 번째 섹션 본문의 메서드입니다.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## 5단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.ComboBoxContentControl.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### .NET용 Aspose.Words를 사용하는 콤보 상자 콘텐츠 제어의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

그게 다야! Aspose.Words for .NET을 사용하여 Word 문서에 콤보 상자 콘텐츠 컨트롤을 성공적으로 만들었습니다.