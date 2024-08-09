---
title: 글꼴 폴더 설정
linktitle: 글꼴 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: 이 포괄적인 단계별 가이드를 통해 .NET용 Aspose.Words에서 사용자 정의 글꼴 폴더를 설정하는 방법을 알아보세요. 문서 글꼴을 향상시키려는 개발자에게 적합합니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folders/
---
## 소개

안녕하세요! .NET용 Aspose.Words의 사용자 정의 글꼴 세계로 뛰어들 준비가 되셨습니까? 시작해 봅시다. 이 튜토리얼은 사용자 정의 글꼴 폴더를 설정하는 과정을 안내하여 문서가 원하는 대로 보이도록 합니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 가이드는 모든 단계를 안내합니다. 그럼, 멋진 글꼴을 만들어 보겠습니다!

## 전제 조건

시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.

-  .NET용 Aspose.Words: 다음을 수행할 수 있습니다.[다운로드](https://releases.aspose.com/words/net/) 아직 하지 않았다면 그렇게 하세요.
- Visual Studio: 모든 버전이 작동하지만 최신 버전이 항상 최고입니다.
- 문서: 이 튜토리얼에서는 Word 문서를 사용합니다. 직접 만들거나 기존 것을 사용할 수 있습니다.
- 사용자 정의 글꼴: 일부 사용자 정의 글꼴을 준비하세요. 이를 사용하여 글꼴 폴더를 설정하는 방법을 보여 드리겠습니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이는 Aspose.Words에서 필요한 클래스와 메서드에 액세스하는 데 필수적입니다.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

이러한 네임스페이스를 가져왔으므로 사용자 정의 글꼴 폴더 설정을 시작할 준비가 되었습니다.

## 1단계: 문서 디렉터리 정의

 문서 디렉터리의 경로를 정의하는 것부터 시작하겠습니다. 여기에 Word 문서가 저장됩니다. 우리는 다음과 같은 변수를 사용할 것입니다.`dataDir` 이 경로를 저장합니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 디렉터리의 실제 경로를 사용합니다. Aspose.Words는 문서를 찾을 위치를 알아야 하기 때문에 이는 매우 중요합니다.

## 2단계: 글꼴 소스 설정

 다음으로 글꼴 소스를 설정해야 합니다. 여기가 Aspose.Words에 사용자 정의 글꼴을 찾을 수 있는 위치를 알려주는 곳입니다. 우리는`FontSettings.DefaultInstance.SetFontsSources` 이를 달성하는 방법.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
```

우리가 하는 일은 다음과 같습니다:

- SystemFontSource: Aspose.Words에 시스템의 기본 글꼴을 사용하도록 지시합니다.
-  FolderFontSource: 사용자 정의 글꼴이 포함된 폴더를 지정하는 곳입니다. 바꾸다`"C:\\MyFonts\\"` 사용자 정의 글꼴 디렉토리 경로를 사용하세요. 그만큼`true` 매개변수는 하위 디렉터리도 포함되어야 함을 나타냅니다.

## 3단계: 문서 로드

이제 글꼴 소스를 설정했으므로 작업할 문서를 로드할 차례입니다. 우리는`Document` Aspose.Words의 클래스입니다.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 다음을 확인하세요.`"Rendering.docx"` Word 문서의 이름입니다. 문서의 이름이 다른 경우 이에 맞게 업데이트하세요.

## 4단계: 문서를 PDF로 저장

 마지막으로 문서를 PDF로 저장하여 사용자 정의 글꼴이 실제로 작동하는 모습을 살펴보겠습니다. 우리는`Save` 의 방법`Document` 수업.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

그러면 이전에 설정한 사용자 정의 글꼴을 사용하여 지정된 디렉터리에 문서가 PDF로 저장됩니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words에서 사용자 정의 글꼴 폴더를 성공적으로 설정하고 해당 사용자 정의 글꼴이 포함된 PDF로 문서를 저장했습니다. 정말 멋지죠? 글꼴을 사용자 정의하면 문서의 모양이 크게 달라질 수 있으며 이제 그 방법을 정확히 알게 되었습니다. 즐거운 코딩하세요!

## FAQ

### .NET용 Aspose.Words를 어떻게 설치하나요?

 당신은 할 수 있습니다[다운로드](https://releases.aspose.com/words/net/) 웹사이트에서 Aspose.Words for .NET의 최신 버전을 다운로드하세요.

### 여러 개의 사용자 정의 글꼴 폴더를 사용할 수 있나요?

 예, 여러 개를 추가할 수 있습니다`FolderFontSource` 인스턴스에 대한`SetFontsSources`다른 디렉토리의 글꼴을 사용하는 방법.

### 시스템 글꼴을 포함해야 합니까?

시스템 글꼴을 포함하는 것은 선택 사항이지만 모든 표준 글꼴을 사용할 수 있도록 하는 것이 좋습니다.

### Aspose.Words는 어떤 파일 형식을 지원합니까?

Aspose.Words는 DOCX, DOC, PDF, TXT, HTML 등을 포함한 광범위한 파일 형식을 지원합니다.

### Aspose.Words에 대한 임시 라이선스를 어떻게 얻을 수 있나요?

 당신은 얻을 수 있습니다[임시 면허증](https://purchase.aspose.com/temporary-license/) Aspose 웹사이트에서 Aspose.Words의 전체 기능을 사용해 보세요.