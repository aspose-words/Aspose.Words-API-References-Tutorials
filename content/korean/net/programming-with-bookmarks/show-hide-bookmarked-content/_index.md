---
title: Word 문서에서 북마크된 콘텐츠 숨기기 표시
linktitle: Word 문서에서 북마크된 콘텐츠 숨기기 표시
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 북마크 콘텐츠를 표시하거나 숨기는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 Aspose.Words for .NET 라이브러리에서 Show Hide Bookmarked Content 기능을 사용하는 방법을 이해합니다. 이 기능을 사용하면 데이터 병합 시 특정 조건에 따라 Word 문서의 북마크 내용을 표시하거나 숨길 수 있습니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 북마크 가져오기

 우리는`Bookmarks` 콘텐츠를 표시하거나 숨기려는 특정 책갈피를 가져오려면 문서 범위의 속성을 사용하세요.

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## 2단계: 병합 필드 삽입

 우리는 문서 작성기를 사용합니다`DocumentBuilder` 필요한 병합 필드를 삽입합니다. 이러한 병합 필드는 값에 따라 북마크 내용을 표시하거나 숨기는 조건을 설정합니다.`showHide` 변하기 쉬운:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## 3단계: 북마크 콘텐츠 이동

북마크의 내용을 반복하여 표시되도록 이동합니다.

북마크 앞에 표시됩니다. 이는 지정된 조건에 따라 콘텐츠 표시 또는 숨기기를 제어합니다.

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## 4단계: 나머지 북마크 콘텐츠 이동

북마크의 끝 노드를 삽입 지점으로 사용하여 북마크 뒤의 나머지 북마크 콘텐츠를 이동합니다.

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## 5단계: 병합 수행

 우리는`Execute` 문서의 방법`s `편지 병합` object to execute the merge using the bookmark name and the value of the `showHide` 변수:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### .NET용 Aspose.Words를 사용하여 북마크된 콘텐츠 숨기기 표시에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 북마크 콘텐츠를 표시하거나 숨기는 방법을 보여주는 소스 코드의 전체 예입니다.

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD 북마크}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## 결론

이 기사에서는 .NET용 Aspose.Words의 북마크 콘텐츠 숨기기 표시 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 데이터를 병합할 때 특정 조건에 따라 북마크 내용을 표시하거나 숨기는 단계별 지침을 따랐습니다.

### Word 문서에서 북마크된 콘텐츠 숨기기에 대한 FAQ

#### Q: 동일한 문서의 여러 북마크에 동일한 조건을 사용할 수 있나요?

A: 예, 동일한 문서의 여러 북마크에 대해 동일한 조건을 사용할 수 있습니다. 각 북마크에 대해 2~5단계를 반복하여 북마크 이름과 선택적으로 값을 조정하세요.`showhide` 필요에 따라 변수.

#### Q: 북마크 콘텐츠를 표시하거나 숨기는 조건을 추가하려면 어떻게 해야 합니까?

 A: 더 많은 조건을 추가하려면 다음과 같은 논리 연산자를 사용할 수 있습니다.`AND` 그리고`OR` 2단계에서 병합 필드를 삽입하는 코드에 추가 조건을 추가하려면 다음 코드의 조건을 편집하세요.

```csharp
builder. Write("\" = \"true\" ");
```

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 북마크를 어떻게 삭제할 수 있나요?

 A: .NET용 Aspose.Words를 사용하여 Word 문서에서 책갈피를 제거하려면 다음을 사용할 수 있습니다.`Remove` 의 방법`Bookmarks` 문서 범위의 컬렉션입니다. 특정 북마크를 삭제하는 샘플 코드는 다음과 같습니다.

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### Q: Aspose.Words 라이브러리는 무료인가요?

 A: Aspose.Words 라이브러리는 상업용 라이브러리이므로 프로젝트에서 사용하려면 유효한 라이센스가 필요합니다. 당신은 확인할 수 있습니다[.NET API 참조용 Aspose.Words](https://reference.aspose.com/words/net/) 라이선스 옵션 및 가격에 대해 자세히 알아보세요.

#### Q: .NET에서 Word 문서를 사용한 단어 처리에 사용할 수 있는 다른 라이브러리가 있습니까?

A: 예, Open XML SDK 및 GemBox.Document와 같이 .NET의 Word 문서로 단어 처리에 사용할 수 있는 다른 라이브러리가 있습니다. 특정 요구 사항과 선호도에 따라 Aspose.Words의 대안으로 이러한 라이브러리를 탐색할 수 있습니다.