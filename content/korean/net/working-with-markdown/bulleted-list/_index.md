---
title: 글머리 기호 목록
linktitle: 글머리 기호 목록
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 통해 글머리 기호 목록을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/bulleted-list/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 글머리 기호 목록을 만드는 방법을 알려 드리겠습니다. 글머리 기호 목록은 번호 매기기를 사용하지 않고 항목을 나열하는 데 사용됩니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 기본 글머리 기호 목록 적용

 문서 작성 도구를 사용하여 기본 글머리 기호 목록을 적용할 수 있습니다.`ApplyBulletDefault` 방법.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## 3단계: 글머리 기호 형식 사용자 정의

 속성에 액세스하여 글머리 기호 형식을 사용자 정의할 수 있습니다.`ListFormat.List.ListLevels[0]`. 이 예에서는 대시 "-"를 글머리 기호로 사용합니다.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## 4단계: 목록에 항목 추가

 이제 문서 작성기의`Writeln` 방법.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 5단계: 목록에서 들여쓰기 제거

 하위 목록을 생성하려면 다음을 사용하여 들여쓰기를 늘릴 수 있습니다.`ListFormat.ListIndent()` 방법. 이 예에서는 항목 2a와 2b에 하위 목록을 추가합니다.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### .NET용 Aspose.Words를 사용하는 글머리 기호 목록의 예제 소스 코드


```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

축하합니다! 이제 Aspose.Words for .NET을 사용하여 글머리 기호 목록을 만드는 방법을 배웠습니다.

### FAQ

#### Q: Markdown에서 글머리 기호 목록을 만드는 방법은 무엇입니까?

A: Markdown에서 글머리 기호 목록을 만들려면 각 목록 항목을 글머리 기호 기호(`-`, `*` , 또는`+`), 그 뒤에 공백이 옵니다.

#### Q: Markdown에서 글머리 기호 목록을 중첩할 수 있나요?

A: 예, 각 중첩 목록 항목 앞에 4개의 오프셋 공백을 추가하여 Markdown에서 글머리 기호 목록을 중첩할 수 있습니다.

#### Q: 글머리 기호 기호를 사용자 정의하는 방법은 무엇입니까?

A: 표준 Markdown에서는 글머리 기호 기호가 미리 정의되어 있습니다. 그러나 일부 Markdown 편집기에서는 특정 확장을 사용하여 사용자 정의할 수 있습니다.

#### Q: Markdown의 글머리 기호 목록은 들여쓰기를 지원합니까?

A: 예, Markdown의 글머리 기호 목록은 들여쓰기를 지원합니다. 공백이나 탭을 사용하여 왼쪽 Shift를 추가할 수 있습니다.

#### Q: 목록 항목에 링크나 인라인 텍스트를 추가할 수 있나요?

A: 예, 적절한 Markdown 구문을 사용하여 목록 항목에 링크나 인라인 텍스트를 추가할 수 있습니다.
