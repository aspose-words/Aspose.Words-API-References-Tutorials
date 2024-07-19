---
title: 체크박스 현황
linktitle: 체크박스 현황
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 확인란 콘텐츠 컨트롤의 현재 상태를 검색하고 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/current-state-of-check-box/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 확인란 콘텐츠 컨트롤의 현재 상태를 검색하고 설정하는 방법을 설명합니다. 현재 상태에 따라 확인란을 선택하거나 선택 취소할 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드 및 확인란 콘텐츠 컨트롤 검색
 다음을 사용하여 Word 문서를 로드합니다.`Document` 생성자, 문서 경로를 매개변수로 전달합니다. 그런 다음 문서에서 원하는 확인란 콘텐츠 컨트롤을 검색합니다. 이 예에서는 확인란이 문서의 첫 번째 구조화된 문서 태그라고 가정합니다.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3단계: 현재 상태에 따라 확인란을 선택하거나 선택 취소합니다.
 검색된 구조화된 문서 태그 유형이 맞는지 확인하세요.`SdtType.Checkbox` . 그렇다면`Checked` 콘텐츠 컨트롤의 속성`true` 상자를 확인합니다. 그렇지 않으면 선택하지 않은 상태로 둘 수 있습니다.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## 4단계: 문서 저장
 수정된 문서를 다음을 사용하여 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.CurrentStateOfCheckBox.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### .NET용 Aspose.Words를 사용하는 확인란의 현재 상태에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// 문서에서 첫 번째 콘텐츠 컨트롤을 가져옵니다.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 확인란 콘텐츠 컨트롤의 현재 상태를 성공적으로 검색하고 설정했습니다.