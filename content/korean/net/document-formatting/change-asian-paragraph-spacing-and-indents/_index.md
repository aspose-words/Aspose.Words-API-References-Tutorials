---
title: Word 문서에서 아시아 단락 간격 및 들여쓰기 변경
linktitle: Word 문서에서 아시아 단락 간격 및 들여쓰기 변경
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 아시아 단락 간격과 들여쓰기를 변경하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 아시아 단락의 간격과 들여쓰기를 변경하는 방법을 안내합니다. 소스 코드를 이해하고 변경 사항을 적용하려면 아래 단계를 따르세요.

## 1단계: 문서 로드

시작하려면 문서의 디렉터리를 지정하고 아시아 타이포그래피가 포함된 문서를 Document 객체에 로드하세요. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 2단계: 단락 간격 및 들여쓰기 변경

이제 아시아 문서의 첫 번째 단락의 간격과 들여쓰기를 수정하겠습니다. 방법은 다음과 같습니다.

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // ParagraphFormat.LeftIndent 업데이트
format.CharacterUnitRightIndent = 10; // ParagraphFormat.RightIndent 업데이트
format.CharacterUnitFirstLineIndent = 20; //ParagraphFormat.FirstLineIndent 업데이트
format.LineUnitBefore = 5; // ParagraphFormat.SpaceBefore 업데이트
format.LineUnitAfter = 10; // ParagraphFormat.SpaceAfter 업데이트
```

## 3단계: 문서 저장

 텍스트 입력 양식 필드를 삽입한 후,`Save` 방법. 적절한 파일 경로를 제공해야 합니다.

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### .NET용 Aspose.Words를 사용하여 아시아 단락 간격 및 들여쓰기 변경에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용한 아시아 단락 간격 및 들여쓰기 편집 기능의 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent가 업데이트됩니다.
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent가 업데이트됩니다.
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent가 업데이트됩니다.
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore가 업데이트됩니다.
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter가 업데이트됩니다.

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

이 코드를 사용하면 .NET용 Aspose.Words를 사용하여 아시아 단락의 간격과 들여쓰기를 변경할 수 있습니다.

## 결론

 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 아시아 단락의 간격과 들여쓰기를 변경하는 방법을 배웠습니다. 관련 속성을 수정하여`ParagraphFormat`Word 문서에서 아시아 단락의 레이아웃과 모양을 제어할 수 있습니다. 이 기능은 아시아 문자가 포함된 텍스트 서식을 사용자 정의하고 언어 내용이 혼합된 문서에서 원하는 시각적 표현을 얻는 데 유용합니다.

### FAQ

#### Q: Aspose.Words for .NET의 "아시아 단락 간격 및 들여쓰기 변경" 기능은 무엇을 합니까?

A: Aspose.Words for .NET의 "아시아 단락 간격 및 들여쓰기 변경" 기능을 사용하면 Word 문서에서 아시아 단락의 간격 및 들여쓰기 속성을 수정할 수 있습니다. 왼쪽 및 오른쪽 들여쓰기, 첫 줄 들여쓰기, 앞 공백, 뒤 공백 값을 조정하여 단락의 레이아웃과 모양을 제어할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 아시아 단락의 간격과 들여쓰기를 어떻게 변경합니까?

 A: 아시아 단락의 간격과 들여쓰기를 변경하려면`ParagraphFormat`대상 단락의 관련 속성을 수정합니다. 제공된 예제 코드에서는 문서의 첫 번째 단락에 액세스하고`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , 그리고`LineUnitAfter` 간격과 들여쓰기를 조정하는 속성입니다.

#### Q: 이러한 변경 사항을 문서의 다른 단락에 적용할 수 있습니까?

 A: 예, 해당 변경 사항에 액세스하여 문서의 다른 단락에 이러한 변경 사항을 적용할 수 있습니다.`ParagraphFormat` 사물. 예제 코드는 문서의 첫 번째 단락을 대상으로 하지만`Paragraphs` 수집하거나 다른 기준을 사용하여 원하는 단락을 선택합니다.