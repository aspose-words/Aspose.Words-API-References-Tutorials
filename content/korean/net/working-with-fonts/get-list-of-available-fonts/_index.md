---
title: 사용 가능한 글꼴 목록 가져오기
linktitle: 사용 가능한 글꼴 목록 가져오기
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 .NET용 Aspose.Words에서 사용할 수 있는 글꼴 목록을 얻는 방법을 알아봅니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/get-list-of-available-fonts/
---
이 튜토리얼에서는 .NET용 Aspose.Words에서 사용할 수 있는 글꼴 목록을 얻는 방법을 설명합니다. 사용 가능한 글꼴 목록을 통해 문서에 사용할 수 있는 글꼴을 알 수 있습니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리

## 1단계: 문서 디렉터리 정의
 먼저, Word 문서 위치에 대한 디렉터리 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 글꼴 소스 구성
 다음으로 인스턴스를 생성하겠습니다.`FontSettings` 다음을 사용하여 기존 글꼴 소스를 가져옵니다.`GetFontsSources()` 방법. 또한 글꼴이 포함된 폴더를 지정하여 새 글꼴 소스를 추가하겠습니다.

```csharp
// 글꼴 소스 구성
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// 새 글꼴 소스 추가
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## 3단계: 사용 가능한 글꼴 목록 가져오기
 이제 다음을 사용하여 사용 가능한 글꼴을 찾아보겠습니다.`GetAvailableFonts()` 첫 번째 업데이트된 글꼴 소스에 대한 메서드입니다.

```csharp
// 사용 가능한 글꼴 목록 얻기
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### .NET용 Aspose.Words를 사용하여 사용 가능한 글꼴 목록 가져오기의 샘플 소스 코드 

```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Aspose.Words가 다음 폴더에서 글꼴을 검색하도록 지시하는 새 폴더 소스를 추가합니다.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// 기존 글꼴 소스 목록에 글꼴이 포함된 사용자 정의 폴더를 추가합니다.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words에서 사용할 수 있는 글꼴 목록을 얻는 방법을 살펴보았습니다. 이를 통해 문서에 사용할 수 있는 글꼴을 알 수 있습니다. 이 기능을 사용하여 필요에 맞는 적절한 글꼴을 선택하세요.

### FAQ

#### Q: Aspose.Words에서 사용할 수 있는 글꼴 목록을 어떻게 검색할 수 있나요?

 A: Aspose.Words에서 사용 가능한 글꼴 목록을 검색하려면 다음을 사용할 수 있습니다.`FontsProvider` 수업과`GetAvailableFonts` 방법. 이 방법은 시스템에 설치된 모든 글꼴 목록을 반환합니다.

#### Q: Aspose.Words에서 특정 기준에 따라 사용 가능한 글꼴 목록을 필터링할 수 있나요?

A: 예, 특정 기준을 사용하여 Aspose.Words에서 사용 가능한 글꼴 목록을 필터링할 수 있습니다. 예를 들어 글꼴을 계열, 스타일 또는 언어별로 필터링할 수 있습니다.

#### Q: 내 Word 문서에서 사용 가능한 글꼴 목록을 어떻게 사용할 수 있나요?

 A: Word 문서에서 사용할 수 있는 글꼴 목록을 사용하려면 목록을 탐색하고 해당 글꼴의 메서드와 속성을 사용하여 적절한 글꼴을 선택할 수 있습니다.`FontSettings` Aspose.Words의 클래스입니다.