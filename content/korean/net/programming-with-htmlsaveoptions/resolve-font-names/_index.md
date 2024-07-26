---
title: 글꼴 이름 확인
linktitle: 글꼴 이름 확인
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 HTML로 변환할 때 Word 문서의 글꼴 이름을 확인하는 방법을 알아보세요. 자세한 설명이 포함된 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/resolve-font-names/
---
## 소개

안녕하세요, 동료 코더입니다! Word 문서를 HTML로 저장할 때 글꼴 문제로 어려움을 겪고 계시다면 혼자가 아닙니다. 글꼴은 까다로울 수 있지만 걱정하지 마세요. 내가 도와 줄게. 오늘은 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 이름을 확인하는 방법을 살펴보겠습니다. 이 가이드는 글꼴이 HTML 형식에서 올바르게 표시되도록 프로세스를 단계별로 안내합니다.

## 전제조건

시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.

1.  .NET용 Aspose.Words: 아직 다운로드하지 않았다면 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
2.  유효한 라이센스: 라이센스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy) 아니면 임시면허를 취득하세요.[여기](https://purchase.aspose.com/temporary-license/).
3. C# 및 .NET에 대한 기본 지식: 이 자습서에서는 사용자가 C#의 기본 프로그래밍 개념에 익숙하다고 가정합니다.
4. Visual Studio: .NET 프레임워크를 지원하는 모든 버전.

이제 전제 조건이 정렬되었으므로 작업에 뛰어들겠습니다!

## 네임스페이스 가져오기

코딩을 시작하기 전에 필요한 네임스페이스를 프로젝트로 가져왔는지 확인하세요. 이는 Aspose.Words 기능에 액세스하는 데 중요합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1단계: 문서 디렉토리 설정

먼저 문서 디렉터리 경로를 설정해 보겠습니다. 여기에는 Word 문서가 있고 출력을 저장할 위치가 있습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

설명:
 여기,`dataDir` 문서 디렉토리의 경로를 보유합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 시스템의 실제 경로와 함께.

## 2단계: Word 문서 로드

다음으로 처리하려는 Word 문서를 로드해야 합니다. 이 문서에는 확인하려는 글꼴이 있어야 합니다.

```csharp
Document doc = new Document(dataDir + "Missing font.docx");
```

설명:
 우리는`Document` 개체를 선택하고 "Missing Font.docx"라는 Word 문서를 로드합니다.`dataDir`.

## 3단계: HTML 저장 옵션 구성

이제 문서를 HTML로 저장하기 위한 옵션을 설정해 보겠습니다. 여기서는 글꼴 이름이 올바르게 확인되는지 확인합니다.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    PrettyFormat = true,
    ResolveFontNames = true
};
```

설명:
 우리는`HtmlSaveOptions` ~와 함께`SaveFormat.Html` . 그만큼`PrettyFormat` 옵션을 사용하면 HTML 출력을 더 쉽게 읽을 수 있습니다.`ResolveFontNames` 글꼴 이름이 확인되는지 확인합니다.

## 4단계: 문서를 HTML로 저장

마지막으로 구성된 저장 옵션을 사용하여 문서를 HTML 파일로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

설명:
 우리는`Save` 에 대한 방법`Document` 객체, 출력 경로와 우리가 구성한 저장 옵션을 지정합니다. 그러면 글꼴 이름이 확인된 HTML 파일이 생성됩니다.

## 결론

그리고 거기에 있습니다! 다음 단계를 수행하면 .NET용 Aspose.Words를 사용하여 Word 문서를 HTML로 변환할 때 글꼴 이름을 성공적으로 확인할 수 있습니다. 이렇게 하면 글꼴이 올바르게 표시될 뿐만 아니라 HTML 출력이 세련되고 전문적으로 보입니다. 즐거운 코딩하세요!

## FAQ

### .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 프로그래밍 방식으로 Word 문서를 생성, 수정 및 변환할 수 있는 강력한 라이브러리입니다.

### .NET용 Aspose.Words를 어떻게 설치하나요?
 .NET용 Aspose.Words는 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/). 설명서에 제공된 설치 지침을 따르십시오.

### 라이선스 없이 .NET용 Aspose.Words를 사용할 수 있나요?
 예, 하지만 몇 가지 제한 사항이 있습니다. 전체 기능을 이용하려면 라이센스를 구매하세요[여기](https://purchase.aspose.com/buy) 아니면 임시면허를 취득하세요.[여기](https://purchase.aspose.com/temporary-license/).

### 내 글꼴이 HTML에서 올바르게 표시되지 않는 이유는 무엇입니까?
 변환 중에 글꼴이 제대로 해석되지 않으면 이런 일이 발생할 수 있습니다. 사용`ResolveFontNames = true` ~에`HtmlSaveOptions` 이 문제를 해결하는 데 도움이 될 수 있습니다.

### .NET용 Aspose.Words에 대한 지원은 어디서 받을 수 있나요?
 에서 지원을 받으실 수 있습니다.[Aspose.Words 지원 포럼](https://forum.aspose.com/c/words/8).