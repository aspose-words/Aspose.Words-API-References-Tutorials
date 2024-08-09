---
title: 글꼴 폴더 설정
linktitle: 글꼴 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: Word 문서가 누락된 글꼴 없이 올바르게 렌더링되도록 .NET용 Aspose.Words에서 사용자 정의 글꼴 폴더를 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folder/
---
## 소개

.NET 응용 프로그램에서 Word 문서 작업을 하는 동안 글꼴이 누락되는 문제에 직면한 적이 있습니까? 글쎄, 당신은 혼자가 아닙니다. 올바른 글꼴 폴더를 설정하면 이 문제를 원활하게 해결할 수 있습니다. 이 가이드에서는 .NET용 Aspose.Words를 사용하여 글꼴 폴더를 설정하는 방법을 안내합니다. 뛰어들어보자!

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 설치된 Visual Studio
- .NET 프레임워크 설정
-  .NET 라이브러리용 Aspose.Words. 아직 다운로드하지 않았다면 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).

## 네임스페이스 가져오기

먼저 Aspose.Words를 사용하려면 필요한 네임스페이스를 가져와야 합니다. 코드 파일 상단에 다음 줄을 추가합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

다음 단계를 주의 깊게 따르면 글꼴 폴더 설정은 간단합니다.

## 1단계: 문서 디렉터리 정의

무엇보다도 먼저 문서 디렉토리의 경로를 정의하십시오. 이 디렉토리에는 Word 문서와 사용하려는 글꼴이 포함됩니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 꼭 교체하세요`"YOUR DOCUMENT DIRECTORY"` 디렉터리의 실제 경로를 사용합니다.

## 2단계: FontSettings 초기화

 이제 초기화를 해야 합니다.`FontSettings` 물체. 이 개체를 사용하면 사용자 정의 글꼴 폴더를 지정할 수 있습니다.

```csharp
FontSettings fontSettings = new FontSettings();
```

## 3단계: 글꼴 폴더 설정

 사용하여`SetFontsFolder` 의 방법`FontSettings` 개체에서 사용자 정의 글꼴이 저장되는 폴더를 지정합니다.

```csharp
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

 여기,`dataDir + "Fonts"` 문서 디렉토리 내의 "Fonts"라는 폴더를 가리킵니다. 두 번째 매개변수,`false`, 폴더가 재귀적이지 않음을 나타냅니다.

## 4단계: LoadOptions 생성

 다음으로,`LoadOptions` 수업. 이 클래스는 지정된 글꼴 설정으로 문서를 로드하는 데 도움이 됩니다.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
```

## 5단계: 문서 로드

 마지막으로 다음을 사용하여 Word 문서를 로드합니다.`Document` 수업과`LoadOptions` 물체.

```csharp
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```

 다음을 확인하세요.`"Rendering.docx"` Word 문서의 이름입니다. 파일 이름으로 바꿀 수 있습니다.

## 결론

그리고 거기에 있습니다! 다음 단계를 따르면 .NET용 Aspose.Words에서 사용자 정의 글꼴 폴더를 쉽게 설정하여 모든 글꼴이 올바르게 렌더링되도록 할 수 있습니다. 이 간단한 설정을 통해 많은 어려움을 덜고 문서를 원하는 대로 정확하게 볼 수 있습니다.

## FAQ

### 사용자 정의 글꼴 폴더를 설정해야 하는 이유는 무엇입니까?
사용자 정의 글꼴 폴더를 설정하면 Word 문서에 사용된 모든 글꼴이 올바르게 렌더링되어 글꼴 누락 문제를 방지할 수 있습니다.

### 여러 글꼴 폴더를 설정할 수 있나요?
 예, 다음을 사용할 수 있습니다.`SetFontsFolders` 여러 폴더를 지정하는 방법입니다.

### 글꼴을 찾을 수 없으면 어떻게 되나요?
Aspose.Words는 누락된 글꼴을 시스템 글꼴과 유사한 글꼴로 대체하려고 시도합니다.

### Aspose.Words는 .NET Core와 호환됩니까?
예, Aspose.Words는 .NET Framework와 함께 .NET Core를 지원합니다.

### 문제가 발생하면 어디서 지원을 받을 수 있나요?
 에서 지원을 받으실 수 있습니다.[Aspose.Words 지원 포럼](https://forum.aspose.com/c/words/8).