---
title: 포함된 글꼴을 비활성화하여 PDF 크기 줄이기
linktitle: 포함된 글꼴을 비활성화하여 PDF 크기 줄이기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 포함된 글꼴을 비활성화하여 PDF 크기를 줄입니다. 효율적인 저장 및 공유를 위해 문서를 최적화하려면 단계별 가이드를 따르십시오.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---
## 소개

효율적인 저장과 빠른 공유를 위해서는 PDF 파일의 크기를 줄이는 것이 중요할 수 있습니다. 이를 수행하는 효과적인 방법 중 하나는 특히 대부분의 시스템에서 표준 글꼴을 이미 사용할 수 있는 경우 포함된 글꼴을 비활성화하는 것입니다. 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 포함된 글꼴을 비활성화하여 PDF 크기를 줄이는 방법을 살펴보겠습니다. 여러분의 프로젝트에서 이를 쉽게 구현할 수 있도록 각 단계를 살펴보겠습니다.

## 전제 조건

코드를 살펴보기 전에 다음 사항을 확인하세요.

-  .NET용 Aspose.Words: 아직 설치하지 않았다면 다음 사이트에서 다운로드하여 설치하세요.[다운로드 링크](https://releases.aspose.com/words/net/).
- .NET 개발 환경: Visual Studio가 널리 사용됩니다.
- 샘플 Word 문서: PDF로 변환할 DOCX 파일을 준비하세요.

## 네임스페이스 가져오기

시작하려면 필요한 네임스페이스를 프로젝트로 가져왔는지 확인하세요. 이를 통해 작업에 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

프로세스를 간단하고 관리 가능한 단계로 나누어 보겠습니다. 각 단계는 작업을 안내하여 모든 지점에서 무슨 일이 일어나고 있는지 이해할 수 있도록 해줍니다.

## 1단계: 문서 초기화

먼저 PDF로 변환하려는 Word 문서를 로드해야 합니다. 이것이 당신의 여행이 시작되는 곳입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 여기,`dataDir` 문서가 있는 디렉토리에 대한 자리 표시자입니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 실제 경로와 함께.

## 2단계: PDF 저장 옵션 구성

다음으로 PDF 저장 옵션을 설정하겠습니다. 여기에서 표준 Windows 글꼴을 포함하지 않도록 지정합니다.

```csharp
// 출력 PDF는 표준 Windows 글꼴을 포함하지 않고 저장됩니다.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone
};
```

 설정으로`FontEmbeddingMode` 에게`EmbedNone`, Aspose.Words에 이러한 글꼴을 PDF에 포함하지 않도록 지시하여 파일 크기를 줄입니다.

## 3단계: 문서를 PDF로 저장

마지막으로 구성된 저장 옵션을 사용하여 문서를 PDF로 저장합니다. DOCX가 컴팩트한 PDF로 변환되는 진실의 순간입니다.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 실제 디렉토리 경로를 다시 한 번 사용하십시오. 이제 출력 PDF가 내장된 표준 글꼴 없이 지정된 디렉토리에 저장됩니다.

## 결론

다음 단계를 따르면 PDF 파일의 크기를 크게 줄일 수 있습니다. 포함된 글꼴을 비활성화하는 것은 문서를 더 가볍고 공유하기 쉽게 만드는 간단하면서도 효과적인 방법입니다. Aspose.Words for .NET은 이 프로세스를 원활하게 만들어 최소한의 노력으로 파일을 최적화할 수 있도록 해줍니다.

## FAQ

### PDF에 포함된 글꼴을 비활성화해야 하는 이유는 무엇입니까?
포함된 글꼴을 비활성화하면 PDF 파일 크기가 크게 줄어들어 저장 효율성이 향상되고 공유 속도가 빨라집니다.

### PDF가 포함된 글꼴 없이도 올바르게 표시됩니까?
예, 글꼴이 표준이고 PDF를 보는 시스템에서 사용할 수 있다면 올바르게 표시됩니다.

### PDF에 특정 글꼴만 선택적으로 포함할 수 있습니까?
예, .NET용 Aspose.Words를 사용하면 포함된 글꼴을 사용자 정의할 수 있으므로 파일 크기를 줄이는 방법에 유연성을 제공합니다.

### PDF에 포함된 글꼴을 비활성화하려면 .NET용 Aspose.Words가 필요합니까?
예, Aspose.Words for .NET은 PDF에 글꼴 포함 옵션을 구성하는 데 필요한 기능을 제공합니다.

### 문제가 발생하면 어떻게 지원을 받을 수 있나요?
 당신은 방문 할 수 있습니다[지원 포럼](https://forum.aspose.com/c/words/8) 발생한 문제에 대한 도움을 받으려면
