---
title: 테이블
linktitle: 테이블
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 사용하여 테이블을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/table/
---


이 예에서는 Aspose.Words for .NET을 사용하여 테이블을 만드는 방법을 안내합니다. 테이블은 정보를 행과 열로 구성하는 데이터 구조입니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## 2단계: 셀 및 데이터 추가

 다음을 사용하여 테이블에 셀과 데이터를 추가하겠습니다.`InsertCell` 방법과`Writeln` 문서 생성기의 방법.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### .NET용 Aspose.Words를 사용하여 테이블을 생성하기 위한 예제 소스 코드

```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

// 첫 번째 행을 추가합니다.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// 두 번째 행을 추가합니다.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

축하합니다! 이제 Aspose.Words for .NET을 사용하여 테이블을 만드는 방법을 배웠습니다.

### FAQ

#### Q: Markdown에서 테이블을 어떻게 생성합니까?

A: Markdown에서 테이블을 생성하려면 파이프 구문(`|`)를 사용하여 셀과 대시를 구분합니다(`-`)을 사용하여 테이블 헤더를 구분합니다.

#### Q: Markdown에서 테이블의 모양을 사용자 정의할 수 있나요?

A: 표준 Markdown에서는 테이블 사용자 정의 옵션이 제한됩니다. 그러나 일부 Markdown 편집기를 사용하면 표에 CSS 스타일을 추가하여 모양을 사용자 정의할 수 있습니다.

#### Q: Markdown에서 테이블의 셀을 병합하는 방법은 무엇입니까?

A: Markdown에서 테이블의 셀 병합은 사용된 Markdown 편집기에 따라 다릅니다. 일부 Markdown 편집기는 특정 구문을 사용하여 셀 병합을 지원합니다.

#### Q: Markdown의 테이블은 CSS 스타일을 지원합니까?

A: 표준 Markdown에서 테이블은 CSS 스타일을 직접 지원하지 않습니다. 그러나 일부 Markdown 편집기를 사용하면 표에 CSS 스타일을 추가하여 모양을 사용자 정의할 수 있습니다.

#### Q: Markdown의 테이블 셀에 인라인 형식의 링크나 텍스트를 추가할 수 있나요?

A: 예, 적절한 Markdown 구문을 사용하여 Markdown의 테이블 셀에 링크나 인라인 텍스트를 추가할 수 있습니다.