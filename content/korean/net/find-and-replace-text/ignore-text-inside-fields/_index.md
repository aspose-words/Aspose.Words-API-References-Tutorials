---
title: 필드 내부의 텍스트 무시
linktitle: 필드 내부의 텍스트 무시
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words의 "필드 내부 텍스트 무시" 기능을 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/find-and-replace-text/ignore-text-inside-fields/
---
이 기사에서는 위의 C# 소스 코드를 탐색하여 .NET용 Aspose.Words 라이브러리의 필드 내부 텍스트 무시 기능을 사용하는 방법을 이해합니다. 이 기능은 문서를 조작할 때 필드 내부의 텍스트를 무시하려는 경우에 유용합니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 새 문서 만들기

 필드 내부의 텍스트 조작을 시작하기 전에 Aspose.Words for .NET을 사용하여 새 문서를 만들어야 합니다. 이는 인스턴스화를 통해 수행할 수 있습니다.`Document` 물체:

```csharp
Document doc = new Document();
```

## 2단계: 내부에 텍스트가 있는 필드 삽입

 문서가 있으면 다음을 사용하여 문서 안에 텍스트가 포함된 필드를 삽입할 수 있습니다.`DocumentBuilder` 물체. 예를 들어, "Text in field" 텍스트와 함께 "INCLUDETEXT" 필드를 삽입하려면 다음을 사용할 수 있습니다.`InsertField` 방법:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## 3단계: 필드 내부 텍스트 무시 기능 사용

 후속 작업에서 필드 내부의 텍스트를 무시하려면`FindReplaceOptions` 객체를 설정하고`IgnoreFields`재산`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## 4단계: 검색 및 바꾸기에 정규식 사용

문서 텍스트에 대한 검색 및 바꾸기 작업을 수행하기 위해 정규식을 사용합니다. 이 예에서는 문자 "e"가 나타나는 모든 항목을 검색하고 이를 별표 "로 바꿉니다.* ". 우리는 .NET을 사용할 것입니다.`Regex` 이에 대한 수업 :

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 5단계: 수정된 문서 출력 보기

 검색 및 바꾸기를 적용한 후 다음을 사용하여 문서의 변경된 내용을 표시할 수 있습니다.`GetText` 방법:

```csharp
Console.WriteLine(doc.GetText());
```

## 6단계: 필드를 포함하도록 옵션 변경

 출력 결과의 필드 내부에 텍스트를 포함하면 필드를 무시하지 않도록 옵션을 변경할 수 있습니다. 이를 위해 우리는`IgnoreFields`재산`false`:

```csharp
options.IgnoreFields = false;
```

## 7단계: 수정된 문서를 필드와 함께 표시

옵션을 변경한 후 검색 및 바꾸기를 다시 수행하여 포함된 필드 내부의 텍스트로 결과를 얻을 수 있습니다.

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### .NET용 Aspose.Words를 사용하여 필드 내부 텍스트 무시에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words와 함께 필드 내부 텍스트 무시 기능을 사용하는 방법을 보여주는 전체 샘플 소스 코드입니다.

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// 내부에 텍스트가 있는 필드를 삽입합니다.
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## 결론

이 기사에서는 .NET용 Aspose.Words에서 필드 내부 텍스트 무시 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 우리는 단계별 가이드에 따라 문서를 만들고, 내부에 텍스트가 있는 필드를 삽입하고, 필드 내부의 텍스트 무시 기능을 사용하고, 정규식으로 검색 및 바꾸기 작업을 수행하고, 수정된 문서를 표시했습니다.

### FAQ

#### Q: .NET용 Aspose.Words의 "필드 내부 텍스트 무시" 기능은 무엇입니까?

A: Aspose.Words for .NET의 "필드 내부 텍스트 무시" 기능을 사용하면 텍스트 찾기 및 바꾸기와 같은 특정 작업 중에 필드 내부 텍스트를 무시해야 하는지 여부를 지정할 수 있습니다. 이 기능이 활성화되면 작업 중에 필드 내부의 텍스트가 고려되지 않습니다.

#### Q: Aspose.Words for .NET을 사용하여 새 문서를 어떻게 만들 수 있나요?

 A: .NET용 Aspose.Words를 사용하여 새 문서를 생성하려면`Document` 물체. 다음은 새 문서를 만드는 C# 코드의 예입니다.

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET을 사용하여 문서 내부에 텍스트가 있는 필드를 삽입하려면 어떻게 해야 합니까?

 A: 문서가 있으면 다음을 사용하여 내부에 텍스트가 있는 필드를 삽입할 수 있습니다.`DocumentBuilder` 물체. 예를 들어, "필드의 텍스트" 텍스트와 함께 "INCLUDETEXT" 필드를 삽입하려면 다음을 사용할 수 있습니다.`InsertField` 방법:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### Q: .NET용 Aspose.Words의 필드 내부 텍스트를 어떻게 무시할 수 있나요?

 A: 후속 작업 중에 필드 내부의 텍스트를 무시하려면`FindReplaceOptions` 객체를 설정하고`IgnoreFields`재산`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

#### Q: Aspose.Words for .NET에서 정규식을 사용하여 검색 및 바꾸기를 어떻게 수행할 수 있습니까?

 A: 정규식을 사용하여 문서 텍스트에 대한 검색 및 바꾸기 작업을 수행하려면 .NET을 사용할 수 있습니다.`Regex` 수업. 예를 들어 문자 "e"가 나타나는 모든 항목을 검색하고 이를 별표 "* ", 당신은 만들 수 있습니다`Regex` 개체를 사용하여`Replace` 방법:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q: .NET용 Aspose.Words에서 문서의 수정된 출력을 어떻게 볼 수 있나요?

 A: 검색 및 바꾸기 작업을 적용한 후 다음을 사용하여 문서의 변경된 내용을 볼 수 있습니다.`GetText` 방법:

```csharp
Console.WriteLine(doc.GetText());
```

#### Q: .NET용 Aspose.Words의 출력 결과에 필드를 어떻게 포함할 수 있나요?

 A: 출력 결과의 필드 내부에 텍스트를 포함하려면 필드를 무시하지 않도록 옵션을 변경할 수 있습니다. 이를 위해 다음을 설정할 수 있습니다.`IgnoreFields` 의 재산`FindReplaceOptions` 반대하다`false`:

```csharp
options.IgnoreFields = false;
```

#### Q: Aspose.Words for .NET의 필드와 함께 수정된 문서를 어떻게 표시할 수 있나요?

A: 필드를 포함하도록 옵션을 변경한 후 검색 및 바꾸기를 다시 수행하여 포함된 필드 내부의 텍스트로 결과를 얻을 수 있습니다.

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```