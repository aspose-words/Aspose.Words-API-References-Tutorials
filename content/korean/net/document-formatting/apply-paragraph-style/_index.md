---
title: Word 문서에 단락 스타일 적용
linktitle: Word 문서에 단락 스타일 적용
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에 단락 스타일을 적용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-formatting/apply-paragraph-style/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 단락 스타일을 적용하는 방법을 안내합니다. 소스 코드를 이해하고 단락 스타일을 적용하려면 아래 단계를 따르세요.

## 1단계: 문서 만들기 및 구성

시작하려면 새 문서와 관련 DocumentBuilder 개체를 만듭니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 단락 스타일 구성

이제 내장된 스타일 식별자를 사용하여 단락 스타일을 구성하겠습니다. 방법은 다음과 같습니다.

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## 3단계: 콘텐츠 추가

단락에 내용을 추가해 보겠습니다. 방법은 다음과 같습니다.

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### .NET용 Aspose.Words를 사용하여 단락 스타일 적용에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 단락 스타일 적용 기능에 대한 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

이 코드를 사용하면 .NET용 Aspose.Words를 사용하여 단락 스타일을 적용할 수 있습니다.

## 결론

 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 단락 스타일을 적용하는 방법을 살펴보았습니다. 설정하여`StyleIdentifier` 의 재산`ParagraphFormat`, 단락에 내장된 스타일을 적용할 수 있었습니다. Aspose.Words for .NET은 사용자 정의 스타일을 생성하고 적용하는 기능을 포함하여 광범위한 서식 옵션을 제공하므로 전문가 수준의 문서를 쉽게 만들 수 있습니다.

### FAQ

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에 단락 스타일을 어떻게 적용합니까?

A: .NET용 Aspose.Words를 사용하여 Word 문서에 단락 스타일을 적용하려면 다음 단계를 따르세요.
1.  새 문서를 만들고`DocumentBuilder` 물체.
2.  다음을 설정하여 단락 스타일을 구성합니다.`StyleIdentifier` 의 재산`ParagraphFormat` 원하는 스타일 식별자(예:`StyleIdentifier.Title`, `StyleIdentifier.Heading1`, 등.).
3.  다음을 사용하여 단락에 내용을 추가합니다.`Write` 의 방법`DocumentBuilder`.
4.  다음을 사용하여 문서를 저장합니다.`Save` 방법.

#### Q: .NET용 Aspose.Words의 스타일 식별자는 무엇입니까?

 A: Aspose.Words for .NET의 스타일 식별자는 내장된 단락 스타일을 나타내는 미리 정의된 상수입니다. 각 스타일 식별자는 "제목", "제목1", "제목2" 등과 같은 특정 스타일에 해당합니다.`StyleIdentifier` 의 재산`ParagraphFormat`, 해당 스타일을 단락에 적용할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 사용자 정의 단락 스타일을 만들고 적용할 수 있습니까?

A: 예, .NET용 Aspose.Words를 사용하면 사용자 정의 단락 스타일을 만들고 적용할 수 있습니다. 글꼴, 정렬, 들여쓰기 등과 같은 특정 서식 속성을 사용하여 자신만의 스타일을 정의하고 이를 문서의 단락에 적용할 수 있습니다. 이를 통해 문서 전체에서 일관되고 사용자 정의된 서식을 얻을 수 있습니다.