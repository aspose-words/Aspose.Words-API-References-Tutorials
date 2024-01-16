---
title: Word 문서에 북마크된 텍스트 추가
linktitle: Word 문서에 북마크된 텍스트 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 책갈피에서 텍스트를 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/append-bookmarked-text/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 Aspose.Words for .NET 라이브러리에서 Append Bookmarked Text 기능을 사용하는 방법을 이해합니다. 이 기능을 사용하면 Word 문서의 특정 책갈피에 포함된 텍스트를 다른 문서에 추가할 수 있습니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 북마크에서 단락 가져오기

 북마크 텍스트 추가를 시작하기 전에 북마크의 시작과 끝을 포함하는 단락을 가져와야 합니다. 이 작업은 다음에 액세스하여 수행할 수 있습니다.`BookmarkStart` 그리고`BookmarkEnd` 북마크 속성:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## 2단계: 상위 단락 확인

시작 및 끝 단락에 유효한 부모가 있는지, 즉 실제로 단락에 속하는지 확인합니다. 그렇지 않은 경우 예외가 발생합니다.

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## 3단계: 단락의 상위 항목 확인

시작 문단과 끝 문단의 상위 문단이 같은지 확인합니다. 그렇지 않은 경우 단락이 동일한 섹션이나 문서에 포함되어 있지 않으며 예외가 발생한다는 의미입니다.

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## 4단계: 단락 복사

시작 단락부터 끝 단락까지 노드(단락)를 반복합니다. 각 노드에 대해 복사본을 만들고 이를 대상 문서의 컨텍스트로 가져옵니다.

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### .NET용 Aspose.Words를 사용하여 북마크된 텍스트 추가에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 북마크에서 텍스트를 추가하는 방법을 보여주는 전체 예제 소스 코드입니다.

```csharp

	// 북마크의 시작 부분을 포함하는 단락입니다.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// 북마크의 끝 부분을 포함하는 단락입니다.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// 합리적으로 간단한 시나리오로 제한하십시오.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// 시작 단락부터 끝 단락까지(및 포함) 모든 단락을 복사하고 싶습니다.
	// 따라서 우리가 멈추는 노드는 끝 단락 다음의 노드입니다.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//그러면 현재 노드의 복사본이 생성되고 컨텍스트에서 이를 가져옵니다(유효하게 만듭니다).
		// 대상 문서의 가져오기란 스타일과 목록 식별자를 올바르게 조정하는 것을 의미합니다.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## 결론

이 기사에서는 .NET용 Aspose.Words의 북마크 텍스트 추가 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 우리는 북마크에서 단락을 가져오고, 상위 항목을 확인하고, 단락을 다른 문서에 복사하는 방법에 대한 단계별 가이드를 따랐습니다.

### Word 문서에 북마크된 텍스트 추가에 대한 FAQ

#### Q1: Aspose.Words for .NET에서 "책갈피로 텍스트 추가" 기능을 사용하기 위한 전제 조건은 무엇입니까?

A: Aspose.Words for .NET의 "책갈피로 텍스트 추가" 기능을 사용하려면 C# 언어에 대한 기본 지식이 필요합니다. 또한 Aspose.Words 라이브러리가 설치된 .NET 개발 환경이 필요합니다.

#### Q2: Word 문서에서 책갈피의 시작과 끝이 포함된 단락을 가져오는 방법은 무엇입니까?

A: Word 문서에서 책갈피의 시작과 끝이 포함된 단락을 얻으려면`BookmarkStart` 그리고`BookmarkEnd` 북마크의 속성입니다. 다음은 샘플 코드입니다.

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3: 시작 및 끝 단락에 유효한 부모가 없으면 어떻게 됩니까?

A: 시작 및 끝 단락에 유효한 부모가 없는 경우, 즉 실제로 단락이 아닌 경우 예외가 발생합니다. 현재로서는 이 상황을 관리할 수 없습니다.
