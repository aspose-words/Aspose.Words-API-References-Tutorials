---
title: 정렬된 목록
linktitle: 정렬된 목록
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 통해 정렬된 목록을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/ordered-list/
---

이 예에서는 Aspose.Words for .NET에서 정렬된 목록 기능을 사용하는 방법을 설명합니다. 순서가 지정된 목록을 사용하면 항목을 숫자로 순차적으로 구성할 수 있습니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 새 문서를 만듭니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 정렬된 목록 형식 적용

 문서 작성 도구를 사용하여 순서가 지정된 목록 형식을 적용하겠습니다.`ApplyBulletDefault`방법. 목록 수준으로 이동하여 원하는 형식을 설정하여 번호 매기기 형식을 사용자 정의할 수도 있습니다.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## 3단계: 목록에 항목 추가

 문서 생성기의 기능을 사용하여 목록에 항목을 추가할 수 있습니다.`Writeln` 방법.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 4단계: 목록 들여쓰기

 문서 생성기의`ListIndent` 방법.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## 5단계: 문서 저장

마지막으로 원하는 형식으로 문서를 저장할 수 있습니다.

### .NET용 Aspose.Words를 사용한 정렬된 목록의 예제 소스 코드

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

축하합니다! 이제 Aspose.Words for .NET에서 순서 목록 기능을 사용하는 방법을 배웠습니다.


### FAQ

#### Q: Markdown에서 순서가 지정된 목록을 만드는 방법은 무엇입니까?

A: Markdown에서 순서가 지정된 목록을 만들려면 각 목록 항목을 숫자와 마침표((`1.`, `2.`, `3.`), 그 뒤에 공백이 옵니다.

#### Q: Markdown에서 순서가 지정된 목록을 중첩할 수 있나요?

A: 예, 각 중첩 목록 항목 앞에 4개의 오프셋 공백을 추가하여 Markdown에서 순서가 지정된 목록을 중첩할 수 있습니다.

#### Q: 순서가 지정된 목록의 번호 매기기를 사용자 정의하는 방법은 무엇입니까?

A: 표준 Markdown에서는 순서가 지정된 목록 번호 매기기가 자동으로 생성됩니다. 그러나 일부 Markdown 편집기에서는 특정 확장을 사용하여 사용자 정의할 수 있습니다.

#### Q: Markdown의 순서 목록은 들여쓰기를 지원합니까?

A: 예, Markdown의 정렬된 목록은 들여쓰기를 지원합니다. 공백이나 탭을 사용하여 왼쪽 Shift를 추가할 수 있습니다.

#### Q: 목록 항목에 링크나 인라인 텍스트를 추가할 수 있나요?

A: 예, 적절한 Markdown 구문을 사용하여 목록 항목에 링크나 인라인 텍스트를 추가할 수 있습니다.