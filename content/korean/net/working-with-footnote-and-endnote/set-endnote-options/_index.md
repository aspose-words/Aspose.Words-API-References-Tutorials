---
title: 미주 옵션 설정
linktitle: 미주 옵션 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 미주 옵션을 설정하는 방법을 알아보세요. 예제 소스 코드가 포함된 단계별 튜토리얼입니다.
type: docs
weight: 10
url: /ko/net/working-with-footnote-and-endnote/set-endnote-options/
---

이 단계별 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 미주 옵션을 설정하는 방법을 안내합니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

 시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 설정되어 있는지 확인하세요. 아직 수행하지 않은 경우 다음에서 라이브러리를 다운로드하여 설치하십시오.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1단계: 문서 개체 초기화

 먼저, 초기화`Document` 소스 문서에 대한 경로를 제공하여 개체를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## 2단계: DocumentBuilder 개체 초기화

 다음으로 초기화`DocumentBuilder` 문서에 대한 작업을 수행하는 개체:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 텍스트 및 미주 추가하기

 사용`Write` 의 방법`DocumentBuilder` 문서에 텍스트를 추가하는 개체와`InsertFootnote` 미주 삽입 방법:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## 4단계: 미주 옵션 설정하기

 액세스`EndnoteOptions`미주 옵션을 수정하려면 문서의 속성을 사용하세요. 이 예에서는 각 페이지에서 다시 시작하도록 다시 시작 규칙과 섹션 끝 위치를 설정했습니다.

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## 5단계: 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 미주 옵션을 성공적으로 설정했습니다.

### .NET용 Aspose.Words를 사용하여 미주 옵션 설정에 대한 예제 소스 코드

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

자신의 프로젝트에서 이 코드를 자유롭게 사용하고 특정 요구 사항에 따라 수정하십시오.

### FAQ

#### Q: Aspose.Words에서 어떻게 미주의 스타일을 지정할 수 있나요?

 A: Aspose.Words에서 미주의 스타일을 지정하려면 다음을 사용할 수 있습니다.`EndnoteOptions` 수업과`SeparatorNoteTextStyle` 재산. 이 속성을 사용하여 미주의 글꼴 스타일, 크기, 색상 등을 지정할 수 있습니다.

#### Q: 문서의 미주 번호 매기기를 사용자 정의할 수 있습니까?

 A: 예, 문서의 미주 번호 매기기를 사용자 정의할 수 있습니다. 당신은 사용할 수 있습니다`RestartRule`그리고`NumberStyle` 의 속성`EndnoteOptions` 특정 재시작 규칙과 번호 매기기 스타일을 정의하는 클래스입니다.

#### Q: 문서에서 미주를 배치하려면 어떻게 해야 합니까?

A: 문서에서 미주 위치를 지정하려면`Position` 의 재산`EndnoteOptions` 수업. 미주를 각 페이지 하단, 각 섹션 끝, 문서 끝 중 어디에 배치할지 지정할 수 있습니다.

#### Q: 미주 번호 매기기 형식을 사용자 정의할 수 있나요?

 A: 예, Aspose.Words에서 미주 번호 매기기 형식을 사용자 정의할 수 있습니다. 사용`NumberFormat` 의 재산`EndnoteOptions` 아라비아 숫자, 로마 숫자, 문자 등 원하는 형식을 설정하는 클래스입니다.

#### Q: 문서의 섹션 간에 미주 번호를 계속 매길 수 있나요?

 A: 예, 문서의 섹션 간에 미주 번호를 계속 매기는 것이 가능합니다. 사용`RestartRule` 의 재산`EndnoteOptions` 클래스로 설정하고`RestartContinuous` 섹션 간에 번호 매기기를 계속할 수 있습니다.