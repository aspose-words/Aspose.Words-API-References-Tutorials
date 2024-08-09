---
title: 내장된 Arial 및 Times Roman 글꼴 건너뛰기로 PDF 크기 최적화
linktitle: 내장된 Arial 및 Times Roman 글꼴 건너뛰기로 PDF 크기 최적화
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 내장된 Arial 및 Times Roman 글꼴을 건너뛰어 PDF 크기를 최적화하세요. PDF 파일을 간소화하려면 이 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---
## 소개

PDF 파일 크기가 너무 큰 상황에 처한 적이 있습니까? 그것은 휴가를 위해 짐을 꾸렸는데 여행가방이 터지는 것을 깨닫는 것과 같습니다. 살을 좀 빼야 한다는 걸 알지만, 무엇을 버릴 수 있나요? PDF 파일, 특히 Word 문서에서 변환된 파일로 작업할 때 포함된 글꼴로 인해 파일 크기가 커질 수 있습니다. 고맙게도 Aspose.Words for .NET은 PDF를 간결하고 의미있게 유지하는 세련된 솔루션을 제공합니다. 이 튜토리얼에서는 내장된 Arial 및 Times Roman 글꼴을 건너뛰어 PDF 크기를 최적화하는 방법을 살펴보겠습니다. 시작해 봅시다!

## 전제 조건

핵심적인 내용으로 넘어가기 전에 필요한 몇 가지 사항이 있습니다.
-  .NET용 Aspose.Words: 이 강력한 라이브러리가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
- C#에 대한 기본 이해: 코드 조각을 따라가는 데 도움이 됩니다.
- Word 문서: 프로세스를 보여주기 위해 샘플 문서를 사용하겠습니다. 

## 네임스페이스 가져오기

가장 먼저 필요한 네임스페이스를 가져왔는지 확인하세요. 이는 Aspose.Words 기능에 액세스하기 위한 단계를 설정합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

이제 프로세스를 단계별로 분석해 보겠습니다.

## 1단계: 환경 설정

시작하려면 개발 환경을 설정해야 합니다. 자주 사용하는 C# IDE(예: Visual Studio)를 열고 새 프로젝트를 만듭니다.

## 2단계: Word 문서 로드

다음 단계는 PDF로 변환하려는 Word 문서를 로드하는 것입니다. 문서가 올바른 디렉토리에 있는지 확인하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 이 스니펫에서는`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리 경로와 함께.

## 3단계: PDF 저장 옵션 구성

이제 글꼴이 포함되는 방식을 제어하려면 PDF 저장 옵션을 구성해야 합니다. 기본적으로 모든 글꼴이 포함되어 있으므로 파일 크기가 커질 수 있습니다. 이 설정을 변경하겠습니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll
};
```

## 4단계: 문서를 PDF로 저장

마지막으로 지정된 저장 옵션을 사용하여 문서를 PDF로 저장합니다. 이것이 바로 마법이 일어나는 곳입니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

이 명령은 문서를 지정된 디렉토리에 "OptimizedPDF.pdf"라는 이름의 PDF로 저장합니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Arial 및 Times Roman 글꼴 포함을 건너뛰고 PDF 파일 크기를 최적화하는 방법을 배웠습니다. 이 간단한 조정을 통해 파일 크기를 크게 줄여 공유 및 저장이 더 쉬워질 수 있습니다. 이는 모든 필수 요소를 그대로 유지하면서 불필요한 무게를 줄여 PDF를 보기 위해 체육관에 가는 것과 같습니다.

## FAQ

### Arial 및 Times Roman 글꼴 포함을 건너뛰어야 하는 이유는 무엇입니까?
대부분의 시스템에 이미 이러한 글꼴이 설치되어 있으므로 이러한 일반 글꼴을 건너뛰면 PDF 파일 크기가 줄어들 수 있습니다.

### 이것이 내 PDF의 모양에 영향을 줍니까?
아니요, 그렇지 않습니다. Arial 및 Times Roman은 표준 글꼴이므로 모양은 다른 시스템에서도 일관되게 유지됩니다.

### 다른 글꼴 삽입도 건너뛸 수 있나요?
예, 필요한 경우 다른 글꼴 포함을 건너뛰도록 저장 옵션을 구성할 수 있습니다.

### .NET용 Aspose.Words는 무료인가요?
Aspose.Words for .NET은 다운로드할 수 있는 무료 평가판을 제공합니다.[여기](https://releases.aspose.com/) , 그러나 전체 액세스를 위해서는 라이센스를 구입해야 합니다.[여기](https://purchase.aspose.com/buy).

### .NET용 Aspose.Words에 대한 추가 튜토리얼은 어디서 찾을 수 있나요?
 포괄적인 문서와 튜토리얼을 찾을 수 있습니다.[여기](https://reference.aspose.com/words/net/).