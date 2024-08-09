---
title: 글꼴 폴더 시스템 및 사용자 정의 폴더 설정
linktitle: 글꼴 폴더 시스템 및 사용자 정의 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 시스템 및 사용자 정의 글꼴 폴더를 설정하여 문서가 다양한 환경에서 올바르게 표시되도록 하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## 소개

고유한 글꼴 스타일로 문서를 작성하고 있는데 다른 컴퓨터에서는 해당 글꼴이 올바르게 표시되지 않는다는 사실을 발견했다고 상상해 보십시오. 실망스럽죠? 여기에서 글꼴 폴더 구성이 시작됩니다. .NET용 Aspose.Words를 사용하면 시스템 및 사용자 정의 글꼴 폴더를 정의하여 문서가 항상 의도한 대로 보이도록 할 수 있습니다. 이를 달성할 수 있는 방법을 살펴보겠습니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words: 아직 다운로드하지 않았다면 다운로드하세요.[여기](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 IDE.
- C#에 대한 기본 지식: C#에 익숙하면 코드 예제를 따라가는 데 도움이 됩니다.

## 네임스페이스 가져오기

먼저 프로젝트에 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

이제 프로세스를 간단한 단계로 나누어 보겠습니다.

## 1단계: 문서 로드

 시작하려면 Word 문서를 Aspose.Words에 로드하세요.`Document` 물체. 이 문서는 글꼴 폴더를 설정하려는 문서입니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## 2단계: 글꼴 설정 초기화

 새 인스턴스 만들기`FontSettings`. 이 개체를 사용하면 글꼴 소스를 관리할 수 있습니다.

```csharp
FontSettings fontSettings = new FontSettings();
```

## 3단계: 시스템 글꼴 소스 검색

기본 시스템 글꼴 소스를 검색합니다. Windows 시스템에서는 일반적으로 "Windows\Fonts"가 포함됩니다.\" 디렉토리.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## 4단계: 사용자 정의 글꼴 폴더 추가

추가 글꼴이 포함된 사용자 정의 폴더를 추가합니다. 이는 시스템 글꼴 디렉토리에 설치되지 않은 특정 글꼴이 있는 경우에 유용합니다.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## 5단계: 글꼴 소스 업데이트

 글꼴 소스 목록을 다시 배열로 변환하고`FontSettings` 물체.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## 6단계: 문서에 글꼴 설정 적용

 마지막으로 구성된 내용을 적용합니다.`FontSettings` 문서에 PDF 등 원하는 형식으로 저장하세요.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## 결론

그리고 거기에 있습니다! 다음 단계를 수행하면 Word 문서가 시스템 글꼴이든 특정 디렉터리에 저장된 사용자 지정 글꼴이든 올바른 글꼴을 사용하는지 확인할 수 있습니다. 이 설정은 다양한 환경에서 문서 모양의 무결성을 유지하는 데 도움이 됩니다.

## FAQ

### 시스템 폴더와 사용자 정의 폴더 모두에 글꼴이 없으면 어떻게 됩니까?

Aspose.Words는 누락된 글꼴을 대체하기 위해 기본 글꼴을 사용하여 문서를 계속 읽을 수 있도록 보장합니다.

### 여러 개의 사용자 정의 글꼴 폴더를 추가할 수 있나요?

 예, 생성 과정을 반복하여 여러 개의 사용자 정의 글꼴 폴더를 추가할 수 있습니다.`FolderFontSource` 개체를 글꼴 소스 목록에 추가합니다.

### 사용자 정의 글꼴 폴더에 네트워크 경로를 사용할 수 있습니까?

 예, 다음에서 네트워크 경로를 지정할 수 있습니다.`FolderFontSource` 건설자.

### Aspose.Words는 문서 저장을 위해 어떤 파일 형식을 지원합니까?

Aspose.Words는 DOCX, PDF, HTML 등을 포함한 다양한 형식을 지원합니다.

### 글꼴 대체 알림을 어떻게 처리합니까?

 다음을 사용하여 글꼴 대체 알림을 처리할 수 있습니다.`FontSettings` 수업의`FontSubstitutionWarning`이벤트.