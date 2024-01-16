---
title: 렌더링 시 기본 글꼴 지정
linktitle: 렌더링 시 기본 글꼴 지정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 기본 글꼴을 지정하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/specify-default-font-when-rendering/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 기본 글꼴을 지정하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 문서를 렌더링할 때 사용할 기본 글꼴을 지정하는 방법을 알게 될 것입니다.

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 편집된 렌더링 문서를 저장하려는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 렌더링할 문서 로드
 다음으로 렌더링할 문서를 로드해야 합니다.`Document` 수업. 올바른 문서 경로를 지정하십시오.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: 기본 글꼴 설정
 이제 인스턴스를 생성하여 렌더링할 때 사용할 기본 글꼴을 지정할 수 있습니다.`FontSettings` 수업과 설정`DefaultFontName` 의 재산`DefaultFontSubstitution` 에 반대하다`DefaultFontSubstitution` 물체`SubstitutionSettings` ~의`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## 4단계: 렌더링된 문서 저장
 마지막으로 다음을 사용하여 렌더링된 문서를 파일로 저장할 수 있습니다.`Save()` 의 방법`Document` 수업. 올바른 경로와 파일 이름을 지정하십시오.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### .NET용 Aspose.Words를 사용하여 렌더링할 때 기본 글꼴 지정에 대한 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// 여기에 정의된 기본 글꼴을 렌더링 중에 찾을 수 없는 경우
// 대신 컴퓨터에서 가장 가까운 글꼴이 사용됩니다.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 렌더링할 때 기본 글꼴을 지정하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 문서를 렌더링할 때 사용할 기본 글꼴을 쉽게 설정할 수 있습니다. Aspose.Words는 문서의 글꼴을 사용한 단어 처리를 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 특정 요구 사항에 맞게 문서 렌더링을 제어하고 사용자 정의할 수 있습니다.

### FAQ

#### Q: Aspose.Words에서 PDF로 변환할 때 기본 글꼴을 어떻게 지정합니까?

 A: Aspose.Words에서 PDF로 변환할 때 기본 글꼴을 지정하려면`PdfOptions` 클래스를 설정하고`DefaultFontName` 속성을 원하는 글꼴 이름으로 설정합니다.

#### Q: PDF로 변환할 때 기본 글꼴을 사용할 수 없으면 어떻게 되나요?

A: PDF로 변환할 때 지정된 기본 글꼴을 사용할 수 없는 경우 Aspose.Words는 대체 글꼴을 사용하여 변환된 문서의 텍스트를 표시합니다. 이로 인해 원본 글꼴과 모양이 약간 다를 수 있습니다.

#### Q: DOCX 또는 HTML과 같은 다른 출력 형식에 대한 기본 글꼴을 지정할 수 있습니까?

A: 예, 적절한 변환 옵션을 사용하고 각 형식에 해당 속성을 설정하여 DOCX 또는 HTML과 같은 다른 출력 형식에 대한 기본 글꼴을 지정할 수 있습니다.

#### Q: Aspose.Words에 지정된 기본 글꼴을 어떻게 확인할 수 있나요?

 A: Aspose.Words에 지정된 기본 글꼴을 확인하려면`DefaultFontName` 의 재산`PdfOptions` 클래스를 구성하고 구성된 글꼴의 이름을 검색합니다.

#### Q: 문서의 각 섹션에 대해 서로 다른 기본 글꼴을 지정할 수 있습니까?

A: 예, 각 섹션에 특정한 서식 옵션을 사용하여 문서의 각 섹션에 대해 서로 다른 기본 글꼴을 지정할 수 있습니다. 그러나 이를 위해서는 Aspose.Words 기능을 사용하여 문서에 대한 보다 고급 조작이 필요합니다.