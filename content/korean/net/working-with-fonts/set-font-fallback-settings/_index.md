---
title: 글꼴 대체 설정 지정
linktitle: 글꼴 대체 설정 지정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words에서 글꼴 대체 설정을 구성하는 방법을 알아보세요. 이 종합 가이드는 문서의 모든 문자가 올바르게 표시되도록 보장합니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-font-fallback-settings/
---

다양한 언어나 특수 문자 등 다양한 텍스트 요소가 포함된 문서로 작업할 때 이러한 요소가 올바르게 표시되는지 확인하는 것이 중요합니다. Aspose.Words for .NET은 글꼴 대체 설정이라는 강력한 기능을 제공합니다. 이 기능은 원본 글꼴이 특정 문자를 지원하지 않을 때 글꼴 대체 규칙을 정의하는 데 도움이 됩니다. 이 가이드에서는 단계별 튜토리얼에서 Aspose.Words for .NET을 사용하여 글꼴 대체 설정을 구성하는 방법을 살펴보겠습니다.

## 전제조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- C#에 대한 기본 지식: C# 프로그래밍 언어 및 .NET 프레임워크에 대한 지식.
-  .NET용 Aspose.Words: 다음에서 다운로드하여 설치하세요.[다운로드 링크](https://releases.aspose.com/words/net/).
- 개발 환경: 코드를 작성하고 실행하기 위한 Visual Studio와 같은 설정입니다.
-  샘플 문서: 샘플 문서를 준비합니다(예:`Rendering.docx`) 테스트 준비가 완료되었습니다.
- 글꼴 대체 규칙 XML: 글꼴 대체 규칙을 정의하는 XML 파일을 준비합니다.

## 네임스페이스 가져오기

Aspose.Words를 사용하려면 필요한 네임스페이스를 가져와야 합니다. 이를 통해 문서 처리에 필요한 다양한 클래스와 메소드에 접근할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## 1단계: 문서 디렉터리 정의

먼저 문서가 저장되는 디렉터리를 정의합니다. 이는 문서를 찾고 처리하는 데 필수적입니다.

```csharp
// 문서 디렉토리의 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드

 문서를 Aspose.Words에 로드하세요.`Document` 물체. 이 단계에서는 프로그래밍 방식으로 문서 작업을 수행할 수 있습니다.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: 글꼴 설정 구성

 새로 만들기`FontSettings` 개체를 선택하고 XML 파일에서 글꼴 대체 설정을 로드합니다. 이 XML 파일에는 글꼴 대체 규칙이 포함되어 있습니다.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## 4단계: 문서에 글꼴 설정 적용

 구성된 할당`FontSettings` 문서에. 이렇게 하면 문서를 렌더링할 때 글꼴 대체 규칙이 적용됩니다.

```csharp
doc.FontSettings = fontSettings;
```

## 5단계: 문서 저장

마지막으로 문서를 저장합니다. 적절한 글꼴 대체를 보장하기 위해 저장 작업 중에 글꼴 대체 설정이 사용됩니다.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## XML 파일: 글꼴 대체 규칙

다음은 글꼴 대체 규칙을 정의하는 XML 파일의 모양에 대한 예입니다.

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## 결론

다음 단계를 수행하면 Aspose.Words for .NET에서 글꼴 대체 설정을 효과적으로 설정하고 사용할 수 있습니다. 이렇게 하면 원본 글꼴이 특정 문자를 지원하지 않는 경우에도 문서가 모든 문자를 올바르게 표시할 수 있습니다. 이러한 설정을 구현하면 문서의 품질과 가독성이 크게 향상됩니다.

## 자주 묻는 질문

### Q1: 글꼴 대체란 무엇입니까?

글꼴 대체는 원본 글꼴이 특정 문자를 지원하지 않는 경우 글꼴을 대체하여 모든 텍스트 요소가 올바르게 표시되도록 하는 기능입니다.

### Q2: 여러 대체 글꼴을 지정할 수 있나요?

예, XML 규칙에 여러 대체 글꼴을 지정할 수 있습니다. Aspose.Words는 해당 문자를 지원하는 글꼴을 찾을 때까지 지정된 순서대로 각 글꼴을 확인합니다.

### Q3: .NET용 Aspose.Words를 어디서 다운로드할 수 있나요?

 다음에서 다운로드할 수 있습니다.[Aspose 다운로드 페이지](https://releases.aspose.com/words/net/).

### 질문 4: 글꼴 대체 규칙에 대한 XML 파일을 어떻게 생성합니까?

XML 파일은 텍스트 편집기를 사용하여 생성할 수 있습니다. 이 자습서에 제공된 예제에 표시된 구조를 따라야 합니다.

### Q5: Aspose.Words에 대한 지원이 제공됩니까?

 예, 다음에서 지원을 받으실 수 있습니다.[Aspose.Words 지원 포럼](https://forum.aspose.com/c/words/8).