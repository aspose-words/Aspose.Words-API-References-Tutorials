---
title: Word 문서의 섹션으로 이동
linktitle: Word 문서의 섹션으로 이동
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words의 Word 문서 기능에서 섹션으로 이동을 사용하는 단계별 가이드는 Word 문서의 섹션과 단락을 조작합니다.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/move-to-section/
---
이 예에서는 제공된 C# 소스 코드를 사용하여 Aspose.Words for .NET의 Word 문서에서 섹션으로 이동 기능을 단계별로 사용하는 방법을 안내합니다. 이 기능을 사용하면 Word 문서 내의 다양한 섹션을 탐색하고 조작할 수 있습니다. 이 기능을 애플리케이션에 통합하려면 아래 단계를 따르세요.

## 1단계: 새 문서 만들기 및 섹션 추가

먼저 새 문서를 만들고 섹션을 추가해야 합니다. 이 단계를 수행하려면 다음 코드를 사용하십시오.

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

이 코드는 새로운 빈 문서를 만들고 이 문서에 섹션을 추가합니다.

## 2단계: DocumentBuilder를 두 번째 섹션으로 이동하고 텍스트 추가

다음으로 DocumentBuilder를 문서의 두 번째 섹션으로 이동하고 여기에 텍스트를 추가해야 합니다. 이 단계를 수행하려면 다음 코드를 사용하십시오.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

이 코드는 기존 문서에서 DocumentBuilder를 만든 다음 DocumentBuilder에서 문서의 두 번째 섹션으로 커서를 이동합니다. 마지막으로 지정된 텍스트를 이 섹션에 추가합니다.

## 3단계: 기존 단락이 포함된 문서 로드

단락이 포함된 기존 문서로 작업하려면 다음 코드를 사용하여 이 문서를 로드할 수 있습니다.

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

이 코드는 지정된 문서를 로드합니다("MyDir + "Paragraphs.docx 교체)."" 문서의 실제 경로와 함께) 문서의 첫 번째 섹션에서 단락 컬렉션에 액세스합니다. 라인`Assert.AreEqual(22, paragraphs.Count);` 문서에 22개의 단락이 포함되어 있는지 확인합니다.

## 4단계: 문서에 대한 DocumentBuilder 만들기

위치 인덱스를 사용하여 특정 단락에 대한 DocumentBuilder 커서를 만들 수 있습니다.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## 5단계: 커서를 특정 단락으로 이동


위치 인덱스를 사용하여 DocumentBuilder 커서를 특정 단락으로 이동할 수 있습니다. 수행 방법은 다음과 같습니다.

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

이 코드는 DocumentBuilder의 커서를 두 번째 섹션의 세 번째 단락(인덱스 2의 단락) 및 위치 10으로 이동합니다. 그런 다음 일부 텍스트가 포함된 새 단락을 추가하고 커서가 이 새 단락에 잘 배치되었는지 확인합니다.

### .NET용 Aspose.Words를 사용하여 섹션으로 이동에 대한 예제 소스 코드

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// DocumentBuilder를 두 번째 섹션으로 이동하고 텍스트를 추가합니다.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// 단락이 포함된 문서를 만듭니다.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// 문서에 대한 DocumentBuilder를 만들 때 해당 커서는 기본적으로 문서의 맨 처음에 있습니다.
// DocumentBuilder에 의해 추가된 모든 콘텐츠는 문서 앞에 추가됩니다.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//단락의 어느 위치로든 커서를 이동할 수 있습니다.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

그게 다야 ! 이제 제공된 소스 코드를 사용하여 .NET용 Aspose.Words의 섹션 이동 기능을 사용하는 방법을 이해했습니다. 이제 이 기능을 자신의 응용 프로그램에 통합하고 Word 문서의 섹션과 단락을 동적으로 조작할 수 있습니다.

## 결론

이 예에서는 .NET용 Aspose.Words의 섹션으로 이동 기능을 살펴보았습니다. 새 문서를 만들고, 섹션을 추가하고, DocumentBuilder 클래스를 사용하여 Word 문서 내의 특정 섹션과 단락으로 이동하는 방법을 배웠습니다. 이 기능은 개발자에게 Aspose.Words for .NET을 사용하여 프로그래밍 방식으로 Word 문서의 내용과 구조를 조작할 수 있는 강력한 도구를 제공합니다.

### Word 문서의 섹션 이동에 대한 FAQ

#### Q: Aspose.Words for .NET의 섹션으로 이동 기능의 목적은 무엇입니까?

A: .NET용 Aspose.Words의 섹션으로 이동 기능을 사용하면 개발자가 프로그래밍 방식으로 Word 문서 내의 다른 섹션을 탐색하고 조작할 수 있습니다. 문서의 특정 섹션에 내용을 삽입, 수정 또는 삭제할 수 있는 기능을 제공합니다.

#### Q: DocumentBuilder를 Word 문서의 특정 섹션으로 어떻게 이동합니까?

A: DocumentBuilder를 Word 문서의 특정 섹션으로 이동하려면 DocumentBuilder 클래스의 MoveToSection 메서드를 사용할 수 있습니다. 이 메서드는 대상 섹션의 인덱스를 매개 변수로 사용하고 해당 섹션의 시작 부분에 커서를 놓습니다.

#### Q: 섹션 이동 기능을 이용해 특정 섹션으로 이동한 후 콘텐츠를 추가하거나 수정할 수 있나요?

A: 예, MoveToSection을 사용하여 DocumentBuilder가 원하는 섹션에 배치되면 Writeln, Write 또는 InsertHtml과 같은 DocumentBuilder 클래스의 다양한 메서드를 사용하여 해당 섹션의 내용을 추가하거나 수정할 수 있습니다.

#### 질문: 섹션으로 이동 기능을 사용하여 문서의 기존 단락으로 작업하려면 어떻게 해야 합니까?

A: Document 생성자를 사용하여 단락이 포함된 기존 문서를 로드한 다음 FirstSection.Body.Paragraphs 속성을 사용하여 원하는 섹션의 단락 컬렉션에 액세스할 수 있습니다.

#### Q: 섹션으로 이동 기능을 사용하여 DocumentBuilder 커서를 섹션 내의 특정 단락으로 이동할 수 있습니까?

A: 예, MoveToParagraph 메서드를 사용하여 DocumentBuilder 커서를 섹션 내 특정 단락으로 이동할 수 있습니다. 이 메서드는 대상 단락의 인덱스와 단락 내 문자 위치(오프셋)를 매개 변수로 사용합니다.