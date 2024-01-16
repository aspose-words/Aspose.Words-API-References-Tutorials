---
title: DOM을 사용하여 병합 필드 삽입
linktitle: DOM을 사용하여 병합 필드 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 사용자 정의 필드 병합 필드를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-merge-field-using-dom/
---

다음은 .NET용 Aspose.Words의 "필드 병합 필드 삽입" 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

## 1단계: 문서 디렉터리 설정

제공된 코드에서 문서의 디렉터리를 지정해야 합니다. "YOUR DOCUMENT DIRECTORY" 값을 문서 디렉토리에 대한 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 및 DocumentBuilder 만들기

새 문서를 만들고 DocumentBuilder를 초기화하는 것부터 시작합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 커서를 단락으로 이동

 우리는`MoveTo()` DocumentBuilder의 메서드를 사용하여 필드 병합 필드를 삽입하려는 단락으로 커서를 이동합니다.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## 4단계: 필드 병합 필드 삽입

 우리는 DocumentBuilder를 사용합니다.`InsertField()` 단락에 필드 병합 필드를 삽입하는 방법입니다.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

그런 다음 필드 이름, 필드 앞과 뒤의 텍스트, 세로 서식 옵션 등 적절한 옵션을 지정하여 필드 병합 필드 속성을 구성합니다.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 마지막으로 우리는`Update()` 필드를 업데이트하는 방법입니다.

```csharp
field. Update();
```

### .NET용 Aspose.Words를 사용하여 필드 병합 필드를 삽입하기 위한 샘플 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서와 DocumentBuilder를 만듭니다.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 커서를 단락으로 이동합니다.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// 필드 병합 필드를 삽입합니다.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// 필드를 업데이트합니다.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

이 예에서는 새 문서를 만들고 커서를 원하는 단락으로 이동한 다음 문서에 필드 병합 필드를 삽입했습니다.

### FAQ

#### Q: DOM과 함께 .NET용 Aspose.Words를 사용하여 Word 문서에 병합 필드를 삽입하려면 어떻게 해야 합니까?

A: DOM이 포함된 .NET용 Aspose.Words를 사용하여 Word 문서에 병합 필드를 삽입하려면 다음 단계를 따르세요.

1. 병합 필드를 삽입하려는 단락으로 이동합니다.
2.  만들기`FieldMergeField` 물체.
3. 필드 이름, 서식 옵션 등 병합 필드 속성을 설정합니다.
4.  다음을 사용하여 단락에 병합 필드를 추가합니다.`Paragraph.AppendChild` 방법.

#### Q: Aspose.Words for .NET에서 병합 필드에 대한 소스 데이터를 어떻게 지정할 수 있습니까?

A: Aspose.Words for .NET에서 병합 필드의 소스 데이터를 지정하려면 다음을 사용할 수 있습니다.`FieldMergeField.FieldName` CSV 파일, 데이터베이스 등과 같은 외부 데이터 소스의 필드 이름인 병합 필드 이름을 설정하는 방법입니다.`FieldMergeField.Text` 병합 필드 값을 직접 설정하는 방법입니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 병합 필드의 모양을 사용자 지정할 수 있나요?

 A: 예, Aspose.Words for .NET을 사용하여 Word 문서에서 병합 필드의 모양을 사용자 정의할 수 있습니다. 대소문자, 글꼴, 색상 등과 같은 서식 옵션을 속성을 사용하여 설정할 수 있습니다.`FieldMergeField` 물체.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에 병합 필드가 성공적으로 삽입되었는지 어떻게 확인할 수 있나요?

 A: 병합 필드가 성공적으로 삽입되었는지 확인하려면 문서 콘텐츠를 탐색하고 병합 필드 인스턴스를 검색하면 됩니다. 다음의 메서드와 속성을 사용할 수 있습니다.`Document` 문서의 단락, 필드 및 기타 요소에 액세스하기 위한 개체입니다.

#### Q: DOM을 사용하여 병합 필드를 삽입하면 .NET용 Aspose.Words를 사용하는 Word 문서 구조에 영향을 줍니까?

A: DOM을 사용하여 병합 필드를 삽입해도 Word 문서의 구조에 직접적인 영향을 미치지 않습니다. 그러나 문서 콘텐츠에 새 필드 요소를 추가합니다. 필요에 따라 기존 요소를 추가, 삭제, 수정하여 문서 구조를 조작할 수 있습니다.