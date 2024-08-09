---
title: 펜스된 코드
linktitle: 펜스된 코드
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 분리 코드 및 정보 문자열을 추가하는 방법을 알아보세요. 단계별 가이드가 포함되어 있습니다. 문서 서식 기술을 향상시키세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/fenced-code/
---
## 소개

안녕하세요, 동료 코더입니다! 오늘 우리는 Word 문서에 분리 코드와 정보 문자열이 포함된 분리 코드를 추가하는 기술을 익히기 위해 .NET용 Aspose.Words의 세계로 뛰어들었습니다. Word 문서를 캔버스로 상상해 보세요. 예술가인 당신은 노련한 개발자의 정밀함으로 그림을 그리려고 합니다. Aspose.Words를 사용하면 구조화되고 형식화된 코드 블록을 사용하여 프로그래밍 방식으로 문서를 향상시켜 기술 문서를 전문성과 명확성으로 빛나게 만들 수 있습니다.

## 전제 조건

튜토리얼을 시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.

- C#에 대한 기본 지식: C#에 대한 일반적인 이해는 개념을 빠르게 이해하는 데 도움이 됩니다.
-  .NET용 Aspose.Words: .NET용 Aspose.Words가 설치되어 있어야 합니다. 아직 못받으셨다면 꼭 챙겨가세요[여기](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio 또는 익숙한 기타 C# IDE.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져와야 합니다. 이는 프로젝트를 시작하기 전에 모든 도구를 모으는 것과 같습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Style;
```

이제 프로세스를 단계별로 분석해 보겠습니다.

## 1단계: 프로젝트 설정

Word 문서에서 아름답고 서식이 지정된 코드 블록을 만들려면 먼저 Visual Studio에서 새 프로젝트를 설정해야 합니다.

1. 새 프로젝트 만들기: Visual Studio를 열고 새 C# 콘솔 애플리케이션을 만듭니다.
2. Aspose.Words 참조 추가: NuGet 패키지 관리자를 통해 Aspose.Words를 설치합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 Aspose.Words를 검색하면 됩니다.

## 2단계: DocumentBuilder 초기화

이제 프로젝트가 설정되었으므로 Word 문서에 콘텐츠를 추가하기 위한 기본 도구가 될 DocumentBuilder를 초기화해 보겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 3단계: 분리된 코드에 대한 스타일 생성

분리된 코드를 추가하려면 먼저 스타일을 생성해야 합니다. 이것을 코드 블록의 테마를 설정하는 것으로 생각하십시오.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
fencedCode.Font.Name = "Courier New";
fencedCode.Font.Size = 10;
fencedCode.ParagraphFormat.LeftIndent = 20;
fencedCode.ParagraphFormat.RightIndent = 20;
fencedCode.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## 4단계: 문서에 분리 코드 추가

스타일이 준비되었으므로 이제 문서에 분리된 코드 블록을 추가할 수 있습니다.

```csharp
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is a fenced code block");
```

## 5단계: 정보 문자열을 사용하여 분리 코드에 대한 스타일 생성

때로는 프로그래밍 언어를 지정하거나 코드 블록에 추가 정보를 추가해야 할 수도 있습니다. 이에 대한 스타일을 만들어 보겠습니다.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
fencedCodeWithInfo.Font.Name = "Courier New";
fencedCodeWithInfo.Font.Size = 10;
fencedCodeWithInfo.ParagraphFormat.LeftIndent = 20;
fencedCodeWithInfo.ParagraphFormat.RightIndent = 20;
fencedCodeWithInfo.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## 6단계: 정보 문자열이 포함된 분리 코드를 문서에 추가

이제 C# 코드임을 나타내기 위해 정보 문자열이 포함된 분리된 코드 블록을 추가해 보겠습니다.

```csharp
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code block with info string - C#");
```

## 결론

축하해요! 방금 Aspose.Words for .NET을 사용하여 Word 문서에 정보 문자열이 포함된 울타리 코드 블록과 울타리 코드를 추가했습니다. 이것은 빙산의 일각에 불과합니다. Aspose.Words를 사용하면 문서 처리를 새로운 차원으로 자동화하고 향상할 수 있습니다. 계속 탐색하고 즐거운 코딩을 즐겨보세요!

## FAQ

### .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 프로그래밍 방식으로 Word 문서를 생성, 조작 및 변환할 수 있는 강력한 라이브러리입니다.

### Aspose.Words를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Words는 주로 .NET 언어를 지원하지만 Java, Python 및 기타 언어에 사용할 수 있는 버전도 있습니다.

### Aspose.Words는 무료로 사용할 수 있나요?
 Aspose.Words는 상용 제품이지만 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/)그 특징을 탐구합니다.

### Aspose.Words에 대한 지원은 어떻게 받을 수 있나요?
 Aspose 커뮤니티와 개발자로부터 지원을 받을 수 있습니다[여기](https://forum.aspose.com/c/words/8).

### Aspose.Words는 어떤 다른 기능을 제공합니까?
Aspose.Words는 문서 변환, 템플릿 기반 문서 생성, 보고 등을 포함한 광범위한 기능을 제공합니다.