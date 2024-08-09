---
title: 핵심 글꼴을 포함하지 않음으로써 PDF 파일 크기 줄이기
linktitle: 핵심 글꼴을 포함하지 않음으로써 PDF 파일 크기 줄이기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 핵심 글꼴을 포함하지 않음으로써 PDF 파일 크기를 줄이는 방법을 알아보세요. PDF를 최적화하려면 단계별 가이드를 따르십시오.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---
## 소개

PDF 파일이 왜 그렇게 큰지 궁금해서 머리를 긁적인 적이 있습니까? 글쎄, 당신은 혼자가 아닙니다. 일반적인 원인 중 하나는 Arial 및 Times New Roman과 같은 핵심 글꼴을 포함하는 것입니다. 운 좋게도 Aspose.Words for .NET에는 이 문제를 해결할 수 있는 멋진 방법이 있습니다. 이 튜토리얼에서는 이러한 핵심 글꼴이 포함되지 않도록 하여 PDF 파일 크기를 줄이는 방법을 보여 드리겠습니다. 바로 뛰어 들어 봅시다!

## 전제 조건

이 흥미진진한 여행을 시작하기 전에 필요한 모든 것이 준비되어 있는지 확인하세요. 간단한 체크리스트는 다음과 같습니다.

-  .NET용 Aspose.Words: .NET용 Aspose.Words가 설치되어 있는지 확인하세요. 아직 없으시면 다운로드 하시면 됩니다[여기](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 개발 환경이 필요합니다.
- Word 문서: 이 튜토리얼에서는 Word 문서(예: "Rendering.docx")를 사용합니다.
- 기본 C# 지식: C#에 대한 기본적인 이해가 있으면 따라가는 데 도움이 됩니다.

자, 이제 모든 준비가 끝났으니 핵심으로 들어가 보겠습니다!

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이 단계를 통해 필요한 모든 Aspose.Words 기능에 액세스할 수 있습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1단계: 문서 디렉터리 초기화

문서 조작을 시작하기 전에 문서가 저장된 디렉토리를 지정해야 합니다. 이는 파일에 액세스하는 데 필수적입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` Word 문서가 있는 실제 경로를 사용합니다.

## 2단계: Word 문서 로드

다음으로 PDF로 변환하려는 Word 문서를 로드해야 합니다. 이 예에서는 "Rendering.docx"라는 문서를 사용하고 있습니다.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

이 코드 줄은 문서를 메모리에 로드하여 추가 처리를 준비합니다.

## 3단계: PDF 저장 옵션 구성

이제 마법의 부분이 나옵니다! 핵심 글꼴이 포함되지 않도록 PDF 저장 옵션을 구성하겠습니다. 이는 PDF 파일 크기를 줄이는 데 도움이 되는 핵심 단계입니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    UseCoreFonts = true
};
```

 환경`UseCoreFonts` 에게`true` Arial 및 Times New Roman과 같은 핵심 글꼴이 PDF에 포함되지 않도록 하여 파일 크기를 크게 줄입니다.

## 4단계: 문서를 PDF로 저장

마지막으로 구성된 저장 옵션을 사용하여 Word 문서를 PDF로 저장합니다. 이 단계에서는 핵심 글꼴을 포함하지 않고 PDF 파일을 생성합니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

그리고 거기에 있습니다! 이제 PDF 파일이 부피가 큰 핵심 글꼴 없이 지정된 디렉토리에 저장됩니다.

## 결론

.NET용 Aspose.Words를 사용하면 PDF 파일 크기를 쉽게 줄일 수 있습니다. 핵심 글꼴이 포함되지 않도록 하면 파일 크기를 크게 줄일 수 있어 문서를 더 쉽게 공유하고 저장할 수 있습니다. 이 튜토리얼이 도움이 되기를 바라며 프로세스를 명확하게 이해하는 데 도움이 되기를 바랍니다. 작은 변화가 큰 변화를 가져올 수 있다는 점을 기억하세요!

## FAQ

### PDF에 핵심 글꼴을 포함하지 말아야 하는 이유는 무엇입니까?
핵심 글꼴을 포함하지 않으면 파일 크기가 줄어들어 공유 및 저장이 더 쉬워집니다.

### 내장된 핵심 글꼴 없이도 PDF를 올바르게 볼 수 있습니까?
예, Arial 및 Times New Roman과 같은 핵심 글꼴은 일반적으로 대부분의 시스템에서 사용할 수 있습니다.

### 사용자 정의 글꼴을 포함해야 하는 경우 어떻게 해야 합니까?
 당신은`PdfSaveOptions`필요에 따라 특정 글꼴을 포함합니다.

### .NET용 Aspose.Words는 무료로 사용할 수 있나요?
 .NET용 Aspose.Words에는 라이선스가 필요합니다. 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### .NET용 Aspose.Words에 대한 추가 문서는 어디서 찾을 수 있나요?
 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/words/net/).