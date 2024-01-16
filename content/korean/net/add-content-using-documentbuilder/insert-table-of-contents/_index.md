---
title: Word 문서에 목차 삽입
linktitle: Word 문서에 목차 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 목차를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/insert-table-of-contents/
---
이 포괄적인 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 목차를 삽입하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 적절한 제목과 페이지 번호가 포함된 목차를 생성할 수 있습니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 새 문서 및 DocumentBuilder 만들기
시작하려면 Document 클래스를 사용하여 새 문서를 만들고 DocumentBuilder 객체를 초기화합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 목차 삽입
다음으로 DocumentBuilder 클래스의 InsertTableOfContents 메서드를 사용하여 목차를 삽입합니다. 메서드 내에서 필요한 형식 지정 옵션을 지정합니다.

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## 3단계: 문서 콘텐츠 추가
목차 삽입 후 실제 문서 내용을 추가합니다. StyleIdentifier를 사용하여 적절한 제목 스타일을 설정합니다.

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## 4단계: 목차 업데이트
새로 삽입된 목차는 처음에는 비어 있습니다. 이를 채우려면 문서의 필드를 업데이트하세요.

```csharp
doc.UpdateFields();
```

## 5단계: 문서 저장
목차를 삽입하고 필드를 업데이트한 후 Document 클래스의 Save 메서드를 사용하여 문서를 파일에 저장합니다.

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### .NET용 Aspose.Words를 사용하여 목차 삽입을 위한 소스 코드 예
다음은 .NET용 Aspose.Words를 사용하여 목차를 삽입하는 전체 소스 코드입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document 객체를 사용하여 DocumentBuilder 초기화
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 목차 삽입a
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// 두 번째 페이지에서 실제 문서 내용을 시작하세요.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// 새로 삽입된 목차는 처음에는 비어 있습니다.
// 문서의 필드를 업데이트하여 채워야 합니다.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## 결론

축하해요! Aspose.Words for .NET을 사용하여 Word 문서에 목차를 삽입하는 방법을 성공적으로 배웠습니다. 이 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 문서에 적합한 제목과 페이지 번호가 포함된 목차를 생성할 수 있습니다.

### Word 문서에 목차 삽입에 대한 FAQ

#### Q: 목차의 모양을 사용자 정의할 수 있나요?

 A: 예.`InsertTableOfContents` 방법. 매개변수를 사용하면 페이지 번호, 들여쓰기 및 기타 스타일을 제어할 수 있습니다.

#### Q: 목차에 특정 제목 수준을 포함하려면 어떻게 해야 합니까?

 A: 목차 내의 값을 조정하여 목차에 포함할 원하는 제목 수준을 지정할 수 있습니다.`InsertTableOfContents` 방법. 예를 들어,`"\\o \"1-3\""` 제목 수준 1~3이 포함됩니다.

#### Q: 문서 내용을 변경하면 목차를 자동으로 업데이트할 수 있나요?

 A: 예.`UpdateFields` 문서에 대한 방법. 이렇게 하면 제목 추가 또는 제거 등 문서 내용에 대한 모든 변경 사항이 목차에 반영됩니다.

#### Q: 목차의 제목 수준 스타일을 다르게 지정하려면 어떻게 해야 합니까?

 A: 각 제목 수준에 대해 서로 다른 단락 스타일을 사용하여 제목 수준의 스타일을 다르게 지정할 수 있습니다. 다르게 할당하여`StyleIdentifier` 가치를`ParagraphFormat` ~의`DocumentBuilder`를 사용하면 각 제목 수준에 대해 고유한 스타일을 만들 수 있습니다.

#### Q: 목차의 제목에 추가 서식을 추가할 수 있나요?

 A: 예, 목차의 제목에 글꼴 스타일, 색상, 기타 속성 등 추가 서식을 추가할 수 있습니다. 조정함으로써`Font` 의 속성`DocumentBuilder`을 사용하면 제목에 사용자 정의 서식을 적용할 수 있습니다.