---
title: 취소선
linktitle: 취소선
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET 단계별 가이드를 통해 취소선 텍스트 스타일을 적용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/strikethrough/
---


이 예에서는 Aspose.Words for .NET을 사용하여 취소선 텍스트 스타일을 적용하는 방법을 안내합니다. 취소선 텍스트는 텍스트가 삭제되었거나 더 이상 유효하지 않음을 나타내는 데 사용됩니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 취소선 텍스트 스타일 적용

 취소선 텍스트 스타일을 활성화하려면`StrikeThrough` 의 재산`Font` 반대하다`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## 3단계: 취소선 텍스트 추가

 이제 문서 생성기의`Writeln` 방법.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### .NET용 Aspose.Words를 사용한 취소선 텍스트의 예제 소스 코드

```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

// 텍스트를 취소선으로 만듭니다.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

축하합니다! 이제 Aspose.Words for .NET을 사용하여 취소선 텍스트 스타일을 적용하는 방법을 배웠습니다.

### FAQ

#### Q: Aspose.Words에 취소선 텍스트를 어떻게 추가할 수 있나요?

 A: Aspose.Words에 취소선 텍스트를 추가하려면`Font.StrikeThrough` 의 재산`Run`물체. 이 속성을 다음과 같이 설정할 수 있습니다.`true` 특정 텍스트에 취소선 텍스트를 추가하려면 예를 들어 다음을 사용할 수 있습니다.`run.Font.StrikeThrough=true` 취소선 텍스트를`Run` 물체.

#### Q: 같은 단락의 여러 텍스트에 취소선 텍스트를 추가할 수 있습니까?

 A: 예, 여러 가지 옵션을 사용하여 단일 단락에 있는 텍스트의 여러 부분에 취소선 텍스트를 추가할 수 있습니다.`Run` 사물. 여러 개를 생성할 수 있습니다.`Run` 객체를 설정하고`Font.StrikeThrough`재산`true` 각 개체에 대해 취소선 텍스트를 원하는 텍스트 부분에 추가합니다. 그런 다음 다음을 사용하여 단락에 추가할 수 있습니다.`Paragraph.AppendChild(run)` 방법.

#### Q: Aspose.Words의 테이블이나 셀에 있는 텍스트에 취소선 텍스트를 추가할 수 있나요?

 A: 예, Aspose.Words의 테이블이나 셀에 있는 텍스트에 취소선 텍스트를 추가할 수 있습니다. 적절한 방법을 사용하여 원하는 셀이나 단락으로 이동한 다음`Font.StrikeThrough` 의 재산`Run` 또는`Paragraph` 물체.