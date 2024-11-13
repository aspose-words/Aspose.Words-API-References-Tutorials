---
title: 수출 자원
linktitle: 수출 자원
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서를 HTML로 저장하는 동안 CSS 및 글꼴과 같은 리소스를 내보내는 방법을 알아보세요. 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/export-resources/
---
## 소개

안녕하세요, 동료 기술 매니아 여러분! Word 문서를 HTML로 변환해야 하는 상황에 처한 적이 있다면, 여러분은 올바른 곳에 있습니다. 오늘은 Aspose.Words for .NET의 멋진 세계로 뛰어듭니다. 이 강력한 라이브러리를 사용하면 Word 문서를 프로그래밍 방식으로 손쉽게 작업할 수 있습니다. 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서를 HTML로 저장할 때 글꼴 및 CSS와 같은 리소스를 내보내는 단계를 살펴보겠습니다. 재미있고 유익한 여행을 위해 안전띠를 매세요!

## 필수 조건

코드로 들어가기 전에, 시작하는 데 필요한 모든 것을 갖추었는지 확인해 보겠습니다. 간단한 체크리스트는 다음과 같습니다.

1.  Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Visual Studio 웹사이트](https://visualstudio.microsoft.com/).
2.  Aspose.Words for .NET: Aspose.Words for .NET 라이브러리가 필요합니다. 아직 없다면 무료 평가판을 받으세요.[Aspose 릴리스](https://releases.aspose.com/words/net/) 또는 다음에서 구매하세요[아스포즈 스토어](https://purchase.aspose.com/buy).
3. C#에 대한 기본 지식: C#에 대한 기본적인 이해는 코드 예제를 따라가는 데 도움이 됩니다.

다 알아들었나요? 좋아요! 필요한 네임스페이스를 가져오는 것으로 넘어가죠.

## 네임스페이스 가져오기

Aspose.Words for .NET을 사용하려면 프로젝트에 관련 네임스페이스를 포함해야 합니다. 방법은 다음과 같습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

이러한 네임스페이스는 우리 튜토리얼에서 사용할 Aspose.Words 클래스와 메서드에 액세스하는 데 필수적입니다.

Word 문서를 HTML로 저장할 때 리소스를 내보내는 과정을 분석해 보겠습니다. 단계별로 설명하므로 따라하기 쉽습니다.

## 1단계: 문서 디렉토리 설정

먼저, 문서 디렉토리 경로를 지정해야 합니다. 여기가 Word 문서가 있는 곳이고 HTML 파일이 저장되는 곳입니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 디렉토리의 실제 경로를 포함합니다.

## 2단계: Word 문서 로드

 다음으로, HTML로 변환하려는 Word 문서를 로드해 보겠습니다. 이 튜토리얼에서는 다음 이름의 문서를 사용합니다.`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

이 코드 줄은 지정된 디렉토리에서 문서를 로드합니다.

## 3단계: HTML 저장 옵션 구성

CSS 및 글꼴과 같은 리소스를 내보내려면 다음을 구성해야 합니다.`HtmlSaveOptions`. 이 단계는 HTML 출력이 잘 구성되고 필요한 리소스가 포함되어 있는지 확인하는 데 중요합니다.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://example.com/리소스"
};
```

각 옵션의 기능을 살펴보겠습니다.
- `CssStyleSheetType = CssStyleSheetType.External`: 이 옵션은 CSS 스타일을 외부 스타일 시트에 저장해야 함을 지정합니다.
- `ExportFontResources = true`: 이를 통해 글꼴 리소스를 내보낼 수 있습니다.
- `ResourceFolder = dataDir + "Resources"`: 리소스(글꼴 및 CSS 파일 등)가 저장될 로컬 폴더를 지정합니다.
- `ResourceFolderAlias = "http://example.com/resources"`: HTML 파일에서 사용될 리소스 폴더의 별칭을 설정합니다.

## 4단계: 문서를 HTML로 저장

저장 옵션이 구성되면 마지막 단계는 문서를 HTML 파일로 저장하는 것입니다. 방법은 다음과 같습니다.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

이 코드 줄은 내보낸 리소스와 함께 문서를 HTML 형식으로 저장합니다.

## 결론

이제 아시죠! Aspose.Words for .NET을 사용하여 Word 문서를 HTML로 저장하면서 리소스를 성공적으로 내보냈습니다. 이 강력한 라이브러리를 사용하면 Word 문서를 프로그래밍 방식으로 처리하는 것이 아주 쉬워집니다. 웹 애플리케이션에서 작업하든 오프라인에서 사용할 수 있도록 문서를 변환해야 하든 Aspose.Words가 해결해 드립니다.

## 자주 묻는 질문

### 글꼴과 CSS와 함께 이미지를 내보낼 수 있나요?
 네, 가능합니다! Aspose.Words for .NET도 이미지 내보내기를 지원합니다. 다음 사항을 구성하세요.`HtmlSaveOptions` 따라서.

### 외부 스타일 시트를 사용하는 대신 CSS를 내장할 수 있는 방법이 있나요?
 물론입니다. 설정할 수 있습니다.`CssStyleSheetType` 에게`CssStyleSheetType.Embedded` 내장된 스타일을 선호하는 경우.

### 출력 HTML 파일의 이름을 어떻게 사용자 지정할 수 있나요?
 원하는 파일 이름을 지정할 수 있습니다.`doc.Save` 방법. 예를 들어,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### Aspose.Words는 HTML 외에 다른 포맷도 지원하나요?
 네, PDF, DOCX, TXT 등 다양한 형식을 지원합니다. 확인해 보세요.[선적 서류 비치](https://reference.aspose.com/words/net/) 전체 목록은 여기에서 확인하세요.

### 더 많은 지원과 리소스를 어디서 얻을 수 있나요?
더 많은 도움이 필요하면 다음을 방문하세요.[Aspose.Words 지원 포럼](https://forum.aspose.com/c/words/8) . 또한 자세한 설명서와 예제를 다음에서 찾을 수 있습니다.[Aspose 웹사이트](https://reference.aspose.com/words/net/).