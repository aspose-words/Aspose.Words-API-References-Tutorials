---
title: Word 문서의 단락 서식 지정
linktitle: Word 문서의 단락 서식 지정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 단락에 사용자 정의 서식을 적용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-formatting/paragraph-formatting/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서 기능에서 단락 서식을 사용하는 방법을 안내합니다. 소스 코드를 이해하고 변경 사항을 적용하려면 아래 단계를 따르세요.

## 1단계: 문서 만들기 및 구성

시작하려면 새 문서와 관련 DocumentBuilder 개체를 만듭니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 단락 서식 지정

이제 DocumentBuilder 개체의 ParagraphFormat 개체에서 사용할 수 있는 속성을 사용하여 단락에 서식을 적용하겠습니다. 방법은 다음과 같습니다.

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat. LeftIndent = 50;
paragraphFormat. RightIndent = 50;
paragraphFormat. SpaceAfter = 25;
```

## 3단계: 문서 저장

 텍스트 입력 양식 필드를 삽입한 후,`Save` 방법. 적절한 파일 경로를 제공해야 합니다.

```csharp
builder.Writeln(
	"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
builder.Writeln(
	"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
```

### .NET용 Aspose.Words를 사용한 단락 서식 지정을 위한 예제 소스 코드

다음은 .NET용 Aspose.Words의 단락 서식 지정 기능에 대한 전체 소스 코드입니다.


```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat.LeftIndent = 50;
paragraphFormat.RightIndent = 50;
paragraphFormat.SpaceAfter = 25;

builder.Writeln(
	"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
builder.Writeln(
	"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");

```

이 코드를 사용하면 .NET용 Aspose.Words를 사용하여 단락에 다양한 서식을 적용할 수 있습니다.


## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 단락 서식 지정 기능을 사용하는 프로세스를 살펴보았습니다. 설명된 단계를 따르면 단락의 서식을 효과적으로 지정하고 정렬, 들여쓰기 및 간격을 조정하여 시각적으로 매력적이고 잘 구성된 문서를 만들 수 있습니다.

### 자주 묻는 질문

#### Q: Word 문서의 단락 서식이란 무엇입니까?

A: 단락 서식은 Word 문서의 개별 단락을 시각적으로 사용자 정의하는 것을 의미합니다. 콘텐츠의 모양과 가독성을 향상시키기 위해 정렬, 들여쓰기, 줄 간격 및 기타 스타일 요소에 대한 조정이 포함됩니다.

#### Q: 동일한 문서의 다양한 단락에 서로 다른 서식을 적용할 수 있나요?

 A: 예, 동일한 문서 내의 다양한 단락에 서로 다른 서식을 적용할 수 있습니다. 을 사용하여`ParagraphFormat` 개체를 선택하고 해당 속성을 조정하면 각 단락의 모양을 독립적으로 사용자 정의할 수 있습니다.

#### Q: .NET용 Aspose.Words는 다른 텍스트 서식 옵션을 지원합니까?

A: 예, Aspose.Words for .NET은 텍스트 서식에 대한 광범위한 지원을 제공합니다. 여기에는 글꼴 스타일, 크기, 색상 및 기타 다양한 텍스트 속성을 수정하는 기능이 포함되어 있습니다. 프로그래밍 방식으로 Word 문서의 텍스트 시각적 표현을 향상시킬 수 있습니다.

#### Q: Aspose.Words for .NET은 다른 문서 형식과 호환됩니까?

A: 예, .NET용 Aspose.Words는 DOCX, DOC, RTF, HTML 등을 포함한 다양한 문서 형식을 지원합니다. 다양한 문서 유형으로 작업할 수 있는 강력한 API를 제공하므로 문서를 효율적으로 변환, 조작 및 생성할 수 있습니다.