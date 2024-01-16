---
title: 문서 작성기 없이 고급 필드 삽입
linktitle: 문서 작성기 없이 고급 필드 삽입
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에 고급 필드를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

다음은 Aspose.Words for .NET의 "DocumentBuilder 없이 고급 필드 삽입" 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

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

## 3단계: 고급 필드 삽입

 우리는`AppendField()` 단락에 고급 필드를 삽입하는 방법입니다.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

그런 다음 원하는 값을 지정하여 고급 필드의 다양한 속성을 구성합니다.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 마지막으로 우리는`Update()` 필드를 업데이트하는 방법입니다.

```csharp
field. Update();
```

### .NET용 Aspose.Words를 사용하여 DocumentBuilder 없이 고급 필드를 삽입하기 위한 소스 코드의 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 생성.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// 고급 필드를 삽입합니다.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

이 예에서는 새 문서를 만들고, DocumentBuilder를 사용하지 않고 고급 필드를 삽입하고, 다양한 필드 속성을 구성하고, 지정된 파일 이름으로 문서를 저장했습니다.

이것으로 .NET용 Aspose.Words에서 "DocumentBuilder 없이 고급 필드 삽입" 기능을 사용하는 방법에 대한 가이드를 마칩니다.

### FAQ

#### Q: Aspose.Words의 고급 분야는 무엇인가요?

답변: Aspose.Words의 고급 필드는 Word 문서에서 계산을 수행하고 조건을 포함하며 복잡한 작업을 수행할 수 있는 특수한 유형의 필드입니다. 동적 및 사용자 정의 필드를 생성할 수 있는 뛰어난 유연성을 제공합니다.

#### Q: Aspose.Words에서 Document Builder를 사용하지 않고 Word 문서에 고급 필드를 삽입하는 방법은 무엇입니까?

A: Aspose.Words에서 문서 작성기를 사용하지 않고 Word 문서에 고급 필드를 삽입하려면 다음 단계를 따르세요.

1. Aspose.Words.Fields 네임스페이스에서 Document 및 Field 클래스를 가져옵니다.
2. 기존 문서를 로드하여 Document 인스턴스를 만듭니다.
3. 고급 필드 코드를 지정하여 고급 필드를 삽입하려면 InsertField 메서드를 사용합니다.
4. 문서를 저장합니다.

#### Q: Word 문서에서 고급 필드의 결과를 얻는 방법은 무엇입니까?

A: Word 문서에서 고급 필드의 결과를 얻으려면 Field 클래스에서 사용할 수 있는 Result 속성을 사용할 수 있습니다. 이 속성은 필드의 계산된 결과를 반환합니다.

#### Q: Word 문서에 고급 필드 수식을 삽입한 후 수정할 수 있나요?

A: 예, 고급 필드의 수식을 Word 문서에 삽입한 후 편집할 수 있습니다. Field 클래스의 FieldCode 속성에 액세스하고 수식 텍스트를 수정하여 수식을 업데이트하면 됩니다.