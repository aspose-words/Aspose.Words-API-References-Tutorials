---
title: 우선순위로 글꼴 폴더 설정
linktitle: 우선순위로 글꼴 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 글꼴 폴더에 우선순위를 설정하는 방법을 알아보세요. 우리 가이드는 귀하의 문서가 매번 완벽하게 렌더링되도록 보장합니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folders-with-priority/
---
## 소개

문서 조작의 세계에서 사용자 정의 글꼴 폴더를 설정하면 문서를 어디에서 보든 문서가 완벽하게 렌더링되도록 하는 데 큰 변화를 가져올 수 있습니다. 오늘은 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 폴더에 우선순위를 설정하는 방법에 대해 알아 보겠습니다. 이 포괄적인 가이드는 각 단계를 안내하여 프로세스를 최대한 원활하게 만듭니다.

## 전제 조건

시작하기 전에 필요한 모든 것이 있는지 확인합시다. 간단한 체크리스트는 다음과 같습니다.

-  .NET용 Aspose.Words: 이 라이브러리를 설치해야 합니다. 아직 갖고 있지 않다면 다음을 수행할 수 있습니다.[여기에서 다운로드하세요](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 .NET 개발 환경이 작동하는지 확인하세요.
-  문서 디렉터리: 문서 디렉터리가 있는지 확인하세요. 예제에서는 다음을 사용합니다.`"YOUR DOCUMENT DIRECTORY"` 이 경로의 자리 표시자로 사용됩니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스는 Aspose.Words에서 제공하는 클래스와 메서드에 액세스하는 데 필수적입니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

이제 각 단계를 세분화하여 글꼴 폴더를 우선순위로 설정해 보겠습니다.

## 1단계: 글꼴 소스 설정

시작하려면 글꼴 소스를 정의해야 합니다. 여기가 Aspose.Words에 글꼴을 찾을 위치를 알려주는 곳입니다. 여러 글꼴 폴더를 지정하고 우선순위를 설정할 수도 있습니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
    new SystemFontSource(), 
    new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

이 예에서는 두 가지 글꼴 소스를 설정합니다.
- SystemFontSource: 시스템에 설치된 모든 글꼴을 포함하는 기본 글꼴 소스입니다.
-  FolderFontSource: 다음 위치에 있는 사용자 정의 글꼴 폴더입니다.`C:\\MyFonts\\` . 그만큼`true` 매개변수는 이 폴더를 반복적으로 검사해야 함을 지정합니다.`1` 우선순위를 정합니다.

## 2단계: 문서 로드

그런 다음 작업하려는 문서를 로드합니다. 문서가 지정된 디렉토리에 있는지 확인하십시오.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 이 코드 줄은 다음과 같은 문서를 로드합니다.`Rendering.docx` 문서 디렉토리에서.

## 3단계: 새 글꼴 설정으로 문서 저장

마지막으로 문서를 저장하세요. 문서를 저장하면 Aspose.Words는 사용자가 지정한 글꼴 설정을 사용합니다.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

 그러면 문서가 문서 디렉터리에 다음 이름의 PDF로 저장됩니다.`WorkingWithFonts.SetFontsFoldersWithPriority.pdf`.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 우선순위가 있는 글꼴 폴더를 성공적으로 설정했습니다. 사용자 정의 글꼴 폴더와 우선 순위를 지정하면 문서를 보는 위치에 관계없이 문서가 일관되게 렌더링되도록 할 수 있습니다. 이는 특정 글꼴이 기본적으로 설치되지 않은 환경에서 특히 유용합니다.

## FAQ

### 사용자 정의 글꼴 폴더를 설정해야 하는 이유는 무엇입니까?
사용자 정의 글꼴 폴더를 설정하면 문서를 보고 있는 시스템에 설치되지 않은 글꼴을 사용하는 경우에도 문서가 올바르게 렌더링됩니다.

### 여러 개의 사용자 정의 글꼴 폴더를 설정할 수 있나요?
예, 여러 글꼴 폴더를 지정할 수 있습니다. Aspose.Words를 사용하면 각 폴더의 우선순위를 설정하여 가장 중요한 글꼴이 먼저 검색되도록 할 수 있습니다.

### 지정된 모든 소스에서 글꼴이 누락되면 어떻게 되나요?
지정된 모든 소스에서 글꼴이 누락된 경우 Aspose.Words는 대체 글꼴을 사용하여 문서를 계속 읽을 수 있는지 확인합니다.

### 시스템 글꼴의 우선순위를 변경할 수 있나요?
시스템 글꼴은 항상 기본적으로 포함되지만 사용자 정의 글꼴 폴더를 기준으로 우선순위를 설정할 수 있습니다.

### 사용자 정의 글꼴 폴더에 네트워크 경로를 사용할 수 있습니까?
예, 네트워크 경로를 사용자 정의 글꼴 폴더로 지정하여 글꼴 리소스를 네트워크 위치에 중앙 집중화할 수 있습니다.