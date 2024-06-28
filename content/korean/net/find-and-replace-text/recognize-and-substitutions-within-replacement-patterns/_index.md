---
title: 대체 패턴 내에서 인식 및 대체
linktitle: 대체 패턴 내에서 인식 및 대체
second_title: Aspose.Words 문서 처리 API
description: Word 문서를 조작하기 위해 .NET용 Aspose.Words에서 인식 및 대체와 함께 대체 패턴을 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 .NET 라이브러리용 Aspose.Words에서 대체 패턴 내 인식 및 대체 기능을 사용하는 방법을 이해합니다. 이 기능은 복잡한 검색 패턴을 인식하고 문서 조작 중에 캡처된 그룹을 기반으로 대체를 수행하는 데 도움이 됩니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 새 문서 만들기

대체 패턴에서 일치 항목과 대체 항목을 사용하기 전에 Aspose.Words for .NET을 사용하여 새 문서를 만들어야 합니다. 이는 인스턴스화를 통해 수행할 수 있습니다.`Document` 물체:

```csharp
Document doc = new Document();
```

## 2단계: 문서에 텍스트 삽입

 문서가 있으면 다음을 사용하여 텍스트를 삽입할 수 있습니다.`DocumentBuilder` 물체. 이 예에서는`Write` "Jason이 Paul에게 돈을 줍니다."라는 문구를 삽입하는 방법입니다. :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## 3단계: 대체 패턴의 인식 및 대체

 이제 우리는`Range.Replace` 특정 패턴을 인식하기 위해 정규식을 사용하여 텍스트 검색 및 바꾸기를 수행하는 기능입니다. 이 예에서는 정규 표현식을 사용합니다.`([A-z]+) gives money to ([A-z]+)` 누군가가 다른 사람에게 돈을 주는 문장을 인식합니다. 교체 패턴을 사용합니다`$2 takes money from $1` 역할을 바꾸어 대체를 수행합니다. 사용`$1` 그리고`$2` 정규식으로 캡처된 그룹을 나타냅니다.

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### .NET용 Aspose.Words를 사용하여 대체 패턴 내에서 인식 및 대체를 위한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용한 대체 패턴에서 일치 및 대체 사용을 설명하는 전체 예제 소스 코드입니다.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## 결론

이 기사에서는 .NET용 Aspose.Words의 대체 패턴 내 인식 및 대체 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 탐색했습니다. 우리는 단계별 가이드에 따라 문서를 생성하고, 텍스트를 삽입하고, 캡처된 그룹을 기반으로 정규식과 대체 패턴을 사용하여 검색 및 바꾸기를 수행하고, 문서를 조작했습니다.

### FAQ

#### Q: Aspose.Words for .NET의 "대체 패턴 내 인식 및 대체" 기능은 무엇입니까?

A: Aspose.Words for .NET의 "대체 패턴 내 인식 및 대체" 기능을 사용하면 정규식을 사용하여 복잡한 검색 패턴을 인식하고 문서 조작 중에 캡처된 그룹을 기반으로 대체를 수행할 수 있습니다. 교체 패턴에서 캡처된 그룹을 참조하여 일치하는 텍스트를 동적으로 변환할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 새 문서를 어떻게 만들 수 있나요?

 A: .NET용 Aspose.Words를 사용하여 새 문서를 생성하려면`Document` 물체. 다음은 새 문서를 만드는 C# 코드의 예입니다.

```csharp
Document doc = new Document();
```

#### Q: .NET용 Aspose.Words를 사용하여 문서에 텍스트를 삽입하려면 어떻게 해야 합니까?

 A: 문서가 있으면 다음을 사용하여 텍스트를 삽입할 수 있습니다.`DocumentBuilder` 물체. 예를 들어, "Jason이 Paul에게 돈을 줍니다."라는 문구를 삽입하려면`Write` 방법:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### Q: Aspose.Words for .NET에서 정규식을 사용하여 텍스트 검색 및 바꾸기를 어떻게 수행할 수 있습니까?

 A: .NET용 Aspose.Words에서 정규식을 사용하여 텍스트 검색 및 바꾸기를 수행하려면 다음을 사용할 수 있습니다.`Range.Replace` 정규식 패턴과 함께 작동합니다. 당신은 만들 수 있습니다`Regex` 원하는 패턴으로 개체를 만들어 전달합니다.`Replace` 방법:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q: 텍스트 검색 중에 교체 패턴에서 캡처된 그룹을 사용하고 .NET용 Aspose.Words에서 교체하려면 어떻게 해야 합니까?

 A: 텍스트 검색 중에 교체 패턴에서 캡처된 그룹을 사용하고 .NET용 Aspose.Words에서 교체하려면`UseSubstitutions` 의 재산`FindReplaceOptions` 물체. 이를 통해 다음을 사용하여 캡처된 그룹을 참조할 수 있습니다.`$1`, `$2`등을 교체 패턴에서 사용합니다.

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q: 예제 소스 코드는 .NET용 Aspose.Words의 "대체 패턴 내 인식 및 대체" 기능에 대해 무엇을 보여줍니까?

A: 예제 소스 코드는 .NET용 Aspose.Words의 "대체 패턴 내 인식 및 대체" 기능의 사용을 보여줍니다. 문서를 만들고, 텍스트를 삽입하고, 정규식을 사용하여 텍스트 검색 및 바꾸기를 수행하고, 바꾸기 패턴에서 캡처된 그룹을 사용하여 일치하는 텍스트를 동적으로 변환하는 방법을 보여줍니다.

#### Q: .NET용 Aspose.Words에서 정규식 사용에 대한 추가 정보와 예제를 어디서 찾을 수 있나요?

A: Aspose.Words for .NET에서 정규식 사용에 대한 자세한 내용과 예를 보려면 다음을 참조하세요.[.NET API 참조용 Aspose.Words](https://reference.aspose.com/words/net/). 이 설명서는 Aspose.Words for .NET의 정규식 및 텍스트 조작과 관련된 다양한 시나리오에 대한 자세한 설명과 코드 예제를 제공합니다.

#### Q: 텍스트 검색 및 교체 중에 캡처된 그룹을 기반으로 문서의 다른 측면을 조작할 수 있습니까?

A: 예, 텍스트 검색 및 교체 중에 캡처된 그룹을 기반으로 문서의 다른 측면을 조작할 수 있습니다. 텍스트 대체를 수행하는 것 외에도 Aspose.Words for .NET에서 제공하는 다양한 API를 사용하여 캡처된 그룹을 기반으로 서식, 스타일, 문서 구조 및 기타 요소를 수정할 수 있습니다.

#### Q: Aspose.Words for .NET에서 정규식과 캡처된 그룹을 사용할 때 제한 사항이나 고려 사항이 있습니까?

A: 정규식과 캡처된 그룹은 .NET용 Aspose.Words에서 텍스트 검색 및 바꾸기를 위한 강력한 기능을 제공하지만 복잡성과 성능에 미치는 영향을 고려하는 것이 중요합니다. 매우 복잡한 정규식과 캡처된 그룹의 수가 많으면 성능에 영향을 미칠 수 있습니다. 효율적인 문서 조작을 보장하려면 특정 사용 사례에 맞게 정규식을 테스트하고 최적화하는 것이 좋습니다.

#### Q: 영어 이외의 언어로도 "대체 패턴 인식 및 대체" 기능을 사용할 수 있나요?

A: 예, Aspose.Words for .NET의 "대체 패턴 내에서 인식 및 대체" 기능은 영어 이외의 언어에서도 사용할 수 있습니다. 정규식은 언어에 구애받지 않으며 모든 언어의 특정 패턴과 일치하도록 제작될 수 있습니다. 원하는 언어와 인식하고 대체하려는 특정 텍스트 패턴에 맞게 정규식 패턴을 조정할 수 있습니다.