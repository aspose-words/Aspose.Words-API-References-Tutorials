---
title: Word 문서에서 병합 필드로 이동
linktitle: Word 문서에서 병합 필드로 이동
second_title: Aspose.Words 문서 처리 API
description: 단계별 가이드를 사용하여 .NET용 Aspose.Words의 Word 문서 기능에서 병합 필드로 이동을 구현하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/move-to-merge-field/
---
이 예에서는 .NET용 Aspose.Words의 Word 문서 기능에서 병합 필드로 이동을 살펴보겠습니다. Aspose.Words는 개발자가 프로그래밍 방식으로 Word 문서를 생성, 수정 및 변환할 수 있는 강력한 문서 조작 라이브러리입니다. 병합 필드로 이동 기능을 사용하면 문서 내의 병합 필드로 이동하여 다양한 작업을 수행할 수 있습니다.


## 소스코드를 단계별로 설명하기

.NET용 Aspose.Words를 사용하여 병합 필드로 이동 기능을 사용하는 방법을 이해하기 위해 소스 코드를 단계별로 살펴보겠습니다.

## 1단계: 문서 및 문서 작성기 초기화

먼저 Document 및 DocumentBuilder 객체를 초기화합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계 병합 필드 삽입 및 그 뒤에 텍스트 추가

DocumentBuilder 클래스의 InsertField 메서드를 사용하여 병합 필드를 삽입한 다음 그 뒤에 텍스트를 추가합니다.

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## 3단계: 빌더의 커서는 현재 문서 끝에 있습니다.

```csharp
Assert.Null(builder.CurrentNode);
```
## 4단계: 문서 작성기 커서를 병합 필드로 이동

문서 작성기 커서를 병합 필드로 이동하려면 DocumentBuilder 클래스의 MoveToField 메서드를 사용합니다.

```csharp
builder.MoveToField(field, true);
```

## 병합 필드 바로 뒤에 텍스트 추가

문서 작성기 커서가 병합 필드 안에 있으면 Write 메서드를 사용하여 바로 뒤에 텍스트를 추가할 수 있습니다.

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### .NET용 Aspose.Words를 사용하여 병합 필드로 이동에 대한 예제 소스 코드

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// DocumentBuilder를 사용하여 필드를 삽입하고 그 뒤에 텍스트를 추가합니다.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// 빌더의 커서는 현재 문서 끝에 있습니다.
Assert.Null(builder.CurrentNode);
// 빌더를 이와 같은 필드로 이동하여 필드 바로 뒤에 커서를 놓을 수 있습니다.
builder.MoveToField(field, true);

// 커서는 필드의 FieldEnd 노드를 지나서 위치에 있습니다. 이는 실제로 필드 내부에 있지 않음을 의미합니다.
// DocumentBuilder를 필드 내부로 이동하려면,
// DocumentBuilder.MoveTo() 메서드를 사용하여 필드의 FieldStart 또는 FieldSeparator 노드로 이동해야 합니다.
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## 결론

우리는 .NET용 Aspose.Words의 병합 필드로 이동 기능을 살펴보았습니다. DocumentBuilder 클래스를 사용하여 문서 내의 병합 필드를 탐색하고 해당 필드에 대한 작업을 수행하는 방법을 배웠습니다. 이 기능은 프로그래밍 방식으로 병합을 사용한 단어 처리에 유용합니다.

### Word 문서에서 병합 필드로 이동에 대한 FAQ

#### Q: .NET용 Aspose.Words의 병합 필드로 이동 기능의 목적은 무엇입니까?

A: .NET용 Aspose.Words의 병합 필드로 이동 기능을 사용하면 개발자는 Word 문서 내의 병합 필드를 탐색하고 프로그래밍 방식으로 다양한 작업을 수행할 수 있습니다. 병합 필드는 Word 문서에서 메일 병합 작업을 위해 사용되는 특수 자리 표시자입니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에 병합 필드를 삽입하려면 어떻게 해야 합니까?

대답: DocumentBuilder 클래스의 InsertField 메서드를 사용하여 문서에 병합 필드를 삽입할 수 있습니다. 병합 필드를 삽입한 후 Write 메서드를 사용하여 필드 앞이나 뒤에 텍스트 등의 콘텐츠를 추가할 수 있습니다.

#### Q: 문서 작성기 커서를 특정 병합 필드로 어떻게 이동합니까?

A: 문서 작성기 커서를 특정 병합 필드로 이동하려면 DocumentBuilder 클래스의 MoveToField 메서드를 사용하고 해당 필드를 매개 변수로 전달합니다. 이렇게 하면 병합 필드 바로 뒤에 커서가 배치됩니다.

#### 질문: 병합 필드로 이동 기능을 사용하여 병합 필드 내부에 텍스트를 추가할 수 있습니까?

A: 아니요. 병합 필드로 이동 기능은 문서 작성기 커서를 병합 필드 바로 뒤에 배치합니다. 병합 필드 내부에 텍스트를 추가하려면 DocumentBuilder.MoveTo 메서드를 사용하여 커서를 병합 필드의 FieldStart 또는 FieldSeparator 노드로 이동할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 메일 병합 작업을 어떻게 수행할 수 있나요?

A: Aspose.Words for .NET은 메일 병합 작업에 대한 광범위한 지원을 제공합니다. MailMerge 클래스를 사용하면 배열, 데이터 세트 또는 사용자 정의 데이터 소스와 같은 다양한 소스의 데이터를 사용하여 메일 병합을 수행할 수 있습니다.