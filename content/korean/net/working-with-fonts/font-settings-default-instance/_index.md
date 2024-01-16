---
title: 글꼴 설정 기본 인스턴스
linktitle: 글꼴 설정 기본 인스턴스
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 기본 글꼴 설정을 구성하는 방법을 알아봅니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/font-settings-default-instance/
---

이 튜토리얼에서는 .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서에서 기본 글꼴 설정을 구성하는 방법을 안내합니다. 기본 글꼴 설정을 사용하면 문서를 로드하고 렌더링할 때 사용되는 글꼴 소스를 지정할 수 있습니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

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

## 2단계: 기본 글꼴 설정 구성
 다음으로 인스턴스를 생성하겠습니다.`FontSettings` 사용하여`FontSettings.DefaultInstance`를 선택한 다음 문서를 로드하고 렌더링할 때 사용되는 글꼴 소스를 지정합니다. 이 예에서는 시스템 글꼴 소스와 폴더 글꼴 소스를 사용하고 있습니다.

```csharp
// 기본 글꼴 설정 구성
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## 3단계: 글꼴 설정이 포함된 문서 업로드
 이제 다음을 사용하여 문서를 로드하겠습니다.`LoadOptions` 사용할 글꼴 설정을 지정합니다.

```csharp
// 글꼴 설정이 포함된 문서를 로드합니다.
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### .NET용 Aspose.Words를 사용하는 글꼴 설정 기본 인스턴스의 샘플 소스 코드 
```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 기본 글꼴 설정을 구성하는 방법을 살펴보았습니다. 문서를 로드하고 렌더링할 때 사용되는 글꼴 소스를 지정하면 문서의 글꼴 모양을 제어할 수 있습니다. 이 기능을 사용하여 프로젝트의 글꼴 설정을 사용자 정의하세요.

### FAQ

#### Q: Aspose.Words에서 기본 글꼴을 어떻게 설정하나요?

 A: Aspose.Words에서 기본 글꼴을 설정하려면 다음을 사용할 수 있습니다.`FontSettings` 수업과`DefaultFontName` 원하는 글꼴의 이름을 지정하는 속성입니다.

#### Q: Aspose.Words에서 기본 글꼴 크기를 지정할 수 있나요?

 A: 예, Aspose.Words에서 기본 글꼴 크기를 지정할 수 있습니다.`DefaultFontSize` 의 재산`FontSettings` 수업. 원하는 포인트 크기를 설정할 수 있습니다.

#### Q: Aspose.Words에서 기본 글꼴 색상을 설정할 수 있나요?

 A: 예, Aspose.Words에서 기본 글꼴 색상을 설정할 수 있습니다.`DefaultColor` 의 재산`FontSettings` 수업. RGB 값이나 미리 정의된 이름을 사용하여 색상을 지정할 수 있습니다.

#### Q: 기본 글꼴 설정은 모든 문서에 적용됩니까?

A: 예, 기본 글꼴 설정은 개별 문서에 대해 특정 설정이 지정되지 않는 한 Aspose.Words에서 생성되거나 편집된 모든 문서에 적용됩니다.