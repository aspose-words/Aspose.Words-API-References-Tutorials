---
title: 글꼴 폴더 기본 인스턴스 설정
linktitle: 글꼴 폴더 기본 인스턴스 설정
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 튜토리얼을 통해 .NET용 Aspose.Words에서 기본 인스턴스에 대한 글꼴 폴더를 설정하는 방법을 알아보세요. Word 문서를 손쉽게 사용자 정의하세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folders-default-instance/
---
## 소개

안녕하세요, 동료 코더입니다! .NET에서 Word 문서로 작업하는 경우 올바른 글꼴을 사용하는 것이 얼마나 중요한지 알고 계실 것입니다. 오늘은 Aspose.Words for .NET을 사용하여 기본 인스턴스의 글꼴 폴더를 설정하는 방법을 살펴보겠습니다. 모든 사용자 정의 글꼴을 손끝에서 사용하여 문서를 원하는 대로 정확하게 만들 수 있다고 상상해 보십시오. 정말 좋은 것 같죠? 시작해 봅시다!

## 전제 조건

핵심적인 세부 사항을 살펴보기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.
-  .NET용 Aspose.Words: 라이브러리가 설치되어 있는지 확인하세요. 그렇지 않다면 할 수 있습니다[여기에서 다운로드하세요](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio 또는 기타 .NET 호환 IDE.
- C# 기본 지식: C# 프로그래밍에 익숙해야 합니다.
- 글꼴 폴더: 사용자 정의 글꼴이 포함된 디렉터리입니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이는 글꼴 폴더 설정에 필요한 클래스 및 메서드에 액세스하는 데 도움이 됩니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

프로세스를 간단하고 이해하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 데이터 디렉터리 정의

모든 훌륭한 여행은 한 단계에서 시작되며, 우리의 여행은 문서가 저장되는 디렉터리를 정의하는 것부터 시작됩니다. Aspose.Words가 Word 문서를 찾는 곳입니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 여기서 교체하세요`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오. 여기에는 소스 문서가 있고 출력이 저장되는 위치입니다.

## 2단계: 글꼴 폴더 설정

 이제 Aspose.Words에 사용자 정의 글꼴을 찾을 수 있는 위치를 알려드리겠습니다. 이는 다음을 사용하여 글꼴 폴더를 설정함으로써 수행됩니다.`FontSettings.DefaultInstance.SetFontsFolder` 방법.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

 이 줄에서는`"C:\\MyFonts\\"` 사용자 정의 글꼴 폴더의 경로입니다. 두 번째 매개변수,`true`는 이 폴더의 글꼴을 반복적으로 스캔해야 함을 나타냅니다.

## 3단계: 문서 로드

 글꼴 폴더가 설정되면 다음 단계는 Word 문서를 Aspose.Words에 로드하는 것입니다. 이 작업은 다음을 사용하여 수행됩니다.`Document` 수업.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 여기,`dataDir + "Rendering.docx"` Word 문서의 전체 경로를 나타냅니다. 문서가 지정된 디렉토리에 있는지 확인하십시오.

## 4단계: 문서 저장

마지막 단계는 글꼴 폴더를 설정한 후 문서를 저장하는 것입니다. 이렇게 하면 사용자 정의 글꼴이 출력에 올바르게 적용됩니다.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

이 줄은 문서를 사용자 정의 글꼴이 적용된 PDF로 저장합니다. 출력 파일은 소스 문서와 동일한 디렉터리에 위치합니다.

## 결론

그리고 거기에 있습니다! Aspose.Words for .NET에서 기본 인스턴스에 대한 글꼴 폴더를 설정하는 것은 간단한 단계로 나누면 매우 쉽습니다. 이 가이드를 따르면 모든 사용자 정의 글꼴을 사용하여 Word 문서가 원하는 대로 정확하게 표시되는지 확인할 수 있습니다. 그러니 한번 시도해 보시고 문서를 빛나게 해보세요!

## FAQ

### 여러 글꼴 폴더를 설정할 수 있나요?
 예, 다음을 사용하여 여러 글꼴 폴더를 설정할 수 있습니다.`SetFontsFolders` 폴더 경로 배열을 허용하는 메서드입니다.

### Aspose.Words는 문서 저장을 위해 어떤 파일 형식을 지원합니까?
Aspose.Words는 DOCX, PDF, HTML, EPUB 등을 포함한 다양한 형식을 지원합니다.

### Aspose.Words에서 온라인 글꼴을 사용할 수 있습니까?
아니요, Aspose.Words는 현재 로컬 글꼴 파일만 지원합니다.

### 저장된 PDF에 내 사용자 정의 글꼴이 포함되어 있는지 어떻게 확인할 수 있나요?
 설정하여`FontSettings` 올바르게 글꼴을 사용할 수 있는지 확인하면 Aspose.Words는 해당 글꼴을 PDF 출력에 포함시킵니다.

### 지정된 폴더에 글꼴이 없으면 어떻게 되나요?
Aspose.Words는 지정된 글꼴을 찾을 수 없는 경우 대체 글꼴을 사용합니다.