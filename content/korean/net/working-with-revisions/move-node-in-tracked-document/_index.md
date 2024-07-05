---
title: 추적된 문서에서 노드 이동
linktitle: 추적된 문서에서 노드 이동
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 추적된 문서에서 노드를 이동하세요.
type: docs
weight: 10
url: /ko/net/working-with-revisions/move-node-in-tracked-document/
---

이 단계별 가이드에서는 Aspose.Words for .NET을 사용하여 추적된 Word 문서에서 노드를 이동하는 방법을 안내합니다. 전체 소스 코드를 제공하고 마크다운 출력 형식을 지정하는 방법을 보여 드리겠습니다.

## 1단계: 문서 만들기

첫 번째 단계는 새 문서를 만들고 단락을 추가하는 것입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## 2단계: 버전 추적

문서에서 개정 추적을 활성화하겠습니다.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## 3단계: 노드 이동

개정을 생성하는 동안 노드(단락)를 한 위치에서 다른 위치로 이동합니다.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## 4단계: 리뷰 추적 중지

문서의 개정 내용 추적을 중단합니다.

```csharp
doc.StopTrackRevisions();
```

## 5단계: 문서 저장

 텍스트 입력 양식 필드를 삽입한 후,`Save`방법. 적절한 파일 경로를 제공해야 합니다.

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### .NET용 Aspose.Words를 사용하여 추적된 문서에서 노드 이동에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 추적된 문서에서 노드를 이동하기 위한 전체 소스 코드입니다.


```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// 개정판 추적을 시작하세요.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// 노드를 한 위치에서 다른 위치로 이동할 때 개정을 생성합니다.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// 개정판 추적 프로세스를 중지합니다.
doc.StopTrackRevisions();

// 이동 시작 범위에는 3개의 추가 단락이 있습니다.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 추적된 Word 문서에서 노드를 이동하는 방법을 배웠습니다. 문서 작성, 개정 추적 활성화, 노드 이동 및 개정 추적 중지 단계를 수행함으로써 이 조작을 성공적으로 수행할 수 있었습니다. Aspose.Words for .NET은 Word 문서의 단어 처리를 위한 강력한 도구이며 개정 관리를 위한 고급 기능을 제공합니다. 이제 이 지식을 사용하여 .NET용 Aspose.Words를 사용하여 개정 내용을 추적하면서 자신의 Word 문서에서 노드를 이동할 수 있습니다.

### FAQ

#### Q: .NET 문서용 Aspose.Words에서 개정 추적을 활성화하려면 어떻게 해야 합니까?

 A: .NET 문서용 Aspose.Words에서 개정 추적을 활성화하려면 다음을 사용할 수 있습니다.`StartTrackRevisions` 의 방법`Document` 물체. 이 방법은 개정판 작성자의 이름과 개정판 후속 작업의 시작 날짜를 매개변수로 사용합니다.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### Q: 수정본을 생성하지 않고 추적된 문서에서 노드를 이동하려면 어떻게 해야 합니까?

 A: 수정본을 생성하지 않고 추적된 문서에서 노드를 이동하려는 경우 다음을 사용할 수 있습니다.`Remove` 그리고`InsertAfter` 또는`InsertBefore` 방법`Node` 물체. 예를 들어, 다른 단락 뒤로 단락을 이동하려면 다음 코드를 사용할 수 있습니다.

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### Q: .NET 문서용 Aspose.Words에서 개정 추적을 어떻게 중지할 수 있습니까?

 A: .NET용 Aspose.Words 문서에서 개정 추적을 중지하려면 다음을 사용할 수 있습니다.`StopTrackRevisions` 의 방법`Document` 물체.

```csharp
doc.StopTrackRevisions();
```