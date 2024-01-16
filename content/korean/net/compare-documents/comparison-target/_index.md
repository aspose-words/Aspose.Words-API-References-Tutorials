---
title: Word 문서의 비교 대상
linktitle: Word 문서의 비교 대상
second_title: Aspose.Words 문서 처리 API
description: 문서를 비교하고 변경 사항이 포함된 새 문서를 생성할 수 있는 Aspose.Words for .NET의 Word 문서 기능 비교 대상에 대해 알아보세요.
type: docs
weight: 10
url: /ko/net/compare-documents/comparison-target/
---
다음은 Aspose.Words for .NET의 워드 문서 기능에서 비교 대상을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다.

## 1단계: 소개

.NET용 Aspose.Words의 비교 대상 기능을 사용하면 두 문서를 비교하고 대상 문서에 대한 변경 사항이 포함된 새 문서를 생성할 수 있습니다. 이는 문서의 서로 다른 버전 간에 변경된 내용을 추적하는 데 유용할 수 있습니다.

## 2단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하려면 개발 환경을 설정해야 합니다. Aspose.Words 라이브러리가 설치되어 있고 코드를 포함할 적절한 C# 프로젝트가 있는지 확인하세요.

## 3단계: 필수 어셈블리 추가

Aspose.Words for .NET의 비교 대상 기능을 사용하려면 프로젝트에 필요한 어셈블리를 추가해야 합니다. 프로젝트에 Aspose.Words에 대한 적절한 참조가 있는지 확인하세요.

```csharp
using Aspose.Words;
```

## 4단계: 문서 초기화

이 단계에서는 비교를 위해 두 문서를 초기화합니다. 문서가 있는 디렉터리 경로와 소스 문서의 이름을 지정해야 합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 비교할 문서 A를 초기화합니다.
Document docA = new Document(dataDir + "DocumentA.docx");

// 문서 A를 복제하여 문서 B와 동일한 복사본을 만듭니다.
Document docB = docA.Clone();
```

## 5단계: 비교 옵션 구성

이 단계에서는 비교 동작을 지정하기 위해 비교 옵션을 구성합니다. 옵션에는 서식을 무시하는 기능과 Microsoft Word의 "문서 비교" 대화 상자에 있는 "변경 사항 표시" 옵션인 비교 대상이 포함됩니다.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## 6단계: 문서 비교

이제 문서를 비교하고 새 문서에서 결과를 생성하겠습니다.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 그만큼`Compare`방법은 문서 A를 문서 B와 비교하고 변경 사항을 문서 A에 저장합니다. 참조용으로 사용자 이름과 비교 날짜를 지정할 수 있습니다.

### .NET용 Aspose.Words를 사용하는 비교 대상의 샘플 소스 코드


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// "문서 비교" 대화 상자의 Microsoft Word "변경 내용 표시" 옵션과 관련됩니다.
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## 결론

이 기사에서는 .NET용 Aspose.Words의 diff 대상 기능을 살펴보았습니다. 이 기능을 사용하면 두 문서를 비교하고 변경 사항이 포함된 새 문서를 생성할 수 있습니다. 이 지식을 사용하여 문서의 여러 버전 간의 변경 사항을 추적할 수 있습니다.

### FAQ

#### Q: Aspose.Words for .NET에서 비교 대상을 사용하는 목적은 무엇입니까?

A: Aspose.Words for .NET의 비교 대상을 사용하면 두 문서를 비교하고 대상 문서에 대한 변경 사항이 포함된 새 문서를 생성할 수 있습니다. 이 기능은 문서의 여러 버전 간의 변경 사항을 추적하고 별도 문서의 차이점을 시각화하는 데 유용합니다.

#### Q: .NET용 Aspose.Words에서 비교 대상을 어떻게 사용합니까?

A: .NET용 Aspose.Words에서 비교 대상을 사용하려면 다음 단계를 따르세요.
1. Aspose.Words 라이브러리를 사용하여 개발 환경을 설정하세요.
2. Aspose.Words를 참조하여 프로젝트에 필요한 어셈블리를 추가합니다.
3.  비교하고 싶은 문서를 초기화하세요.`Document` 수업이나`DocumentBuilder` 수업.
4.  다음을 생성하여 비교 옵션을 구성합니다.`CompareOptions` 다음과 같은 객체 및 설정 속성`IgnoreFormatting` 그리고`Target` (예:`ComparisonTargetType.New` 비교 대상의 경우).
5.  사용`Compare` 한 문서에 대한 메서드를 사용하여 다른 문서와`CompareOptions` 매개변수로 개체를 사용합니다. 이 방법은 문서를 비교하고 첫 번째 문서의 변경 사항을 저장합니다.

####  Q: 이 프로그램의 목적은 무엇입니까?`Target` property in the `CompareOptions` class?

 답:`Target` 에 있는 재산`CompareOptions` 클래스를 사용하면 Microsoft Word의 "문서 비교" 대화 상자에 있는 "변경 내용 표시" 옵션과 유사한 비교 대상을 지정할 수 있습니다. 목표는 다음과 같이 설정할 수 있습니다.`ComparisonTargetType.New` 새 문서의 변경 사항을 표시하려면`ComparisonTargetType.Current` 현재 문서의 변경 사항을 표시하거나`ComparisonTargetType.Formatting` 서식 변경 사항만 표시합니다.