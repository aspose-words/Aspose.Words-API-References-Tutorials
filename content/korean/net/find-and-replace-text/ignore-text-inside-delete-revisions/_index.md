---
title: 삭제 개정 내 텍스트 무시
linktitle: 삭제 개정 내 텍스트 무시
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words의 "수정본 내부의 텍스트 무시" 기능을 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 .NET용 Aspose.Words 라이브러리의 "수정본 내부 텍스트 무시" 기능을 사용하는 방법을 이해합니다. 이 기능은 문서로 단어를 처리할 때 삭제 개정 안의 텍스트를 무시하려는 경우에 유용합니다.

## .NET 라이브러리용 Aspose.Words 개요

코드 세부 사항을 살펴보기 전에 Aspose.Words for .NET 라이브러리에 대해 간략하게 소개하겠습니다. .NET 응용 프로그램에서 Word 문서를 생성, 수정 및 변환할 수 있는 강력한 라이브러리입니다. 개정 관리를 포함하여 문서의 단어 처리를 위한 다양한 고급 기능을 제공합니다.

## "수정본 삭제 안의 텍스트 무시" 기능 이해

.NET용 Aspose.Words의 "삭제 개정 내 텍스트 무시" 기능을 사용하면 텍스트 찾기 및 바꾸기와 같은 특정 작업 중에 삭제 개정 내 텍스트를 무시해야 하는지 여부를 지정할 수 있습니다. 이 기능이 활성화되면 수정본 내에서 삭제된 텍스트는 작업 중에 고려되지 않습니다.

## 1단계: Aspose.Words for .NET을 사용하여 새 문서 만들기

 문서의 텍스트 조작을 시작하기 전에 Aspose.Words for .NET을 사용하여 새 문서를 만들어야 합니다. 인스턴스화를 통해 수행할 수 있습니다.`Document` 물체:

```csharp
Document doc = new Document();
```

## 2단계: 수정되지 않은 텍스트를 문서에 삽입하기

 문서가 있으면 검토되지 않은 텍스트를 삽입할 수 있습니다.`DocumentBuilder` 물체. 예를 들어, "삭제된 텍스트"라는 텍스트를 삽입하려면 다음을 사용할 수 있습니다.`Writeln` 그리고`Write` 행동 양식:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## 3단계: 수정 내용 추적을 통해 단락 제거

"수정본 삭제 안의 텍스트 무시" 기능의 사용을 설명하기 위해 수정본 추적을 사용하여 문서에서 단락을 삭제하겠습니다. 이를 통해 이 기능이 후속 작업에 어떤 영향을 미치는지 확인할 수 있습니다.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## 4단계: "수정본 삭제 안의 텍스트 무시" 기능 적용

 이제 단락을 삭제하여 문서를 준비했으므로 다음을 사용하여 "수정본 삭제 안의 텍스트 무시" 기능을 활성화할 수 있습니다.`FindReplaceOptions` 물체. 우리는`IgnoreDeleted`재산`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## 5단계: 찾기 및 바꾸기에 정규식 사용

문서 텍스트에 대한 검색 및 바꾸기 작업을 수행하기 위해 정규식을 사용합니다. 이 예에서는 문자 "e"가 나타나는 모든 항목을 검색하고 이를 별표 "로 바꿉니다.* ". .그물`Regex` 클래스는 다음과 같이 사용됩니다.

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## 6단계: 수정된 문서 출력 표시

 검색 및 바꾸기를 적용한 후 다음을 사용하여 문서의 변경된 내용을 표시할 수 있습니다.`GetText` 방법:

```csharp
Console.WriteLine(doc.GetText());
```

## 7단계: 삭제된 텍스트를 포함하도록 옵션 수정

 출력 결과에 삭제된 텍스트를 포함하려면 삭제된 텍스트를 무시하지 않도록 옵션을 변경할 수 있습니다. 이를 위해 우리는`IgnoreDeleted`재산`false`:

```csharp
options. IgnoreDeleted = false;
```

## 8단계: 텍스트가 삭제된 수정된 문서 출력

옵션을 변경한 후 검색 및 바꾸기를 다시 수행하여 삭제된 텍스트가 포함된 결과를 얻을 수 있습니다.

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### .NET용 Aspose.Words를 사용하여 삭제 개정 내에서 텍스트 무시에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words와 함께 "수정본 내부의 텍스트 무시" 기능 사용을 보여주는 전체 샘플 소스 코드입니다.

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// 수정되지 않은 텍스트를 삽입합니다.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// 수정본을 추적하여 첫 번째 단락을 제거합니다.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## 결론

이 기사에서는 .NET용 Aspose.Words의 "수정본 내부 텍스트 무시" 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 탐색했습니다. 이 기능은 문서를 조작할 때 삭제 개정 내 텍스트를 무시하는 데 유용합니다. 문서 작성, 텍스트 삽입, 수정본 추적을 통해 단락 삭제, "수정본 삭제 안의 텍스트 무시" 기능 적용, 찾기 및 바꾸기 작업 수행에 대한 단계별 가이드를 따랐습니다.

### FAQ

#### Q: Aspose.Words for .NET의 "수정본 내부 텍스트 무시" 기능은 무엇입니까?

A: Aspose.Words for .NET의 "삭제 개정 내 텍스트 무시" 기능을 사용하면 텍스트 찾기 및 바꾸기와 같은 특정 작업 중에 삭제 개정 내 텍스트를 무시해야 하는지 여부를 지정할 수 있습니다. 이 기능이 활성화되면 수정본 내에서 삭제된 텍스트는 작업 중에 고려되지 않습니다.

#### Q: .NET용 Aspose.Words가 무엇인가요?

A: Aspose.Words for .NET은 Word 문서를 생성, 편집 및 .NET 애플리케이션으로 변환하기 위한 강력한 라이브러리입니다. 개정 관리를 포함하여 문서의 단어 처리를 위한 다양한 고급 기능을 제공합니다.

#### Q: .NET용 Aspose.Words에서 새 문서를 만드는 방법은 무엇입니까?

 A: 문서의 텍스트 조작을 시작하기 전에 Aspose.Words for .NET을 사용하여 새 문서를 만들어야 합니다. 이는 인스턴스화를 통해 수행할 수 있습니다.`Document` 물체. 다음은 새 문서를 생성하는 샘플 코드입니다.

```csharp
Document doc = new Document();
```

#### Q: .NET용 Aspose.Words를 사용하여 편집되지 않은 텍스트를 문서에 삽입하는 방법은 무엇입니까?

 A: 문서가 있으면 다음을 사용하여 검토되지 않은 텍스트를 삽입할 수 있습니다.`DocumentBuilder` 물체. 예를 들어, "삭제된 텍스트"라는 텍스트를 삽입하려면`Writeln` 그리고`Write` 행동 양식:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### Q: .NET용 Aspose.Words에서 개정 추적 기능이 있는 단락을 어떻게 삭제합니까?

A: "수정본 삭제 안의 텍스트 무시" 기능의 사용을 설명하기 위해 수정본 추적을 사용하여 문서에서 단락을 삭제하겠습니다. 이를 통해 이 기능이 후속 작업에 어떤 영향을 미치는지 확인할 수 있습니다.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### Q: .NET용 Aspose.Words에서 "수정본 내부의 텍스트 무시" 기능을 활성화하는 방법은 무엇입니까?

 A: 이제 단락을 삭제하여 문서를 준비했으므로 다음을 사용하여 "수정본 삭제 안의 텍스트 무시" 기능을 활성화할 수 있습니다.`FindReplaceOptions` 물체. 우리는`IgnoreDeleted`재산`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### Q: Aspose.Words for .NET에서 정규식을 사용하여 검색하고 바꾸는 방법은 무엇입니까?

A: 문서 텍스트에 대한 검색 및 바꾸기 작업을 수행하려면 정규식을 사용합니다. 이 예에서는 문자 "e"가 나타나는 모든 항목을 검색하고 이를 별표 "로 바꿉니다.* ". 우리는 .NET을 사용할 것입니다`Regex` 이에 대한 수업 :

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q: Aspose.Words for .NET에서 변경된 문서 내용을 보는 방법은 무엇입니까?

A: 검색 및 바꾸기를 적용한 후 다음을 사용하여 문서의 변경된 내용을 표시할 수 있습니다.`GetText` 방법:

```csharp
Console.WriteLine(doc.GetText());
```

#### Q: .NET용 Aspose.Words의 출력 결과에 삭제된 텍스트를 포함하는 방법은 무엇입니까?

 A: 삭제된 텍스트를 출력 결과에 포함하려면 삭제된 텍스트를 무시하지 않도록 옵션을 변경할 수 있습니다. 이를 위해 다음을 설정하겠습니다.`IgnoreDeleted`재산`false`:

```csharp
options. IgnoreDeleted = false;
```

#### Q: Aspose.Words for .NET에서 편집된 문서와 삭제된 텍스트를 표시하는 방법은 무엇입니까?

A: 옵션을 변경한 후 새로운 검색 및 바꾸기를 수행하여 삭제된 텍스트가 포함된 결과를 얻을 수 있습니다.

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
