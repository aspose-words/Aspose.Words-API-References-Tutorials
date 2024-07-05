---
title: Word 문서의 비교 세분성
linktitle: Word 문서의 비교 세분성
second_title: Aspose.Words 문서 처리 API
description: 문서를 문자별로 비교하고 변경 사항을 보고할 수 있는 .NET용 Aspose.Words의 단어 문서 기능에서 비교 세분성을 알아보세요.
type: docs
weight: 10
url: /ko/net/compare-documents/comparison-granularity/
---
다음은 Aspose.Words for .NET의 Word 문서의 세분성 비교 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다.

## 1단계: 소개

.NET용 Aspose.Words의 세분성 비교 기능을 사용하면 문자 수준에서 문서를 비교할 수 있습니다. 즉, 각 문자를 비교하고 이에 따라 변경 사항이 보고됩니다.

## 2단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하려면 개발 환경을 설정해야 합니다. Aspose.Words 라이브러리가 설치되어 있고 코드를 포함할 적절한 C# 프로젝트가 있는지 확인하세요.

## 3단계: 필수 어셈블리 추가

.NET용 Aspose.Words의 세분성 비교 기능을 사용하려면 프로젝트에 필요한 어셈블리를 추가해야 합니다. 프로젝트에 Aspose.Words에 대한 적절한 참조가 있는지 확인하세요.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## 4단계: 문서 작성

이 단계에서는 DocumentBuilder 클래스를 사용하여 두 개의 문서를 만듭니다. 이 문서는 비교에 사용됩니다.

```csharp
// 문서 A를 만듭니다.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// 문서 B를 생성합니다.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## 5단계: 비교 옵션 구성

이 단계에서는 비교 세분성을 지정하기 위한 비교 옵션을 구성합니다. 여기서는 문자 수준의 세분성을 사용합니다.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## 6단계: 문서 비교

이제 Document 클래스의 Compare 메서드를 사용하여 문서를 비교해 보겠습니다. 변경사항은 문서 A에 저장됩니다.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 그만큼`Compare`메서드는 문서 A를 문서 B와 비교하고 변경 사항을 문서 A에 저장합니다. 참조를 위해 작성자 이름과 비교 날짜를 지정할 수 있습니다.

## 결론

이 기사에서는 .NET용 Aspose.Words의 세분성 비교 기능을 살펴보았습니다. 이 기능을 사용하면 문자 수준에서 문서를 비교하고 변경 사항을 보고할 수 있습니다. 이 지식을 사용하여 프로젝트에서 상세한 문서 비교를 수행할 수 있습니다.

### .NET용 Aspose.Words를 사용하여 비교 세분성을 위한 샘플 소스 코드

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words의 비교 세분성 기능을 살펴보았습니다. 이 기능을 사용하면 문서를 비교할 때 세부 수준을 지정할 수 있습니다. 다양한 세분성 수준을 선택하면 특정 요구 사항에 따라 문자, 단어 또는 블록 수준에서 자세한 비교를 수행할 수 있습니다. Aspose.Words for .NET은 유연하고 강력한 문서 비교 기능을 제공하여 다양한 세부 수준으로 문서의 차이점을 쉽게 식별할 수 있습니다.

### FAQ

#### Q: Aspose.Words for .NET에서 비교 세분성을 사용하는 목적은 무엇입니까?

A: .NET용 Aspose.Words의 비교 세분성을 사용하면 문서를 비교할 때 세부 수준을 지정할 수 있습니다. 이 기능을 사용하면 문자 수준, 단어 수준, 블록 수준 등 다양한 수준에서 문서를 비교할 수 있습니다. 각 세부 수준은 비교 결과에 다양한 세부 수준을 제공합니다.

#### Q: .NET용 Aspose.Words에서 비교 세분성을 어떻게 사용합니까?

A: .NET용 Aspose.Words에서 비교 세분성을 사용하려면 다음 단계를 따르세요.
1. Aspose.Words 라이브러리를 사용하여 개발 환경을 설정하세요.
2. Aspose.Words를 참조하여 프로젝트에 필요한 어셈블리를 추가합니다.
3.  다음을 사용하여 비교하려는 문서를 만듭니다.`DocumentBuilder` 수업.
4.  다음을 생성하여 비교 옵션을 구성합니다.`CompareOptions` 개체 및 설정`Granularity` 속성을 원하는 수준으로 조정합니다(예:`Granularity.CharLevel` 캐릭터 레벨 비교용).
5.  사용`Compare`한 문서에 대한 메서드를 사용하여 다른 문서와`CompareOptions` 매개변수로 개체를 사용합니다. 이 방법은 지정된 세분성을 기준으로 문서를 비교하고 첫 번째 문서의 변경 사항을 저장합니다.

#### Q: .NET용 Aspose.Words에서 사용 가능한 비교 세분성 수준은 무엇입니까?

A: .NET용 Aspose.Words는 세 가지 수준의 비교 세분성을 제공합니다.
- `Granularity.CharLevel`: 문자 수준에서 문서를 비교합니다.
- `Granularity.WordLevel`: 단어 수준에서 문서를 비교합니다.
- `Granularity.BlockLevel`: 블록 수준에서 문서를 비교합니다.

#### Q: 문자 수준의 세분성으로 비교 결과를 해석하려면 어떻게 해야 합니까?

A: 문자 수준 세분성을 사용하면 비교 문서의 각 문자에 차이점이 있는지 분석됩니다. 비교 결과에는 추가, 삭제, 수정을 포함한 개별 캐릭터 수준의 변경 사항이 표시됩니다.