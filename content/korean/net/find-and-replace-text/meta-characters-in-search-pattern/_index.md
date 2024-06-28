---
title: 검색 패턴의 메타 문자
linktitle: 검색 패턴의 메타 문자
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 검색 패턴에서 메타 문자를 사용하여 Word 문서를 조작하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/find-and-replace-text/meta-characters-in-search-pattern/
---
이 기사에서는 위의 C# 소스 코드를 탐색하여 Aspose.Words for .NET 라이브러리에서 검색 패턴의 메타 문자 기능을 사용하는 방법을 이해합니다. 이 기능을 사용하면 특수 메타 문자를 사용하여 Word 문서에서 고급 검색 및 바꾸기를 수행할 수 있습니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 새 문서 만들기

 검색 패턴에서 메타 문자를 사용하기 전에 Aspose.Words for .NET을 사용하여 새 문서를 만들어야 합니다. 이는 인스턴스화를 통해 수행할 수 있습니다.`Document` 물체:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 2단계: 문서에 텍스트 삽입

 문서가 있으면 다음을 사용하여 텍스트를 삽입할 수 있습니다.`DocumentBuilder` 물체. 이 예에서는`Writeln` 그리고`Write` 두 줄의 텍스트를 삽입하는 방법:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## 3단계: 메타 문자로 텍스트 찾기 및 바꾸기

 이제 우리는`Range.Replace` 특수 메타 문자가 포함된 검색 패턴을 사용하여 텍스트를 검색하고 바꾸는 기능입니다. 이 예에서는 "This is line 1&pThis is line 2"라는 문구를 다음을 사용하여 "This line is replacement"로 바꿉니다.`&p` 단락 나누기를 나타내는 메타 문자:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## 4단계: 문서에 페이지 나누기 삽입

 다른 메타 문자의 사용을 설명하기 위해 다음을 사용하여 문서에 페이지 나누기를 삽입합니다.`InsertBreak` 방법`BreakType.PageBreak` 매개변수. 먼저 커서를`DocumentBuilder` 문서 끝에 페이지 나누기와 새 텍스트 줄을 삽입합니다.

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## 5단계: 다른 메타문자를 찾아 바꾸기

 이제 다른 검색을 수행하고`&m` 페이지 나누기를 나타내는 메타문자입니다. "이것은 1행입니다&m이것은 2행입니다"라는 문구를 "페이지 나누기가 새 텍스트로 대체됩니다."로 대체합니다. :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## 6단계: 편집된 문서 저장

마지막으로 수정된 문서를 다음을 사용하여 지정된 디렉터리에 저장합니다.`Save` 방법:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### .NET용 Aspose.Words를 사용하는 검색 패턴의 메타 문자에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 검색 패턴에서 메타문자 사용을 보여주는 전체 샘플 소스 코드입니다.

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## 결론

이 기사에서는 .NET용 Aspose.Words의 검색 패턴에서 메타 문자를 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 문서 작성, 텍스트 삽입, 특수 메타 문자를 사용한 검색 및 바꾸기 수행, 페이지 나누기 삽입, 편집된 문서 저장 등의 단계별 지침을 따랐습니다.

### FAQ

#### Q: Aspose.Words for .NET의 검색 패턴의 메타 문자 기능은 무엇입니까?

A: Aspose.Words for .NET의 검색 패턴의 메타 문자 기능을 사용하면 특수 메타 문자를 사용하여 Word 문서에서 고급 검색 및 바꾸기를 수행할 수 있습니다. 이러한 메타 문자를 사용하면 검색 패턴에서 단락 나누기, 섹션 나누기, 페이지 나누기 및 기타 특수 요소를 나타낼 수 있습니다.

#### Q: .NET용 Aspose.Words에서 새 문서를 만드는 방법은 무엇입니까?

 A: 검색 템플릿에서 메타 문자를 사용하기 전에 Aspose.Words for .NET을 사용하여 새 문서를 만들어야 합니다. 이는 인스턴스화를 통해 수행할 수 있습니다.`Document` 물체. 다음은 새 문서를 생성하는 샘플 코드입니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Q: .NET용 Aspose.Words를 사용하여 문서에 텍스트를 삽입하는 방법은 무엇입니까?

 A: 문서가 있으면 다음을 사용하여 텍스트를 삽입할 수 있습니다.`DocumentBuilder` 물체. 이 예에서는`Writeln` 그리고`Write` 두 줄의 텍스트를 삽입하는 방법:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### Q: Aspose.Words for .NET을 사용하여 문서에서 텍스트를 검색하고 메타 문자로 바꾸는 방법은 무엇입니까?

 A: 텍스트를 검색하고 메타 문자로 바꾸려면 다음을 사용할 수 있습니다.`Range.Replace` 방법. 이 예에서는 "This is line 1&pThis is line 2"라는 문구를 다음을 사용하여 "This line is replacement"로 바꿉니다.`&p` 단락 나누기를 나타내는 메타 문자:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### Q: .NET용 Aspose.Words를 사용하여 문서에 페이지 나누기를 삽입하는 방법은 무엇입니까?

A: 다른 메타 문자의 사용을 설명하기 위해 다음을 사용하여 문서에 페이지 나누기를 삽입하겠습니다.`InsertBreak` 방법`BreakType.PageBreak` 매개변수. 먼저 커서를`DocumentBuilder` 문서 끝에 페이지 나누기와 새 텍스트 줄을 삽입합니다.

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### Q: .NET용 Aspose.Words를 사용하여 문서에서 다른 메타 문자를 검색하고 바꾸는 방법은 무엇입니까?

 A: 이제 다른 검색을 수행하고`&m` 페이지 나누기를 나타내는 메타문자입니다. "이것은 1행입니다&m이것은 2행입니다"라는 문구를 "페이지 나누기가 새 텍스트로 대체됩니다."로 대체합니다. :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### Q: .NET용 Aspose.Words에서 편집된 문서를 어떻게 저장합니까?

 답변: 문서를 변경한 후에는 다음을 사용하여 지정된 디렉터리에 저장할 수 있습니다.`Save` 방법:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```