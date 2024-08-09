---
title: 글꼴 폴더를 여러 폴더로 설정
linktitle: 글꼴 폴더를 여러 폴더로 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 여러 글꼴 폴더를 설정하는 방법을 알아보세요. 이 단계별 가이드는 귀하의 문서에 필요한 정확한 글꼴이 사용되도록 보장합니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folders-multiple-folders/
---
## 소개

Word 문서에서 여러 글꼴 소스를 관리하는 방법이 궁금하신가요? 여러 폴더에 글꼴 모음이 흩어져 있고 문서에서 글꼴 모음을 원활하게 사용할 수 있는 방법이 필요할 수도 있습니다. 글쎄, 당신은 운이 좋다! 오늘은 Aspose.Words for .NET을 사용하여 글꼴 폴더를 설정하는 방법을 살펴보겠습니다. 이 가이드는 프로세스를 단계별로 안내하여 문서가 원하는 대로 보이도록 보장합니다.

## 전제 조건

시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하겠습니다. 따라야 할 사항은 다음과 같습니다.

-  .NET용 Aspose.Words: 아직 설치하지 않은 경우 .NET용 Aspose.Words를 다운로드하여 설치하세요. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio 또는 기타 .NET 호환 개발 환경.
- C#에 대한 기본 지식: C#에 조금 익숙해지면 예제를 따르는 데 도움이 됩니다.
- 글꼴 파일: 쉽게 액세스할 수 있는 디렉토리에 글꼴 파일이 저장되어 있는지 확인하세요.

## 네임스페이스 가져오기

먼저 C# 프로젝트에 필요한 네임스페이스를 가져오겠습니다. 이렇게 하면 필요한 모든 Aspose.Words 기능에 액세스할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

해당 세트를 사용하여 .NET용 Aspose.Words에서 글꼴 폴더를 설정하는 단계별 가이드를 살펴보겠습니다.

## 1단계: 문서 로드

좋습니다. 작업하려는 Word 문서를 로드하는 것부터 시작해 보겠습니다. 문서 경로가 준비되어 있는지 확인하세요. 이 예에서는 "Rendering.docx"라는 문서를 사용합니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

여기서는 지정된 디렉터리에서 문서를 로드합니다. 아주 간단하죠?

## 2단계: FontSettings 객체 생성

 다음으로`FontSettings` 물체. 이 개체를 사용하면 문서의 글꼴 소스를 관리할 수 있습니다.

```csharp
FontSettings fontSettings = new FontSettings();
```

 이것`FontSettings`개체는 사용할 글꼴 폴더를 정의하는 데 도움이 됩니다.

## 3단계: 글꼴 폴더 설정

이제 글꼴 폴더 설정이라는 중요한 부분이 나옵니다. 여기에서 글꼴이 있는 디렉터리를 지정합니다. 이 예에서는 "C:\MyFonts"에 글꼴이 있습니다.\" 및 "D:\기타\글꼴\".

```csharp
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

두 번째 매개변수(`true` )는 이러한 폴더가 기본 글꼴 소스를 재정의함을 나타냅니다. 시스템 글꼴 소스도 유지하려면 다음 조합을 사용할 수 있습니다.`GetFontSources`그리고`SetFontSources`.

## 4단계: 문서에 글꼴 설정 적용

글꼴 폴더가 설정되면 이러한 설정을 문서에 적용해야 합니다. 이렇게 하면 렌더링 중에 문서가 지정된 글꼴을 사용하게 됩니다.

```csharp
doc.FontSettings = fontSettings;
```

## 5단계: 문서 저장

마지막으로 문서를 저장해 보겠습니다. 글꼴이 실제로 작동하는지 확인하기 위해 PDF로 저장하겠습니다.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

그리고 거기에 있습니다! 문서에 여러 글꼴 폴더를 성공적으로 설정했습니다.

## 결론

문서에서 글꼴을 관리하는 것은 어려운 작업처럼 보일 수 있지만 .NET용 Aspose.Words를 사용하면 매우 쉽습니다! 이러한 간단한 단계를 따르면 문서가 전문적으로 보이고 필요한 정확한 글꼴을 사용할 수 있습니다. 특정 브랜딩이 필요한 프로젝트를 진행 중이거나 문서의 모양을 더 세밀하게 제어하려는 경우 글꼴 폴더 설정은 숙달할 가치가 있는 기술입니다.

## FAQ

### 글꼴 폴더에 네트워크 경로를 사용할 수 있나요?
예, 글꼴 폴더에 네트워크 경로를 사용할 수 있습니다. 애플리케이션에서 경로에 액세스할 수 있는지 확인하세요.

### 지정된 폴더에 글꼴이 없으면 어떻게 됩니까?
글꼴이 없으면 Aspose.Words는 지정된 기본 글꼴로 돌아가거나 대체 글꼴을 사용합니다.

### 시스템 글꼴을 재정의하지 않고 글꼴 폴더를 추가할 수 있나요?
 전적으로! 사용`FontSettings.GetFontSources` 기존 소스를 검색하고 다음을 사용하여 사용자 정의 폴더와 결합합니다.`FontSettings.SetFontSources`.

### 추가할 수 있는 글꼴 폴더 수에 제한이 있나요?
글꼴 폴더 수에는 엄격한 제한이 없습니다. 그러나 폴더가 많을수록 글꼴 로드 시간이 늘어날 수 있으므로 성능에 주의하세요.

### 내 문서에 어떤 글꼴이 사용되고 있는지 어떻게 확인할 수 있나요?
 당신은 사용할 수 있습니다`FontSettings.GetFontsSources` 문서에 현재 설정된 글꼴 소스를 검색하고 검사하는 방법입니다.