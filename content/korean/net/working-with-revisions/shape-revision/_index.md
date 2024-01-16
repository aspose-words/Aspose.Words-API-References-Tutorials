---
title: 모양 개정
linktitle: 모양 개정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 모양을 수정하세요.
type: docs
weight: 10
url: /ko/net/working-with-revisions/shape-revision/
---

이 단계별 가이드에서는 Aspose.Words for .NET을 사용하여 Word 문서의 도형을 수정하는 방법을 안내합니다. 전체 소스 코드를 제공하고 마크다운 출력 형식을 지정하는 방법을 보여 드리겠습니다.

## 1단계: 문서 만들기 및 도형 추가

첫 번째 단계는 새 문서를 만들고 모양을 추가하는 것입니다.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 2단계: 수정 내용 추적 및 다른 도형 추가

개정 추적을 켜고 다른 모양을 추가하겠습니다.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 3단계: 모양 컬렉션 가져오기 및 수정 사항 확인

문서에서 모양 컬렉션을 가져와 각 모양과 관련된 개정을 확인합니다.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## 4단계: 모양 이동 수정 사항 확인

형상 변위 개정이 포함된 기존 문서를 로드하고 관련 개정을 확인하겠습니다.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### .NET용 Aspose.Words를 사용한 Shape Revision의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 문서의 모양을 수정하기 위한 전체 소스 코드입니다.

```csharp
Document doc = new Document();

//수정 내용을 추적하지 않고 인라인 셰이프를 삽입합니다.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// 수정본 추적을 시작한 다음 다른 모양을 삽입하세요.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// 우리가 추가한 두 개의 도형만 포함하는 문서의 도형 컬렉션을 가져옵니다.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// 첫 번째 모양을 제거합니다.
shapes[0].Remove();

// 변경 사항을 추적하는 동안 해당 모양을 제거했기 때문에 해당 모양은 삭제 개정으로 간주됩니다.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// 그리고 변경 사항을 추적하는 동안 다른 모양을 삽입하여 해당 모양이 삽입 개정으로 계산됩니다.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// 문서에는 이동된 셰이프가 하나 있지만 셰이프 이동 수정 버전에는 해당 셰이프의 인스턴스가 두 개 있습니다.
// 하나는 도착지의 모양이고 다른 하나는 원래 위치의 모양입니다.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// 이것이 개정으로의 이동이며, 도착지의 형상이기도 하다.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// 이는 원래 위치의 모양인 개정판에서 이동한 것입니다.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 도형을 수정하는 방법을 배웠습니다. 문서 작성, 개정 추적 활성화, 각 도형과 관련된 개정 확인, 도형 이동에 대한 개정 확인 단계를 수행함으로써 개정을 성공적으로 관리할 수 있었습니다. Aspose.Words for .NET은 Word 문서의 검토 및 양식을 통해 Words 처리를 위한 강력한 API를 제공합니다.

### FAQ

#### Q: .NET용 Aspose.Words에서 새 문서를 만들고 모양을 추가하려면 어떻게 해야 합니까?

A: .NET용 Aspose.Words에서 새 문서를 만들고 모양을 추가하려면 다음 코드를 사용할 수 있습니다. 여기서는 문서의 첫 번째 섹션에 정육면체와 태양이라는 두 가지 모양을 추가합니다.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Q: .NET용 Aspose.Words에서 개정 추적을 어떻게 활성화합니까?

 A: .NET용 Aspose.Words에서 개정 추적을 활성화하려면 다음을 사용할 수 있습니다.`StartTrackRevisions` 의 방법`Document` 물체. 이 메소드는 개정판 작성자의 이름을 매개변수로 사용합니다.

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Q: Aspose.Words for .NET 문서의 각 모양과 관련된 개정을 어떻게 확인할 수 있습니까?

A: Aspose.Words for .NET 문서의 각 모양과 관련된 개정을 확인하려면 다음을 사용하여 문서의 모양 컬렉션을 얻을 수 있습니다.`GetChildNodes` 방법`NodeType.Shape` 노드 유형. 그런 다음 각 도형의`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , 그리고`IsMoveToRevision` 모양과 연관된 개정 유형을 결정하는 속성:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Q: Aspose.Words for .NET 문서에서 모양의 변위 개정을 어떻게 확인할 수 있나요?

 A: Aspose.Words for .NET 문서에서 모양 변위 개정을 확인하려면 모양 변위 개정이 포함된 기존 문서를 로드할 수 있습니다. 그런 다음 각 도형의`IsMoveFromRevision` 그리고`IsMoveToRevision` 이동 중인지, 그렇다면 어디서, 어디로 이동하는지 확인하는 속성:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```