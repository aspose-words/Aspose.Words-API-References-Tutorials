---
title: 글꼴 줄 간격 가져오기
linktitle: 글꼴 줄 간격 가져오기
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 줄 간격을 얻는 방법을 알아봅니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/get-font-line-spacing/
---
이 튜토리얼에서는 .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서에서 글꼴 줄 간격을 얻는 방법을 알려 드리겠습니다. 글꼴 줄 간격은 텍스트 줄 사이의 세로 간격을 정의합니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

## 전제 조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리

## 1단계: 새 문서 및 문서 생성기 만들기
 먼저, 인스턴스를 생성하여 새 문서를 만듭니다.`Document` 클래스와 문서 작성기를 인스턴스화하여`DocumentBuilder` 수업.

```csharp
// 새 문서 만들기
Document doc = new Document();

//문서 생성기 만들기
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 글꼴 구성
 다음으로, 다음을 설정하여 글꼴을 구성하겠습니다.`Name` 문서 생성기의 속성입니다.

```csharp
// 글꼴 구성
builder.Font.Name = "Calibri";
```

## 3단계: 문서에 텍스트 추가
이제 문서 생성기를 사용하여 서식이 지정된 텍스트를 문서에 추가하겠습니다.

```csharp
// 문서에 텍스트 추가
builder. Writen("qText");
```

## 4단계: 글꼴 줄 간격 가져오기
 이제 우리는`Font` 문서의 첫 번째 단락의 객체를 검색하고 해당 값을 검색합니다.`LineSpacing` 재산.

```csharp
// 글꼴의 줄 간격을 가져옵니다.
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### .NET용 Aspose.Words를 사용하여 글꼴 줄 간격 가져오기에 대한 샘플 소스 코드 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 줄 간격을 얻는 방법을 살펴보았습니다. 글꼴 줄 간격은 텍스트 줄 사이의 세로 간격을 제어하는 데 중요합니다. 이 기능을 자유롭게 사용하여 문서의 텍스트 모양을 사용자 정의하세요.

### FAQ

#### Q: Word 문서에서 특정 텍스트의 줄 간격을 어떻게 변경할 수 있나요?

A: Aspose.Words를 사용하면 Word 문서에서 특정 텍스트의 줄 간격을 쉽게 변경할 수 있습니다. API를 사용하여 원하는 텍스트를 선택하고 적절한 값을 지정하여 줄 사이의 간격을 조정하세요.

#### Q: Word 문서에서 줄 사이에 정확한 간격을 적용할 수 있나요?

A: 예, Aspose.Words를 사용하면 Word 문서의 줄 사이에 정확한 간격을 적용할 수 있습니다. API를 사용하여 줄 간격에 대한 정확한 값을 지정할 수 있습니다.

#### Q: 전체 Word 문서의 줄 간격을 조정하려면 어떻게 해야 합니까?

A: Aspose.Words를 사용하면 전체 Word 문서의 줄 간격을 쉽게 조정할 수 있습니다. API에서 제공하는 방법을 사용하여 전체 문서에 대해 원하는 줄 간격을 지정합니다.

#### Q: Aspose.Words는 여러 줄 간격을 지원합니까?

A: 예, Aspose.Words는 Word 문서에서 여러 줄 간격을 지원합니다. 텍스트 줄에 일반 간격의 1.5배 또는 2배 등 여러 간격을 설정할 수 있습니다.

#### Q: 줄 간격을 조정할 때 줄이 겹치는 문제를 방지하려면 어떻게 해야 합니까?

A: 줄 사이의 간격을 조정할 때 줄이 겹치는 문제를 방지하려면 적절한 간격 값을 선택해야 합니다. 또한 문서의 최종 렌더링을 테스트하여 텍스트를 읽을 수 있고 형식이 올바른지 확인하세요.