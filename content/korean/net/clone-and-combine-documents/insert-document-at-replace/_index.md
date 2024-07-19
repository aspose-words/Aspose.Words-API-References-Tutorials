---
title: 교체 시 문서 삽입
linktitle: 교체 시 문서 삽입
second_title: Aspose.Words 문서 처리 API
description: 자세한 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 하나의 Word 문서를 다른 Word 문서에 원활하게 삽입하는 방법을 알아보세요. 문서 처리를 간소화하려는 개발자에게 적합합니다.
type: docs
weight: 10
url: /ko/net/clone-and-combine-documents/insert-document-at-replace/
---
## 소개

안녕하세요, 문서 전문가 여러분! 한 Word 문서를 다른 Word 문서에 원활하게 삽입하는 방법을 알아내려고 코드에 빠져들었던 적이 있습니까? 두려워하지 마십시오. 오늘 우리는 해당 작업을 쉽게 수행하기 위해 .NET용 Aspose.Words의 세계로 뛰어들기 때문입니다. 찾기 및 바꾸기 작업 중 특정 지점에 문서를 삽입하기 위해 이 강력한 라이브러리를 사용하는 방법에 대한 자세한 단계별 가이드를 살펴보겠습니다. Aspose.Words 마법사가 될 준비가 되셨나요? 시작하자!

## 전제조건

코드를 시작하기 전에 준비해야 할 몇 가지 사항이 있습니다.

-  Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요. 아직 없으시다면, 다음에서 다운로드하실 수 있습니다.[여기](https://visualstudio.microsoft.com/).
-  .NET용 Aspose.Words: Aspose.Words 라이브러리가 필요합니다. 에서 받으실 수 있습니다.[Aspose 웹 사이트](https://releases.aspose.com/words/net/).
- 기본 C# 지식: C# 및 .NET에 대한 기본적인 이해는 이 자습서를 따라가는 데 도움이 됩니다.

좋습니다. 이제 코드를 좀 더 작성해 보겠습니다.

## 네임스페이스 가져오기

먼저 Aspose.Words를 사용하려면 필요한 네임스페이스를 가져와야 합니다. 이는 프로젝트를 시작하기 전에 모든 도구를 모으는 것과 같습니다. C# 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

이제 전제 조건이 준비되었으므로 프로세스를 간단한 단계로 나누어 보겠습니다. 각 단계는 매우 중요하며 목표에 더 가까워질 것입니다.

## 1단계: 문서 디렉토리 설정

먼저 문서가 저장되는 디렉터리를 지정해야 합니다. 이는 마치 큰 공연을 앞두고 무대를 준비하는 것과 같습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 디렉토리 경로와 함께. 이곳은 귀하의 문서가 살아 숨쉬는 곳입니다.

## 2단계: 주 문서 로드

다음으로 다른 문서를 삽입하려는 기본 문서를 로드합니다. 이것을 모든 작업이 일어나는 주요 단계라고 생각하십시오.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

이 코드는 지정된 디렉터리에서 기본 문서를 로드합니다.

## 3단계: 찾기 및 바꾸기 옵션 설정

문서를 삽입할 특정 위치를 찾으려면 찾기 및 바꾸기 기능을 사용합니다. 이는 새로 추가할 정확한 지점을 찾기 위해 지도를 사용하는 것과 같습니다.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

여기서는 방향을 뒤로 설정하고 다음에 정의할 사용자 정의 콜백 핸들러를 지정합니다.

## 4단계: 바꾸기 작업 수행

이제 사용자 정의 콜백을 사용하여 다른 문서를 삽입하는 동안 특정 자리 표시자 텍스트를 찾아서 아무것도 바꾸지 않도록 기본 문서에 지시합니다.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

이 코드는 찾기 및 바꾸기 작업을 수행한 다음 업데이트된 문서를 저장합니다.

## 5단계: 사용자 지정 대체 콜백 핸들러 만들기

우리의 사용자 정의 콜백 핸들러는 마법이 일어나는 곳입니다. 이 처리기는 찾기 및 바꾸기 작업 중에 문서 삽입이 수행되는 방법을 정의합니다.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // 일치 텍스트가 포함된 단락 뒤에 문서를 삽입합니다.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // 일치하는 텍스트가 있는 단락을 제거합니다.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

여기서는 삽입할 문서를 로드한 후 도우미 메서드를 호출하여 삽입을 수행합니다.

## 6단계: 문서 삽입 방법 정의

우리 퍼즐의 마지막 조각은 문서를 지정된 위치에 실제로 삽입하는 방법입니다.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// 섹션 본문의 모든 블록 수준 노드를 반복합니다.
		// 그런 다음 섹션의 마지막 빈 단락이 아닌 모든 노드를 복제하고 삽입합니다.
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

이 방법은 삽입할 문서에서 노드를 가져와서 기본 문서의 올바른 위치에 배치하는 작업을 처리합니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 한 문서를 다른 문서에 삽입하는 방법에 대한 포괄적인 가이드입니다. 다음 단계를 따르면 문서 조립 및 조작 작업을 쉽게 자동화할 수 있습니다. 문서 관리 시스템을 구축하든 문서 처리 워크플로를 간소화해야 하든 Aspose.Words는 신뢰할 수 있는 조수입니다.

## FAQ

### .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 Word 문서를 프로그래밍 방식으로 조작하기 위한 강력한 라이브러리입니다. 이를 통해 Word 문서를 쉽게 생성, 수정, 변환 및 처리할 수 있습니다.

### 한 번에 여러 문서를 삽입할 수 있나요?
예, 문서 컬렉션을 반복하여 여러 삽입을 처리하도록 콜백 핸들러를 수정할 수 있습니다.

### 무료 평가판이 제공되나요?
 전적으로! 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Aspose.Words에 대한 지원을 받으려면 어떻게 해야 하나요?
방문하시면 지원을 받으실 수 있습니다.[Aspose.Words 포럼](https://forum.aspose.com/c/words/8).

### 삽입된 문서의 서식을 유지할 수 있나요?
 예,`NodeImporter` 클래스를 사용하면 한 문서에서 다른 문서로 노드를 가져올 때 서식이 처리되는 방식을 지정할 수 있습니다.