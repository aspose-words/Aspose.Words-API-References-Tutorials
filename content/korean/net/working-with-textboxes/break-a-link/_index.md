---
title: Word 문서에서 앞으로 링크 끊기
linktitle: Word 문서에서 앞으로 링크 끊기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 정방향 링크를 끊는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET은 프로그래밍 방식으로 Microsoft Word 문서의 단어 처리를 위한 다양한 기능을 제공하는 강력한 라이브러리입니다. 유용한 기능 중 하나는 워드 문서에서 정방향 링크를 끊는 기능입니다. 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 링크 정방향을 끊는 방법을 보여주는 C#의 소스 코드를 살펴보겠습니다.

## 1단계: C# 소스 코드 미리보기

제공된 C# 소스 코드는 .NET용 Aspose.Words의 "Break A Link" 기능에 중점을 둡니다. 문서 내부의 TextBox 모양에서 링크를 끊는 방법을 보여줍니다. 코드는 링크를 끊는 다양한 시나리오를 제시하고 원하는 결과를 얻는 방법에 대한 명확한 지침을 제공합니다.

## 2단계: 문서 설정 및 TextBox 모양 만들기

 시작하려면 문서를 설정하고 TextBox 모양을 만들어야 합니다. 다음 코드는`Document` 클래스를 생성하고 텍스트 상자 모양을 만듭니다.

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 3단계: TextBox에서 링크 앞으로 끊기

 TextBox에서 정방향 링크를 끊기 위해 다음을 사용할 수 있습니다.`BreakForwardLink()` 방법. 이 방법은 시퀀스의 다음 셰이프에 대한 링크를 끊습니다. 다음 코드는 정방향 링크를 끊는 방법을 보여줍니다.

```csharp
textBox.BreakForwardLink();
```

## 4단계: null 값을 설정하여 정방향 링크 끊기

 또는 TextBox의 값을 설정하여 정방향 링크를 끊을 수 있습니다.`Next`재산`null`. 이렇게 하면 다음 셰이프에 대한 연결이 효과적으로 제거됩니다. 다음 코드는 이 접근 방식을 보여줍니다.

```csharp
textBox. Next = null;
```

## 5단계: TextBox로 연결되는 링크 끊기

 어떤 경우에는 TextBox 모양으로 연결되는 링크를 끊어야 합니다. 우리는 다음을 호출하여 이를 달성할 수 있습니다.`BreakForwardLink()` 에 대한 방법`Previous` TextBox에 대한 링크를 끊는 양식입니다. 다음은 이러한 링크를 끊는 방법에 대한 예입니다.

```csharp
textBox.Previous?.BreakForwardLink();
```

### .NET용 Aspose.Words와의 링크를 끊기 위한 샘플 소스 코드

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// 앞으로 링크를 끊습니다.
textBox.BreakForwardLink();

// null 값을 설정하여 정방향 링크를 끊습니다.
textBox. Next = null;

// 이 텍스트 상자로 연결되는 링크를 끊습니다.
textBox.Previous?.BreakForwardLink();
```

## 결론

축하합니다! 이제 .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서에서 리디렉션 링크를 끊는 방법을 배웠습니다. 이 가이드의 단계에 따라 문서를 설정하고, TextBox 모양을 만들고, 다양한 방법을 사용하여 리디렉션 링크를 끊을 수 있었습니다.

### Word 문서의 앞으로 전환 링크에 대한 FAQ

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서에서 리디렉션 링크를 끊는 데 사용되는 라이브러리는 무엇입니까?

A: .NET용 Aspose.Words를 사용하여 Word 문서에서 리디렉션 링크를 끊기 위해 사용되는 라이브러리는 .NET용 Aspose.Words입니다.

#### Q: TextBox에서 리디렉션 링크를 끊는 방법은 무엇입니까?

 A: TextBox의 정방향 링크를 끊으려면 다음을 사용할 수 있습니다.`BreakForwardLink()` 방법. 이 방법은 시퀀스의 다음 셰이프에 대한 링크를 끊습니다.

#### Q: null 값을 설정하여 리디렉션 링크를 끊는 방법은 무엇입니까?

A: 또는 다음을 설정하여 리디렉션 링크를 끊을 수 있습니다.`Next` TextBox의 속성을`null`. 이렇게 하면 다음 셰이프에 대한 연결이 효과적으로 제거됩니다.

#### Q: TextBox로 연결되는 링크를 어떻게 끊나요?

 A: 어떤 경우에는 TextBox로 연결되는 링크를 끊어야 합니다. 이 작업은 다음을 호출하여 수행할 수 있습니다.`BreakForwardLink()` 에 대한 방법`Previous` TextBox에 대한 링크를 끊는 양식입니다.

#### Q: TextBox가 아닌 요소의 리디렉션 링크를 끊을 수 있나요?

A: 예, .NET용 Aspose.Words를 사용하면 단락, 표, 이미지 등과 같은 다양한 요소의 리디렉션 링크를 끊을 수 있습니다. 프로세스는 링크를 끊으려는 특정 항목에 따라 달라질 수 있습니다.