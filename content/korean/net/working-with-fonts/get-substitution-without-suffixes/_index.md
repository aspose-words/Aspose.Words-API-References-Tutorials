---
title: 접미사 없이 대체 가져오기
linktitle: 접미사 없이 대체 가져오기
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 접미사 없는 재정의를 얻는 방법을 알아봅니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/get-substitution-without-suffixes/
---

이 튜토리얼에서는 .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서에서 접미사 없이 재정의를 얻는 방법을 보여 드리겠습니다. 접미사가 없는 대체는 문서를 표시하거나 인쇄할 때 글꼴 대체 문제를 해결하는 데 사용됩니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

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

## 2단계: 문서 로드 및 접미사 없이 대체 항목 구성
 다음으로, 다음을 사용하여 문서를 로드하겠습니다.`Document` 클래스를 사용하여 접미사가 없는 대체 항목을 구성하고`DocumentSubstitutionWarnings` 수업. 또한 글꼴이 포함된 폴더를 지정하여 글꼴 소스를 추가하겠습니다.

```csharp
// 문서를 로드하고 접미사 없이 대체 항목을 구성합니다.
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## 3단계: 문서 저장
마지막으로 접미사 없음 재정의가 적용된 문서를 저장합니다.

```csharp
// 문서 저장
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### .NET용 Aspose.Words를 사용하여 접미사 없이 대체 가져오기에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 접미사 없이 재정의를 얻는 방법을 살펴보았습니다. 접미사 없는 대체는 글꼴 대체 문제를 해결하는 데 유용합니다. 이 기능을 사용하여 문서의 표시 및 인쇄를 개선하세요.

### FAQ

#### Q: Aspose.Words가 글꼴 대체에 접미사를 추가하는 이유는 무엇입니까?

A: Aspose.Words는 원래 글꼴과 대체 글꼴 간의 충돌을 피하기 위해 대체 글꼴에 접미사를 추가합니다. 이는 문서를 변환하고 조작할 때 최대의 호환성을 보장하는 데 도움이 됩니다.

#### Q: Aspose.Words에서 접미사 없이 글꼴 대체를 어떻게 검색할 수 있나요?

 A: Aspose.Words에서 접미사 없이 대체 글꼴을 검색하려면 다음을 사용할 수 있습니다.`FontSubstitutionSettings` 수업과`RemoveSuffixes` 재산. 이 속성을 다음으로 설정`true` 추가된 접미사 없이 글꼴 대체를 가져옵니다.

#### Q: Aspose.Words에서 글꼴 대체에 접미사 추가를 비활성화할 수 있습니까?

A: 아니요. Aspose.Words에서 글꼴 대체에 접미사 추가를 비활성화하는 것은 불가능합니다. 문서 호환성과 일관성을 보장하기 위해 기본적으로 접미사가 추가됩니다.

#### Q: Aspose.Words의 글꼴 대체에서 원하지 않는 접미사를 어떻게 필터링할 수 있나요?

 A: Aspose.Words의 글꼴 대체에서 원치 않는 접미사를 필터링하려면 다음과 같은 문자열 처리 기술을 사용할 수 있습니다.`Replace` 또는`Substring` 포함하고 싶지 않은 특정 접미사를 제거하는 방법.