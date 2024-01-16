---
title: 작성자 필드 삽입
linktitle: 작성자 필드 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 AUTHOR 필드를 삽입하는 방법을 알아보세요. 문서를 개인화하려면 작성자 이름을 지정하세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-author-field/
---


다음은 .NET용 Aspose.Words의 "AUTHOR 필드 삽입" 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

## 1단계: 문서 디렉터리 설정

제공된 코드에서 문서의 디렉터리를 지정해야 합니다. "YOUR DOCUMENT DIRECTORY" 값을 문서 디렉토리에 대한 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 및 단락 만들기

새 문서를 만들고 첫 번째 단락을 가져오는 것부터 시작합니다.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 3단계: AUTHOR 필드 삽입

 우리는`AppendField()` AUTHOR 필드를 단락에 삽입하는 방법입니다.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 그런 다음 필드의`AuthorName` 작성자 이름을 지정하는 속성입니다.

```csharp
field. AuthorName = "Test1";
```

 마지막으로 우리는`Update()` 필드를 업데이트하는 방법입니다.

```csharp
field. Update();
```

### .NET용 Aspose.Words를 사용하여 AUTHOR 필드를 삽입하기 위한 소스 코드의 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 생성.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// AUTHOR 필드를 삽입합니다.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

이 예에서는 새 문서를 만들고, AUTHOR 필드를 삽입하고, 작성자 이름을 구성하고, 지정된 파일 이름으로 문서를 저장했습니다.

이것으로 .NET용 Aspose.Words에서 "AUTHOR 필드 삽입" 기능을 사용하는 방법에 대한 가이드를 마칩니다.

### FAQ

#### Q: Aspose.Words의 작성자 필드란 무엇입니까?

A: Aspose.Words의 작성자 필드는 Word 문서에 작성자 이름을 자동으로 삽입하고 업데이트하는 특수 필드입니다. 문서를 생성하거나 수정한 사람을 나타내는 데 자주 사용됩니다.

#### Q: Aspose.Words를 사용하여 Word 문서의 작성자 필드를 업데이트하는 방법은 무엇입니까?

A: Word 문서의 작성자 필드는 현재 작성자의 이름을 반영하도록 업데이트될 수 있습니다. 이를 위해 Document 클래스에서 사용할 수 있는 UpdateFields 메서드를 사용할 수 있습니다. 이 메서드는 작성자 필드를 포함하여 문서의 모든 필드를 업데이트합니다.

#### Q: Word 문서에서 작성자 필드의 형식을 사용자 정의할 수 있습니까?

A: 예, Word 문서에서 작성자 필드의 형식을 사용자 정의할 수 있습니다. 기본적으로 작성자 필드에는 작성자 이름만 표시됩니다. 그러나 Aspose.Words에서 사용할 수 있는 서식 옵션을 사용하여 수정 날짜 및 시간과 같은 추가 정보를 추가할 수 있습니다.

#### Q: 작성자 필드는 작성자 이름의 후속 변경 사항에 민감합니까?

A: 예, 작성자 필드는 작성자 이름의 후속 변경 사항에 민감합니다. 문서 속성에서 작성자 이름을 변경하면 문서 필드를 업데이트할 때 작성자 필드가 자동으로 새 이름으로 업데이트됩니다.