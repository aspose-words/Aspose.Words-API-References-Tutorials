---
title: 글꼴 폴더 설정
linktitle: 글꼴 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words에서 글꼴 디렉터리를 설정하고 문서에 사용되는 글꼴의 가용성을 확인하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folder/
---
이 튜토리얼에서는 .NET용 Aspose.Words에서 글꼴 디렉터리를 설정하는 방법을 보여줍니다. Word 문서에 사용된 글꼴이 포함된 디렉터리를 지정하는 방법을 배우게 됩니다.

## 전제 조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리

## 1단계: 문서 디렉터리 정의
Word 문서 위치에 대한 디렉터리 경로를 설정하여 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 글꼴 디렉터리 설정
 인스턴스를 생성합니다.`FontSettings` 클래스를 사용하고`SetFontsFolder` 글꼴이 포함된 디렉터리를 지정하는 방법입니다. 바꾸다`"Fonts"` 실제 글꼴 디렉토리의 이름으로.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## 3단계: 글꼴 설정이 포함된 문서 로드
 사용`LoadOptions` 글꼴 설정을 지정하는 클래스`FontSettings` 옵션. 그런 다음`Document` 이 옵션을 사용하여 문서를 로드하는 클래스입니다.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### .NET용 Aspose.Words를 사용하여 글꼴 폴더 설정의 샘플 소스 코드 

```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## 결론
축하합니다! 이제 .NET용 Aspose.Words에서 글꼴 디렉터리를 설정하는 방법을 알았습니다. 이 기능을 사용하면 문서에 사용된 글꼴의 가용성을 보장하고 글꼴 표시의 일관성을 보장할 수 있습니다.

### FAQ

#### Q: Aspose.Words에서 사용자 정의 글꼴 폴더를 어떻게 설정할 수 있나요?

 A: Aspose.Words에서 사용자 정의 글꼴 폴더를 설정하려면 다음을 사용할 수 있습니다.`FontsFolder` 수업과`SetFontsFolders` 글꼴이 포함된 폴더의 경로를 지정하는 방법입니다.

#### Q: Aspose.Words에서 여러 글꼴 폴더를 설정할 수 있나요?

 A: 네, Aspose.Words에서 여러 글꼴 폴더를 설정할 수 있습니다.`SetFontsFolders` 사용하려는 다양한 글꼴 폴더의 경로를 여러 번 사용하세요.

#### Q: 문서에 사용된 글꼴이 정의된 글꼴 폴더에 없으면 어떻게 됩니까?

A: 문서에 사용된 글꼴이 Aspose.Words에 정의된 글꼴 폴더에 없으면 대체 글꼴이 대신 사용됩니다. 이렇게 하면 원본 글꼴을 사용할 수 없는 경우에도 문서의 텍스트가 항상 올바르게 표시됩니다.

#### Q: Aspose.Words에 정의된 글꼴 폴더가 시스템에 설치된 글꼴보다 우선순위를 가집니까?

A: 예, Aspose.Words에 정의된 글꼴 폴더는 시스템에 설치된 글꼴보다 우선합니다. 즉, 정의된 글꼴 폴더와 시스템 글꼴 모두에 동일한 이름의 글꼴이 있는 경우 Word 문서를 처리할 때 글꼴 폴더의 버전이 사용됩니다.