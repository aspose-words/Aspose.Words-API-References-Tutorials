---
title: 문서 작성기 없이 필드 포함 텍스트 삽입
linktitle: 문서 작성기 없이 FieldIncludeText 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 FieldIncludeText 필드를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-field-include-text-without-document-builder/
---

다음은 .NET용 Aspose.Words의 "FieldIncludeText 필드 삽입" 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

## 1단계: 문서 디렉터리 설정

제공된 코드에서 문서의 디렉터리를 지정해야 합니다. "YOUR DOCUMENT DIRECTORY" 값을 문서 디렉토리에 대한 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 및 단락 만들기

새 문서를 만들고 단락을 초기화하는 것부터 시작합니다.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 3단계: FieldIncludeText 필드 삽입

 우리는`AppendField()` FieldIncludeText 필드를 단락에 삽입하는 방법입니다.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

그런 다음 책갈피 이름과 소스 파일 이름을 지정하여 FieldIncludeText 필드의 속성을 구성합니다.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

다음으로 문서 본문에 단락을 추가합니다.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 마지막으로 우리는`Update()` 필드를 업데이트하는 방법입니다.

```csharp
fieldIncludeText.Update();
```

### .NET용 Aspose.Words를 사용하여 FieldIncludeText 필드를 삽입하기 위한 소스 코드 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서와 단락을 만듭니다.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// FieldIncludeText 필드를 삽입합니다.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

이 예에서는 새 문서를 만들고, 단락을 초기화하고, 책갈피 이름과 소스 파일 이름을 지정하는 FieldIncludeTexten을 삽입하고, 지정된 파일 이름으로 문서를 저장했습니다.

이것으로 .NET용 Aspose.Words와 함께 "FieldIncludeText 삽입" 기능을 사용하는 방법에 대한 가이드를 마칩니다.

### FAQ

#### Q: Aspose.Words for .NET에서 텍스트 포함 필드에 대한 소스 파일을 어떻게 지정할 수 있습니까?

 A: .NET용 Aspose.Words의 텍스트 포함 필드에 대한 소스 파일을 지정하려면 다음을 사용할 수 있습니다.`FieldIncludeText.SourceFullName`소스 파일의 전체 경로를 설정하는 속성입니다. 소스 파일에 액세스할 수 있고 텍스트 포함 필드에 포함하려는 콘텐츠가 포함되어 있는지 확인하세요.

#### Q: Aspose.Words for .NET을 사용하여 텍스트 포함 필드에 매크로의 텍스트를 포함할 수 있나요?

 A: 예, Aspose.Words for .NET을 사용하면 텍스트 포함 필드에 매크로의 텍스트를 포함할 수 있습니다. 당신은 사용할 수 있습니다`FieldIncludeText.IncludeText` 필드에 내용이 포함되어야 하는 매크로의 이름을 지정하는 속성입니다.

#### Q: 문서 작성기 없이 텍스트 포함 필드를 삽입하면 Aspose.Words for .NET을 사용하는 Word 문서 구조에 영향을 미치나요?

A: 문서 작성기 없이 텍스트 포함 필드를 삽입해도 Word 문서의 구조에 직접적인 영향을 미치지 않습니다. 그러나 문서 콘텐츠에 새 필드 요소를 추가합니다. 필요에 따라 기존 요소를 추가, 삭제, 수정하여 문서 구조를 조작할 수 있습니다.

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서에서 텍스트 포함 필드의 모양을 사용자 지정할 수 있습니까?

A: 텍스트 포함 필드는 Word 문서의 모양을 직접 사용자 정의하지 않습니다. 그러나 .NET용 Aspose.Words에서 사용할 수 있는 단락 속성, 글꼴 속성 및 기타 서식 개체를 사용하여 포함된 텍스트의 서식을 지정할 수 있습니다.