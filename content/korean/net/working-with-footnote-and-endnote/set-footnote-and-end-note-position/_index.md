---
title: 각주 및 끝 메모 위치 설정
linktitle: 각주 및 끝 메모 위치 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 각주 및 미주의 위치를 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

이 단계별 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 각주와 미주의 위치를 설정하는 방법을 안내합니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

 시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 설정되어 있는지 확인하세요. 아직 수행하지 않은 경우 다음에서 라이브러리를 다운로드하여 설치하십시오.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1단계: 문서 개체 초기화

 먼저, 초기화`Document` 소스 문서에 대한 경로를 제공하여 개체를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## 2단계: 각주 및 미주 위치 설정

 다음으로`FootnoteOptions`그리고`EndnoteOptions`각주와 미주의 위치를 설정하려면 문서의 속성을 사용하세요. 이 예에서는 각주 위치를 텍스트 아래로 설정하고 미주의 위치를 섹션 끝으로 설정합니다.

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## 3단계: 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

그게 다야! Aspose.Words for .NET을 사용하여 Word 문서에서 각주와 미주의 위치를 성공적으로 설정했습니다.

### .NET용 Aspose.Words를 사용하여 각주 및 미주 위치 설정에 대한 예제 소스 코드

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

자신의 프로젝트에서 이 코드를 자유롭게 사용하고 특정 요구 사항에 따라 수정하십시오.

### FAQ

#### Q: Aspose.Words에서 각주와 미주의 위치를 어떻게 지정할 수 있나요?

 A: Aspose.Words에서 각주와 미주의 위치를 지정하려면`FootnoteOptions` 수업과`Position` 재산. 이 속성을 다음과 같이 원하는 값으로 설정할 수 있습니다.`BottomOfPage` (페이지 하단) 또는`EndOfSection` (섹션 끝 부분).

#### Q: 문서의 각 페이지나 섹션에 대한 각주와 미주의 위치를 사용자 정의할 수 있나요?

A: 예, 문서의 각 페이지나 섹션에 대한 각주 및 미주의 위치를 사용자 정의할 수 있습니다. Aspose.Words 섹션 및 페이지 조작 방법을 사용하여 각주와 미주의 특정 위치를 정의할 수 있습니다.

#### Q: 문서에서 각주나 미주를 제거하려면 어떻게 해야 합니까?

 A: Aspose.Words의 문서에서 각주나 미주를 제거하려면 다음과 같은 적절한 방법을 사용할 수 있습니다.`RemoveAllFootnotes` 모든 각주를 제거하거나`RemoveAllEndnotes` 모든 미주를 제거하려면 이러한 작업을 수행한 후에는 문서를 저장하십시오.

#### 질문: 각주와 미주를 페이지 여백 바깥쪽에 배치할 수 있나요?

아니요, 기본적으로 각주와 미주는 Aspose.Words의 페이지 여백 외부에 위치할 수 없습니다. 그러나 필요한 경우 각주와 미주에 더 많은 공간을 허용하도록 문서 여백을 조정할 수 있습니다.

#### Q: 각주와 미주를 특정 글꼴이나 서식 스타일로 사용자 정의할 수 있습니까?

A: 예, Aspose.Words에서 특정 글꼴이나 서식 스타일로 각주와 미주를 사용자 정의할 수 있습니다. 사용 가능한 메서드와 속성을 사용하여 글꼴 스타일, 색상, 글꼴 크기 등을 각주와 미주에 적용할 수 있습니다.