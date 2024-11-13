---
title: 글꼴을 Base 64로 내보내기
linktitle: 글꼴을 Base 64로 내보내기
second_title: Aspose.Words 문서 처리 API
description: 이 자세한 튜토리얼에서 Aspose.Words for .NET을 사용하여 글꼴을 Base64로 내보내는 방법을 알아보세요. 글꼴이 HTML 파일에 올바르게 내장되고 표시되는지 확인하세요.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---
## 소개

Word 문서를 프로그래밍 방식으로 조작하는 데 있어 Aspose.Words for .NET은 강력한 도구입니다. 멋진 기능 중 하나는 HTML 파일 내에서 글꼴을 Base64로 내보내 다양한 브라우저와 시스템에서 글꼴이 올바르게 임베드되고 표시되도록 하는 것입니다. 이 튜토리얼에서는 이를 달성하는 방법을 알아보겠습니다. Word 문서 글꼴을 웹 친화적으로 만들 준비가 되셨나요? 시작해 볼까요!

## 필수 조건

코딩에 들어가기 전에 먼저 필요한 모든 것이 있는지 확인해 보겠습니다.

-  .NET 라이브러리용 Aspose.Words: 여기에서 다운로드할 수 있습니다.[Aspose 릴리스](https://releases.aspose.com/words/net/) 페이지.
- .NET 개발 환경: Visual Studio와 같은 모든 IDE가 완벽하게 작동합니다.
- C#에 대한 기본 지식: 전문가가 될 필요는 없지만, 기본적인 이해가 있으면 도움이 됩니다.

## 네임스페이스 가져오기

Aspose.Words for .NET을 사용하려면 C# 코드에서 필요한 네임스페이스를 가져와야 합니다. 이렇게 하면 모든 클래스와 메서드를 사용할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1단계: 프로젝트 설정

먼저, 프로젝트를 설정하고 Aspose.Words 라이브러리를 설치해 보겠습니다.

### 1.1 새 프로젝트 만들기

Visual Studio를 열고 새 콘솔 앱 프로젝트를 만듭니다. "ExportFontsBase64"와 같이 의미 있는 이름을 지정합니다.

### 1.2 Aspose.Words 설치

NuGet 패키지 관리자를 통해 Aspose.Words for .NET을 설치할 수 있습니다.

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭합니다.
2. "NuGet 패키지 관리"를 선택합니다.
3. "Aspose.Words"를 검색하여 설치하세요.

또는 패키지 관리자 콘솔에서 다음 명령을 실행할 수 있습니다.

```sh
Install-Package Aspose.Words
```

## 2단계: Word 문서 로드

이제 프로젝트가 설정되었으니, 글꼴을 내보낼 Word 문서를 로드해 보겠습니다.

### 2.1 문서 디렉토리 정의

먼저, Word 문서가 있는 디렉토리를 정의합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

### 2.2 문서 로드

 다음으로, 다음을 사용하여 문서를 로드합니다.`Document` 수업:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

"Rendering.docx"가 지정된 디렉토리에 있는지 확인하세요.

## 3단계: HTML 저장 옵션 구성

 글꼴을 Base64로 내보내려면 다음을 구성해야 합니다.`HtmlSaveOptions`.


 인스턴스를 생성합니다`HtmlSaveOptions` 그리고 설정하다`ExportFontsAsBase64`재산에`true`:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

## 4단계: 문서를 HTML로 저장

마지막으로 구성된 옵션으로 문서를 저장해 보겠습니다.


 사용하세요`Save` 의 방법`Document` 문서를 저장하는 클래스:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

이 줄은 글꼴을 Base64로 내보내어 HTML 파일로 문서를 저장하고, 글꼴이 HTML 내에 포함되도록 합니다.

## 결론

축하합니다! Aspose.Words for .NET을 사용하여 Word 문서에서 Base64로 글꼴을 성공적으로 내보냈습니다. 이렇게 하면 글꼴이 보존되고 다양한 플랫폼에서 올바르게 표시됩니다. 웹 디스플레이를 위한 문서를 준비하든 단순히 호환성을 보장하든 이 기능은 매우 유용합니다.

## 자주 묻는 질문

### Base64 인코딩이란 무엇인가요?
Base64는 바이너리 데이터(글꼴 등)를 텍스트 포맷으로 인코딩하는 방법입니다. 이를 통해 HTML과 같은 텍스트 기반 포맷과의 호환성이 보장됩니다.

### HTML 글꼴에 Base64를 사용해야 하는 이유는 무엇입니까?
Base64를 사용하면 글꼴이 HTML에 직접 포함되어 글꼴 파일 누락 문제를 방지하고 일관된 표시가 보장됩니다.

### 이 방법을 이미지 등 다른 리소스에도 적용할 수 있나요?
물론입니다! Aspose.Words for .NET을 사용하면 이미지를 포함한 다양한 리소스를 HTML 파일에 Base64로 임베드할 수 있습니다.

### 문서에 여러 개의 글꼴이 있는 경우는 어떻게 되나요?
문제없습니다! Aspose.Words for .NET은 문서에서 사용된 모든 글꼴을 결과 HTML 파일에 Base64로 포함합니다.

### Aspose.Words for .NET은 무료로 사용할 수 있나요?
 Aspose.Words for .NET은 상용 라이브러리입니다. 그러나 다음에서 무료 평가판을 다운로드할 수 있습니다.[Aspose 릴리스](https://releases.aspose.com/) 페이지.
