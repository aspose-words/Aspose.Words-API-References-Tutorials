---
title: PDF 문서에 하위 집합 글꼴 포함
linktitle: PDF 문서에 하위 집합 글꼴 포함
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 필요한 글꼴 하위 집합만 포함하여 PDF 파일 크기를 줄입니다. PDF를 효율적으로 최적화하려면 단계별 가이드를 따르십시오.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---
## 소개

유사한 내용을 포함하고 있음에도 불구하고 일부 PDF 파일이 다른 파일보다 훨씬 큰 것을 본 적이 있습니까? 범인은 종종 글꼴에 있습니다. PDF에 글꼴을 포함하면 모든 장치에서 동일하게 보이지만 파일 크기가 커질 수도 있습니다. 다행히 Aspose.Words for .NET은 필요한 글꼴 하위 집합만 포함하여 PDF를 간결하고 효율적으로 유지하는 편리한 기능을 제공합니다. 이 튜토리얼에서는 프로세스를 단계별로 안내합니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

-  .NET용 Aspose.Words: 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
- .NET 환경: 작동 중인 .NET 개발 환경이 있는지 확인하세요.
- C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 따라가는 데 도움이 됩니다.

## 네임스페이스 가져오기

.NET용 Aspose.Words를 사용하려면 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. C# 파일 상단에 다음을 추가하세요.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1단계: 문서 로드

 먼저 PDF로 변환하려는 Word 문서를 로드해야 합니다. 이 작업은 다음을 사용하여 수행됩니다.`Document` Aspose.Words에서 제공하는 클래스입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 이 코드 조각은 다음 위치에 있는 문서를 로드합니다.`dataDir` . 꼭 교체하세요`"YOUR DOCUMENT DIRECTORY"` 문서의 실제 경로와 함께.

## 2단계: PDF 저장 옵션 구성

 다음으로`PdfSaveOptions` 필요한 글꼴 하위 집합만 포함되도록 합니다. 설정으로`EmbedFullFonts` 에게`false`, Aspose.Words에 문서에 사용된 문자만 삽입하도록 지시합니다.

```csharp
// 출력 PDF에는 문서에 있는 글꼴의 하위 집합이 포함됩니다.
// 문서에 사용된 글리프만 PDF 글꼴에 포함됩니다.
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

이 작지만 중요한 단계는 PDF 파일 크기를 크게 줄이는 데 도움이 됩니다.

## 3단계: 문서를 PDF로 저장

 마지막으로 다음을 사용하여 문서를 PDF로 저장합니다.`Save` 메서드, 구성된 적용`PdfSaveOptions`.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf", saveOptions);
```

 이 코드는 다음 이름의 PDF 파일을 생성합니다.`WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf` 필요한 글꼴 하위 집합만 포함된 지정된 디렉터리에 있습니다.

## 결론

그리고 거기에 있습니다! 이러한 간단한 단계를 따르면 Aspose.Words for .NET을 사용하여 필요한 글꼴 하위 집합만 포함하여 PDF 파일의 크기를 효율적으로 줄일 수 있습니다. 이는 저장 공간을 절약할 뿐만 아니라 특히 광범위한 글꼴이 포함된 문서의 경우 더 빠른 로드 시간과 더 나은 성능을 보장합니다.

## FAQ

### PDF에 글꼴 하위 집합만 포함해야 하는 이유는 무엇입니까?
필요한 글꼴 하위 집합만 포함하면 문서의 모양과 가독성을 저하시키지 않고 PDF 파일 크기를 크게 줄일 수 있습니다.

### 필요한 경우 전체 글꼴 포함으로 되돌릴 수 있나요?
 그래 넌 할수있어. 간단히 설정`EmbedFullFonts`재산`true` 에서`PdfSaveOptions`.

### .NET용 Aspose.Words는 다른 PDF 최적화 기능을 지원합니까?
전적으로! Aspose.Words for .NET은 이미지 압축, 사용하지 않는 개체 제거 등 PDF 최적화를 위한 다양한 옵션을 제공합니다.

### .NET용 Aspose.Words를 사용하여 어떤 유형의 글꼴을 하위 집합으로 포함할 수 있습니까?
Aspose.Words for .NET은 문서에 사용된 모든 트루타입 글꼴에 대한 하위 집합 포함을 지원합니다.

### 내 PDF에 어떤 글꼴이 포함되어 있는지 어떻게 확인할 수 있나요?
Adobe Acrobat Reader에서 PDF를 열고 글꼴 탭 아래의 속성을 확인하여 포함된 글꼴을 확인할 수 있습니다.
