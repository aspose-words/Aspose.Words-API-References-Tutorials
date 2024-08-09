---
title: 각주 및 끝 메모 위치 설정
linktitle: 각주 및 끝 메모 위치 설정
second_title: Aspose.Words 문서 처리 API
description: 이 상세한 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 각주 및 미주 위치를 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---
## 소개

Word 문서로 작업하고 각주와 미주를 효과적으로 관리해야 하는 경우 Aspose.Words for .NET이 가장 적합한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 각주 및 미주 위치를 설정하는 과정을 안내합니다. 쉽게 따라하고 구현할 수 있도록 각 단계를 세분화하겠습니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 사항을 확인하세요.

-  .NET 라이브러리용 Aspose.Words: 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
- Visual Studio: 모든 최신 버전이 정상적으로 작동합니다.
- C#에 대한 기본 지식: 기본 사항을 이해하면 쉽게 따라하는 데 도움이 됩니다.

## 네임스페이스 가져오기

먼저 C# 프로젝트에서 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using Aspose.Words;
```

## 1단계: Word 문서 로드

시작하려면 Word 문서를 Aspose.Words Document 개체에 로드해야 합니다. 이를 통해 문서의 내용을 조작할 수 있습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 이 코드에서는`"YOUR DOCUMENT DIRECTORY"`문서가 있는 실제 경로를 사용합니다.

## 2단계: 각주 위치 설정

다음으로 각주의 위치를 설정합니다. Aspose.Words for .NET을 사용하면 페이지 하단이나 텍스트 아래에 각주를 배치할 수 있습니다.

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
```

 여기서는 텍스트 아래에 각주가 표시되도록 설정했습니다. 페이지 하단에서 원하는 경우 다음을 사용하세요.`FootnotePosition.BottomOfPage`.

## 3단계: 미주 위치 설정

마찬가지로 미주의 위치도 설정할 수 있습니다. 미주는 섹션 끝이나 문서 끝에 배치할 수 있습니다.

```csharp
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

 이 예에서는 각 섹션의 끝에 미주가 배치됩니다. 문서 끝에 배치하려면 다음을 사용하십시오.`EndnotePosition.EndOfDocument`.

## 4단계: 문서 저장

마지막으로 문서를 저장하여 변경 사항을 적용합니다. 출력 문서에 대한 올바른 파일 경로와 이름을 지정했는지 확인하십시오.

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

이 줄은 수정된 문서를 지정된 디렉터리에 저장합니다.

## 결론

Aspose.Words for .NET을 사용하여 Word 문서에서 각주 및 미주 위치를 설정하는 것은 단계를 알고 나면 간단합니다. 이 가이드를 따르면 필요에 맞게 문서를 사용자 정의하여 각주와 미주가 원하는 위치에 정확하게 배치되도록 할 수 있습니다.

## FAQ

### 개별 각주나 미주의 위치를 다르게 설정할 수 있나요?

아니요, Aspose.Words for .NET은 문서의 모든 각주와 미주의 위치를 균일하게 설정합니다.

### Aspose.Words for .NET은 모든 버전의 Word 문서와 호환됩니까?

예, .NET용 Aspose.Words는 DOC, DOCX, RTF 등을 포함한 광범위한 Word 문서 형식을 지원합니다.

### 다른 프로그래밍 언어와 함께 .NET용 Aspose.Words를 사용할 수 있나요?

Aspose.Words for .NET은 .NET 애플리케이션용으로 설계되었지만 C#, VB.NET 등과 같은 .NET 지원 언어와 함께 사용할 수 있습니다.

### .NET용 Aspose.Words에 대한 무료 평가판이 있습니까?

 예, 무료 평가판을 받을 수 있습니다[여기](https://releases.aspose.com/).

### .NET용 Aspose.Words에 대한 자세한 문서는 어디서 찾을 수 있나요?

 자세한 문서가 제공됩니다.[여기](https://reference.aspose.com/words/net/).