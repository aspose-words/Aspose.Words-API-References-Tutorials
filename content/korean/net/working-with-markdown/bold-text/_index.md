---
title: 굵은 텍스트
linktitle: 굵은 텍스트
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 통해 텍스트를 굵은 글씨로 표시하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/bold-text/
---

이 예에서는 .NET용 Aspose.Words를 사용하여 텍스트를 굵게 표시하는 방법을 알려 드리겠습니다. 굵은 텍스트를 사용하면 눈에 더 잘 띄고 눈에 띄게 됩니다.

## 1단계: 문서 생성기 사용

먼저 문서 생성기를 사용하여 문서에 콘텐츠를 추가하겠습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2단계: 굵은 글씨

 문서 작성기의 설정을 통해 텍스트를 굵게 표시할 수 있습니다.`Font.Bold`재산`true`.

```csharp
builder.Font.Bold = true;
```

## 3단계: 문서에 콘텐츠 추가

 이제 다음과 같은 문서 작성기 메소드를 사용하여 문서에 컨텐츠를 추가할 수 있습니다.`Writeln`, 텍스트 한 줄을 추가합니다.

```csharp
builder.Writeln("This text will be bold");
```

## .NET용 Aspose.Words를 사용하는 굵은 텍스트의 예제 소스 코드


```csharp
// 문서 빌더를 사용하여 문서에 콘텐츠를 추가합니다.
DocumentBuilder builder = new DocumentBuilder();

// 텍스트를 굵게 표시합니다.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

축하합니다! 이제 Aspose.Words for .NET을 사용하여 텍스트를 굵게 표시하는 방법을 배웠습니다.


### FAQ

#### Q: Aspose.Words에서 텍스트를 굵게 표시하려면 어떻게 해야 합니까?

 A: Aspose.Words에서 텍스트를 굵게 표시하려면`Font.Bold` 의 재산`Run` 물체. 이 속성을 다음과 같이 설정할 수 있습니다.`true` 특정 텍스트를 굵게 표시합니다. 예를 들어 다음을 사용할 수 있습니다.`run.Font.Bold=true` 안에 있는 텍스트를 굵게 표시하려면`Run` 물체.

#### Q: 같은 단락에서 여러 텍스트를 굵게 표시할 수 있나요?

 A: 예, 여러 개의 텍스트를 사용하여 단일 단락에서 여러 텍스트를 굵게 표시할 수 있습니다.`Run` 사물. 여러 개를 생성할 수 있습니다.`Run` 객체를 설정하고`Font.Bold`재산`true` 각 개체에 대해 원하는 텍스트 부분을 굵게 표시합니다. 그런 다음 다음을 사용하여 단락에 추가할 수 있습니다.`Paragraph.AppendChild(run)` 방법.

#### Q: Aspose.Words의 테이블이나 셀에 있는 텍스트를 굵게 표시할 수 있나요?

 A: 예, Aspose.Words의 테이블이나 셀에 있는 텍스트를 굵은 글씨로 표시할 수 있습니다. 적절한 방법을 사용하여 원하는 셀이나 단락으로 이동한 다음`Font.Bold` 의 재산`Run` 또는`Paragraph` 물체.