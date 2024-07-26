---
title: 자원 수출
linktitle: 자원 수출
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서를 HTML로 저장하면서 CSS 및 글꼴과 같은 리소스를 내보내는 방법을 알아보세요. 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/export-resources/
---
## 소개

안녕하세요, 기술 애호가 여러분! Word 문서를 HTML로 변환해야 하는 경우, 잘 찾아오셨습니다. 오늘 우리는 .NET용 Aspose.Words의 놀라운 세계로 뛰어들고 있습니다. 이 강력한 라이브러리를 사용하면 프로그래밍 방식으로 Word 문서 작업을 쉽게 수행할 수 있습니다. 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서를 HTML로 저장할 때 글꼴 및 CSS와 같은 리소스를 내보내는 단계를 안내합니다. 재미있고 유익한 라이딩을 위해 버클을 채우세요!

## 전제조건

코드를 살펴보기 전에 시작하는 데 필요한 모든 것이 갖추어져 있는지 확인하겠습니다. 간단한 체크리스트는 다음과 같습니다.

1.  Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[비주얼 스튜디오 웹사이트](https://visualstudio.microsoft.com/).
2.  .NET용 Aspose.Words: .NET용 Aspose.Words 라이브러리가 필요합니다. 아직 받지 못했다면 다음에서 무료 평가판을 받으세요.[Aspose 릴리스](https://releases.aspose.com/words/net/) 아니면 에서 구매하세요[Aspose 스토어](https://purchase.aspose.com/buy).
3. C#에 대한 기본 지식: C#에 대한 기본적인 이해는 코드 예제를 따라가는 데 도움이 됩니다.

다 알아냈어? 엄청난! 필요한 네임스페이스를 가져오는 작업으로 넘어가겠습니다.

## 네임스페이스 가져오기

.NET용 Aspose.Words를 사용하려면 프로젝트에 관련 네임스페이스를 포함해야 합니다. 방법은 다음과 같습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

이러한 네임스페이스는 튜토리얼에서 사용할 Aspose.Words 클래스와 메서드에 액세스하는 데 중요합니다.

Word 문서를 HTML로 저장할 때 리소스를 내보내는 프로세스를 분석해 보겠습니다. 차근차근 따라해 보도록 하겠습니다. 따라하기 쉽습니다.

## 1단계: 문서 디렉토리 설정

먼저, 문서 디렉토리의 경로를 지정해야 합니다. 여기에는 Word 문서가 있고 HTML 파일이 저장되는 위치입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 디렉터리의 실제 경로를 사용합니다.

## 2단계: Word 문서 로드

 다음으로 HTML로 변환하려는 Word 문서를 로드해 보겠습니다. 이 튜토리얼에서는 다음과 같은 문서를 사용합니다.`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

이 코드 줄은 지정된 디렉터리에서 문서를 로드합니다.

## 3단계: HTML 저장 옵션 구성

CSS 및 글꼴과 같은 리소스를 내보내려면 다음을 구성해야 합니다.`HtmlSaveOptions`. 이 단계는 HTML 출력이 잘 구성되어 있고 필요한 리소스가 포함되어 있는지 확인하는 데 중요합니다.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://example.com/resources"
};
```

각 옵션의 기능을 분석해 보겠습니다.
- `CssStyleSheetType = CssStyleSheetType.External`: 이 옵션은 CSS 스타일이 외부 스타일시트에 저장되도록 지정합니다.
- `ExportFontResources = true`: 글꼴 리소스를 내보낼 수 있습니다.
- `ResourceFolder = dataDir + "Resources"`: 리소스(예: 글꼴 및 CSS 파일)가 저장될 로컬 폴더를 지정합니다.
- `ResourceFolderAlias = "http://example.com/resources"`: HTML 파일에서 사용될 리소스 폴더의 별칭을 설정합니다.

## 4단계: 문서를 HTML로 저장

저장 옵션이 구성되면 마지막 단계는 문서를 HTML 파일로 저장하는 것입니다. 방법은 다음과 같습니다.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

이 코드 줄은 내보낸 리소스와 함께 문서를 HTML 형식으로 저장합니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서를 HTML로 저장하는 동안 리소스를 성공적으로 내보냈습니다. 이 강력한 라이브러리를 사용하면 Word 문서를 프로그래밍 방식으로 처리하는 것이 매우 쉬워집니다. 웹 애플리케이션에서 작업 중이거나 오프라인 사용을 위해 문서를 변환해야 하는 경우 Aspose.Words가 도와드립니다.

## FAQ

### 글꼴 및 CSS와 함께 이미지를 내보낼 수 있나요?
 그래 넌 할수있어! Aspose.Words for .NET은 이미지 내보내기도 지원합니다. 구성을 확인하세요.`HtmlSaveOptions` 따라서.

### 외부 스타일시트를 사용하는 대신 CSS를 삽입하는 방법이 있나요?
 전적으로. 설정할 수 있습니다`CssStyleSheetType` 에게`CssStyleSheetType.Embedded` 임베디드 스타일을 선호한다면.

### 출력 HTML 파일의 이름을 어떻게 사용자 정의할 수 있나요?
 원하는 파일 이름을 지정할 수 있습니다.`doc.Save` 방법. 예를 들어,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### Aspose.Words는 HTML 외에 다른 형식을 지원합니까?
 예, PDF, DOCX, TXT 등 다양한 형식을 지원합니다. 확인해 보세요[선적 서류 비치](https://reference.aspose.com/words/net/) 전체 목록을 보려면.

### 추가 지원과 리소스는 어디서 얻을 수 있나요?
더 많은 도움을 받으려면 다음을 방문하세요.[Aspose.Words 지원 포럼](https://forum.aspose.com/c/words/8) . 자세한 문서와 예제는 다음에서 찾을 수도 있습니다.[Aspose 웹 사이트](https://reference.aspose.com/words/net/).