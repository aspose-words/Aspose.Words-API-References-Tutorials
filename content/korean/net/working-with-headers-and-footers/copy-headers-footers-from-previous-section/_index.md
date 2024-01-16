---
title: 이전 섹션에서 머리글 바닥글 복사
linktitle: 이전 섹션에서 머리글 바닥글 복사
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 이전 섹션에서 머리글과 바닥글을 복사하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

이 단계별 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 이전 섹션의 머리글과 바닥글을 복사하는 방법을 안내합니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

 시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 설정되어 있는지 확인하세요. 아직 수행하지 않은 경우 다음에서 라이브러리를 다운로드하여 설치하십시오.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1단계: 이전 섹션에 액세스하기

 먼저 다음 섹션에 액세스하여 이전 섹션을 검색합니다.`PreviousSibling` 현재 섹션의 속성:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## 2단계: 이전 섹션 확인

다음으로 이전 섹션이 있는지 확인하세요. 이전 섹션이 없으면 간단히 다음을 반환합니다.

```csharp
if (previousSection == null)
    return;
```

## 3단계: 머리글과 바닥글 지우기 및 복사하기

이전 섹션의 머리글과 바닥글을 현재 섹션으로 복사하려면 현재 섹션의 기존 머리글과 바닥글을 지운 다음 이전 섹션의 머리글과 바닥글을 반복하여 현재 섹션에 복제된 복사본을 추가합니다.

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## 4단계: 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
doc.Save("OutputDocument.docx");
```

그게 다야! Aspose.Words for .NET을 사용하여 Word 문서의 이전 섹션에서 현재 섹션으로 머리글과 바닥글을 성공적으로 복사했습니다.

### .NET용 Aspose.Words를 사용하여 이전 섹션의 머리글 바닥글 복사에 대한 예제 소스 코드

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

자신의 프로젝트에서 이 코드를 자유롭게 사용하고 특정 요구 사항에 따라 수정하십시오.

### FAQ

#### Q: 이전 섹션의 머리글과 바닥글을 Aspose.Words에 어떻게 복사할 수 있나요?

 A: 이전 섹션의 머리글과 바닥글을 Aspose.Words에 복사하려면 다음을 사용할 수 있습니다.`CopyHeadersFootersFromPreviousSection()` 현재의 방법`Section`물체. 이전 섹션의 머리글과 바닥글이 현재 섹션으로 복사됩니다.

#### Q: Aspose.Words의 이전 섹션에서 머리글이나 바닥글만 복사할 수 있나요?

 A: 네, Aspose.Words의 이전 섹션에서 머리글이나 바닥글만 복사하는 것이 가능합니다. 이를 위해 다음을 사용할 수 있습니다.`CopyHeaderFromPreviousSection()` 그리고`CopyFooterFromPreviousSection()` 현재의 방법`Section` 이전 섹션의 머리글이나 바닥글을 현재 섹션으로 구체적으로 복사하려면 개체를 사용하세요.

#### Q: 이전 섹션의 머리글과 바닥글을 복사하면 현재 섹션의 기존 머리글과 바닥글이 바뀌나요?

A: 예, 이전 섹션의 머리글과 바닥글을 복사하면 현재 섹션의 기존 머리글과 바닥글이 대체됩니다. 기존 머리글과 바닥글을 유지하고 복사된 머리글과 바닥글에 추가하려면 내용을 병합하는 추가 작업이 필요합니다.

#### Q: Aspose.Words의 이전 섹션에 있는 머리글이나 바닥글이 섹션에 있는지 어떻게 확인할 수 있나요?

A: 섹션에 Aspose.Words의 이전 섹션에 있는 머리글이나 바닥글이 있는지 확인하려면 다음을 사용할 수 있습니다.`HasHeader` 그리고`HasFooter` 의 속성`Section` 머리글 머리글이나 바닥글이 있는지 확인하는 개체입니다. 만약에`HasHeader` 또는`HasFooter` 보고`false`, 이는 이 섹션의 이전 섹션에 있는 머리글이나 바닥글이 없음을 의미합니다.