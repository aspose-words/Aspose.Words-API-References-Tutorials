---
title: 속성 열거
linktitle: 속성 열거
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 속성을 열거하는 방법을 알아보세요. 모든 기술 수준의 개발자에게 적합합니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-properties/enumerate-properties/
---
## 소개

프로그래밍 방식으로 Word 문서 작업을 원하시나요? Aspose.Words for .NET은 바로 이를 달성하는 데 도움이 되는 강력한 도구입니다. 오늘은 Aspose.Words for .NET을 사용하여 Word 문서의 속성을 열거하는 방법을 안내하겠습니다. 초보자이시든 경험이 있으신가요? 이 가이드는 대화식이며 따라하기 쉬운 방식으로 단계별로 설명합니다.

## 전제 조건

튜토리얼을 시작하기 전에 시작해야 할 몇 가지 사항이 있습니다.

-  .NET용 Aspose.Words: 다음을 수행할 수 있습니다.[여기에서 다운로드하세요](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio가 권장되지만 모든 C# IDE를 사용할 수 있습니다.
- C#에 대한 기본 지식: C#에 대한 기본적인 이해가 있으면 따라가는 데 도움이 됩니다.

자, 바로 뛰어들어 볼까요!

## 1단계: 프로젝트 설정

먼저 Visual Studio에서 프로젝트를 설정해야 합니다.

1. 새 프로젝트 만들기: Visual Studio를 열고 새 콘솔 응용 프로그램 프로젝트를 만듭니다.
2. .NET용 Aspose.Words 설치: NuGet 패키지 관리자를 사용하여 .NET용 Aspose.Words를 설치합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 "Aspose.Words"를 검색하세요. 패키지를 설치합니다.

## 2단계: 네임스페이스 가져오기

Aspose.Words를 사용하려면 필요한 네임스페이스를 가져와야 합니다. Program.cs 파일 맨 위에 다음을 추가합니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Properties;
```

## 3단계: 문서 로드

다음으로 작업하려는 Word 문서를 로드해 보겠습니다. 이 예에서는 프로젝트 디렉터리에 있는 "Properties.docx"라는 문서를 사용합니다.

1. 문서 경로 정의: 문서 경로를 지정합니다.
2.  문서 로드: Aspose.Words 사용`Document` 문서를 로드하는 클래스입니다.

코드는 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

## 4단계: 문서 이름 표시

문서가 로드되면 해당 이름을 표시할 수 있습니다. Aspose.Words는 이에 대한 속성을 제공합니다:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
```

## 5단계: 내장 속성 열거

기본 제공 속성은 Microsoft Word에서 미리 정의된 메타데이터 속성입니다. 여기에는 제목, 작성자 등이 포함됩니다.

1.  내장 속성에 액세스:`BuiltInDocumentProperties` 수집.
2. 루프 스루 속성: 속성을 반복하고 해당 이름과 값을 표시합니다.

코드는 다음과 같습니다.

```csharp
Console.WriteLine("2. Built-in Properties");

foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
    Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
```

## 6단계: 사용자 정의 속성 열거

사용자 정의 속성은 사용자 정의 메타데이터 속성입니다. 문서에 추가하고 싶은 모든 것이 가능합니다.

1.  사용자 정의 속성에 액세스:`CustomDocumentProperties` 수집.
2. 루프 스루 속성: 속성을 반복하고 해당 이름과 값을 표시합니다.

코드는 다음과 같습니다.

```csharp
Console.WriteLine("3. Custom Properties");

foreach (DocumentProperty prop in doc.CustomDocumentProperties)
    Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
```

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서의 기본 제공 속성과 사용자 지정 속성을 모두 성공적으로 열거했습니다. 이는 Aspose.Words로 할 수 있는 작업에 관한 빙산의 일각에 불과합니다. 문서 생성을 자동화하든 복잡한 문서를 조작하든 Aspose.Words는 삶을 더 쉽게 만들어주는 풍부한 기능 세트를 제공합니다.

## FAQ

### 문서에 새 속성을 추가할 수 있나요?
 예, 다음을 사용하여 새로운 사용자 정의 속성을 추가할 수 있습니다.`CustomDocumentProperties` 수집.

### Aspose.Words는 무료로 사용할 수 있나요?
 Aspose.Words는 다음을 제공합니다.[무료 평가판](https://releases.aspose.com/) 그리고 다른[구매 옵션](https://purchase.aspose.com/buy).

### Aspose.Words에 대한 지원을 받으려면 어떻게 해야 하나요?
 Aspose 커뮤니티에서 지원을 받을 수 있습니다[여기](https://forum.aspose.com/c/words/8).

### Aspose.Words를 다른 .NET 언어와 함께 사용할 수 있나요?
예, Aspose.Words는 VB.NET을 포함한 여러 .NET 언어를 지원합니다.

### 더 많은 예시는 어디서 찾을 수 있나요?
 확인해 보세요[.NET 문서용 Aspose.Words](https://reference.aspose.com/words/net/) 더 많은 예시와 자세한 정보를 확인하세요.
