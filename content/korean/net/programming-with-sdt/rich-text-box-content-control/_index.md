---
title: 서식 있는 텍스트 상자 콘텐츠 제어
linktitle: 서식 있는 텍스트 상자 콘텐츠 제어
second_title: Aspose.Words 문서 처리 API
description: 텍스트 서식 지정 및 스타일 지정이 가능한 .NET용 Aspose.Words를 사용하여 Word 문서에서 서식 있는 텍스트 상자 콘텐츠 컨트롤을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/rich-text-box-content-control/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 서식 있는 텍스트 상자 콘텐츠 컨트롤을 만드는 방법을 보여줍니다. 서식 있는 텍스트 상자 콘텐츠 컨트롤을 사용하면 사용자가 다양한 스타일과 서식 옵션을 사용하여 텍스트를 입력하고 서식을 지정할 수 있습니다.

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
 새 인스턴스를 생성합니다.`Document` 수업과`StructuredDocumentTag` 서식 있는 텍스트 상자 콘텐츠 컨트롤을 나타냅니다. 지정하다`SdtType.RichText` 유형과`MarkupLevel.Block` 블록 수준의 서식 있는 텍스트 상자를 만들기 위한 마크업 수준으로.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## 3단계: 서식 있는 텍스트 콘텐츠 생성 및 형식 지정
단락을 만들고 실행하여 서식 있는 텍스트 콘텐츠를 나타냅니다. 색상, 글꼴 등 텍스트 및 서식 옵션을 설정합니다.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## 4단계: 콘텐츠 컨트롤에 서식 있는 텍스트 콘텐츠 추가
서식 있는 텍스트 콘텐츠가 포함된 단락을`ChildNodes` 서식 있는 텍스트 상자 콘텐츠 컨트롤의 컬렉션입니다.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## 5단계: 문서에 콘텐츠 컨트롤 추가
 다음을 사용하여 서식 있는 텍스트 상자 콘텐츠 컨트롤을 문서 본문에 추가합니다.`AppendChild` 문서의 첫 번째 섹션 본문의 메서드입니다.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## 6단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.RichTextBoxContentControl.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### .NET용 Aspose.Words를 사용하는 서식 있는 텍스트 상자 콘텐츠 제어의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에 서식 있는 텍스트 상자 콘텐츠 컨트롤을 성공적으로 만들었습니다.