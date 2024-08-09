---
title: 추적된 문서에서 노드 이동
linktitle: 추적된 문서에서 노드 이동
second_title: Aspose.Words 문서 처리 API
description: 자세한 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 추적된 Word 문서에서 노드를 이동하는 방법을 알아보세요. 개발자에게 적합합니다.
type: docs
weight: 10
url: /ko/net/working-with-revisions/move-node-in-tracked-document/
---
## 소개

안녕하세요, Aspose.단어 매니아 여러분! 수정 내용을 추적하는 동안 Word 문서에서 노드를 이동해야 했던 경우 올바른 위치에 오셨습니다. 오늘 우리는 .NET용 Aspose.Words를 사용하여 이를 달성하는 방법을 살펴보겠습니다. 단계별 프로세스를 배울 뿐만 아니라 문서를 원활하고 효율적으로 조작하는 데 필요한 몇 가지 팁과 요령도 익힐 수 있습니다.

## 전제 조건

일부 코드로 손을 더럽히기 전에 필요한 모든 것이 있는지 확인합시다.

-  .NET용 Aspose.Words: 다운로드[여기](https://releases.aspose.com/words/net/).
- .NET 환경: 호환 가능한 .NET 개발 환경이 설정되어 있는지 확인하세요.
- 기본 C# 지식: 이 자습서에서는 사용자가 C#에 대한 기본 지식을 가지고 있다고 가정합니다.

모든 것을 얻었나요? 엄청난! 가져와야 하는 네임스페이스로 이동해 보겠습니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져와야 합니다. 이는 Aspose.Words 작업 및 문서 노드 처리에 필수적입니다.

```csharp
using Aspose.Words;
using System;
```

이제 프로세스를 관리 가능한 단계로 나누어 보겠습니다. 모든 단계에서 무슨 일이 일어나고 있는지 이해할 수 있도록 각 단계를 자세히 설명합니다.

## 1단계: 문서 초기화

 시작하려면 새 문서를 초기화하고`DocumentBuilder` 몇 가지 단락을 추가합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 일부 단락 추가
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");

// 초기 단락 수 확인
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## 2단계: 개정 추적 시작

다음으로 개정 추적을 시작해야 합니다. 이는 문서의 변경 사항을 볼 수 있게 해주기 때문에 매우 중요합니다.

```csharp
// 개정 추적 시작
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## 3단계: 노드 이동

이제 우리 작업의 핵심 부분인 노드를 한 위치에서 다른 위치로 이동합니다. 세 번째 단락을 이동하여 첫 번째 단락 앞에 배치하겠습니다.

```csharp
// 이동할 노드와 끝 범위를 정의합니다.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];

// 정의된 범위 내에서 노드를 이동합니다.
while (node != endNode)
{
    Node nextNode = node.NextSibling;
    body.InsertBefore(node, referenceNode);
    node = nextNode;
}
```

## 4단계: 개정 추적 중지

노드를 이동한 후에는 개정 추적을 중지해야 합니다.

```csharp
// 버전 추적 중지
doc.StopTrackRevisions();
```

## 5단계: 문서 저장

마지막으로 수정된 문서를 지정된 디렉터리에 저장해 보겠습니다.

```csharp
// 수정된 문서를 저장하세요
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");

// 최종 단락 수를 출력합니다.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 추적된 문서에서 노드를 성공적으로 이동했습니다. 이 강력한 라이브러리를 사용하면 Word 문서를 프로그래밍 방식으로 쉽게 조작할 수 있습니다. 변경 사항을 생성, 편집 또는 추적하는 경우 Aspose.Words가 도와드립니다. 그러니 한번 시도해 보십시오. 즐거운 코딩하세요!

## FAQ

### .NET용 Aspose.Words란 무엇입니까?

Aspose.Words for .NET은 Word 문서를 프로그래밍 방식으로 작업하기 위한 클래스 라이브러리입니다. 이를 통해 개발자는 .NET 응용 프로그램 내에서 Word 문서를 생성, 편집, 변환 및 인쇄할 수 있습니다.

### Aspose.Words를 사용하여 Word 문서의 수정 내용을 어떻게 추적합니까?

 개정판을 추적하려면`StartTrackRevisions` 에 대한 방법`Document` 물체. 이렇게 하면 개정 추적이 활성화되어 문서에 대한 변경 사항이 표시됩니다.

### Aspose.Words에서 여러 노드를 이동할 수 있나요?

예, 여러 노드를 반복하고 다음과 같은 방법을 사용하여 여러 노드를 이동할 수 있습니다.`InsertBefore` 또는`InsertAfter` 원하는 위치에 배치합니다.

### Aspose.Words에서 개정 추적을 어떻게 중지합니까?

 사용`StopTrackRevisions` 에 대한 방법`Document` 개정판 추적을 중지하려면 개체를 사용하세요.

### .NET용 Aspose.Words에 대한 추가 문서는 어디서 찾을 수 있나요?

 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/words/net/).