---
title: 문서 작성기 없이 ASKField 삽입
linktitle: 문서 작성기 없이 ASKField 삽입
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에 ASK 필드를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-askfield-with-out-document-builder/
---

다음은 .NET용 Aspose.Words의 "DocumentBuilder 없이 ASK 필드 삽입" 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

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

## 3단계: ASK 필드 삽입

 우리는`AppendField()` 단락에 ASK 필드를 삽입하는 방법입니다.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

그런 다음 원하는 값을 지정하여 ASK 필드의 다양한 속성을 구성합니다.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 마지막으로 우리는`Update()` 필드를 업데이트하는 방법입니다.

```csharp
field. Update();
```

### .NET용 Aspose.Words를 사용하여 DocumentBuilder 없이 ASK 필드를 삽입하기 위한 소스 코드의 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 생성.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// ASK 필드를 삽입합니다.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

이 예에서는 새 문서를 만들고, DocumentBuilder를 사용하지 않고 ASK 필드를 삽입하고, 필드의 다양한 속성을 구성하고, 지정된 파일 이름으로 문서를 저장했습니다.

이것으로 .NET용 Aspose.Words와 함께 "DocumentBuilder 없이 ASK 필드 삽입" 기능을 사용하는 방법에 대한 가이드를 마칩니다.

### FAQ

#### Q: Aspose.Words의 ASK 필드는 무엇입니까?

A: Aspose.Words의 ASK 필드는 문서를 열 때 사용자에게 질문을 하는 데 사용됩니다. 이는 사용자마다 다를 수 있는 특정 정보나 피드백을 요청하는 데 자주 사용됩니다.

#### Q: Aspose.Words에서 Document Builder를 사용하지 않고 Word 문서에 ASK 필드를 삽입하는 방법은 무엇입니까?

A: Aspose.Words에서 Document Builder를 사용하지 않고 Word 문서에 ASK 필드를 삽입하려면 다음 단계를 따르세요.

1. Aspose.Words.Fields 네임스페이스에서 Document 및 Field 클래스를 가져옵니다.
2. 기존 문서를 로드하여 Document 인스턴스를 만듭니다.
3. 질문 이름을 지정하여 ASK 필드를 삽입하려면 InsertField 메서드를 사용하세요.
4. 문서를 저장합니다.

#### Q: Word 문서의 ASK 필드에 대한 사용자 응답을 얻으려면 어떻게 해야 합니까?

A: Word 문서의 ASK 필드에 대한 사용자 응답을 얻으려면 Document 클래스에서 사용할 수 있는 GetFieldNames 메서드를 사용할 수 있습니다. 이 메서드는 문서에 있는 필드 이름 목록을 반환합니다. 그런 다음 ASK 필드 이름이 목록에 있는지 확인하고 관련 응답을 검색할 수 있습니다.

#### Q: ASK 필드를 사용하여 사용자에게 추가 정보를 요청할 수 있습니까?

A: 예, ASK 필드를 사용하여 사용자에게 여러 정보를 요청할 수 있습니다. 각각 다른 질문이 포함된 여러 개의 ASK 필드를 문서에 삽입할 수 있습니다. 문서가 열리면 사용자에게 해당 답변을 묻는 메시지가 표시됩니다.