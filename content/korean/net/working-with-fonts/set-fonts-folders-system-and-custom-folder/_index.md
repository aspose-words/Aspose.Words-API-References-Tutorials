---
title: 글꼴 폴더 시스템 및 사용자 정의 폴더 설정
linktitle: 글꼴 폴더 시스템 및 사용자 정의 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 시스템 및 사용자 정의 글꼴 폴더 설정에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 시스템 글꼴 폴더와 사용자 정의 폴더를 설정하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼을 마치면 .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 사용할 시스템 폴더 및 사용자 정의 폴더를 포함한 여러 글꼴 폴더를 지정하는 방법을 알게 됩니다.

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 편집된 렌더링 문서를 저장하려는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 렌더링할 문서 로드
 그런 다음 렌더링할 문서를 로드할 수 있습니다.`Document` 수업. 올바른 문서 경로를 지정하십시오.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: 시스템 및 사용자 정의 글꼴 폴더 설정
 이제 다음을 사용하여 시스템 글꼴 폴더와 사용자 정의 폴더를 설정할 수 있습니다.`FontSettings` 수업과`SetFontsSources()` 방법. 먼저, 다음을 사용하여 환경에 따른 글꼴 소스 목록을 검색해야 합니다.`GetFontsSources()` 그리고 그것을 목록에 저장하세요. 그런 다음 새 인스턴스를 만들 수 있습니다.`FolderFontSource` 글꼴이 포함된 사용자 정의 폴더의 경로를 지정합니다. 이 인스턴스를 기존 글꼴 소스 목록에 추가합니다. 마지막으로`SetFontsSources()` 새 목록으로 글꼴 소스를 업데이트합니다.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## 4단계: 글꼴 설정 적용
 다음으로 다음을 사용하여 문서에 글꼴 설정을 적용해야 합니다.`FontSettings` 의 재산`Document` 수업.

```csharp
doc.FontSettings = fontSettings;
```

## 5단계: 렌더링된 문서 저장
마지막으로 렌더링된 문서를 파일로 저장할 수 있습니다.

   사용하여`Save()` 의 방법`Document` 수업. 올바른 경로와 파일 이름을 지정하십시오.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### .NET용 Aspose.Words를 사용하여 글꼴 폴더 시스템 및 사용자 정의 폴더 설정에 대한 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// 기본적으로 검색되는 환경 종속 글꼴 소스의 배열을 검색합니다.
// 예를 들어 여기에는 Windows 시스템의 "Windows\Fonts\" 소스가 포함됩니다.
// 글꼴 항목을 훨씬 쉽게 추가하거나 제거할 수 있도록 이 배열을 새 목록에 추가합니다.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Aspose.Words가 다음 폴더에서 글꼴을 검색하도록 지시하는 새 폴더 소스를 추가합니다.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// 기존 글꼴 소스 목록에 글꼴이 포함된 사용자 정의 폴더를 추가합니다.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 렌더링할 때 시스템 글꼴 폴더와 사용자 정의 폴더를 설정하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 문서를 렌더링할 때 사용할 시스템 폴더 및 사용자 정의 폴더를 포함한 여러 글꼴 폴더를 쉽게 지정할 수 있습니다. Aspose.Words는 문서의 글꼴을 사용한 단어 처리를 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 문서를 특정 요구에 맞게 렌더링할 때 사용되는 글꼴 소스를 제어하고 사용자 정의할 수 있습니다.

### FAQ

#### Q: Aspose.Words에서 시스템 글꼴 폴더를 어떻게 설정합니까?

A: Aspose.Words에서 시스템 글꼴 폴더를 설정하려면 아무 것도 할 필요가 없습니다. Aspose.Words는 운영 체제에 설치된 시스템 글꼴을 자동으로 사용합니다.

#### Q: Aspose.Words에서 사용자 정의 글꼴 폴더를 어떻게 설정합니까?

 A: Aspose.Words에서 사용자 정의 글꼴 폴더를 설정하려면 다음을 사용할 수 있습니다.`SetFontsFolders` 의 방법`Fonts` 사용자 정의 글꼴 폴더의 위치를 지정하는 클래스입니다.

#### Q: Aspose.Words에서 여러 사용자 정의 글꼴 폴더를 지정할 수 있나요?

 A: 예, Aspose.Words에서 여러 사용자 정의 글꼴 폴더를 지정할 수 있습니다.`SetFontsFolders` 의 방법`Fonts` 폴더 위치 목록이 있는 클래스입니다.

#### Q: Aspose.Words에 정의된 글꼴 폴더를 어떻게 확인할 수 있나요?

 Aspose.Words에 정의된 글꼴 폴더를 확인하려면`GetFolders` 의 방법`Fonts` 클래스를 사용하여 구성된 글꼴 폴더 목록을 가져옵니다.

#### Q: Aspose.Words에서 사용자 정의 폴더 글꼴이 시스템 글꼴보다 우선합니까?

A: 예, Aspose.Words에서는 사용자 정의 폴더 글꼴이 시스템 글꼴보다 우선합니다. 사용자 정의 폴더와 시스템 글꼴 모두에 글꼴이 있는 경우 Aspose.Words는 사용자 정의 폴더의 버전을 사용합니다.