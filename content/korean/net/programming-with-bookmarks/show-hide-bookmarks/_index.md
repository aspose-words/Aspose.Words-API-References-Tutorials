---
title: Word 문서에서 책갈피 숨기기 표시
linktitle: Word 문서에서 책갈피 숨기기 표시
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 특정 북마크를 표시하거나 숨기는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/show-hide-bookmarks/
---

이 기사에서는 위의 C# 소스 코드를 탐색하여 .NET용 Aspose.Words 라이브러리에서 Show Hide Bookmarks 기능을 사용하는 방법을 이해합니다. 이 기능을 사용하면 Word 문서에서 특정 책갈피를 표시하거나 숨길 수 있습니다.

## 전제조건

- C# 언어에 대한 기본 지식.
- Aspose.Words 라이브러리가 설치된 .NET 개발 환경.

## 1단계: 문서 로드

 우리는`Document` 파일에서 기존 문서를 로드하는 클래스:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## 2단계: 특정 북마크 표시 또는 숨기기

 우리는`ShowHideBookmarkedContent` 문서 내 특정 북마크를 표시하거나 숨기는 기능입니다. 이 함수는 문서, 북마크 이름, 북마크 표시 여부를 나타내는 부울 값을 매개변수로 사용합니다.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## 3단계: 수정된 문서 저장

 우리는`Save` 수정된 문서를 파일에 저장하는 방법:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### .NET용 Aspose.Words를 사용하여 북마크 숨기기 표시에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 특정 북마크를 표시하거나 숨기는 방법을 보여주는 전체 예제 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedContent 소스 코드

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
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
        }
		
```
## 결론

이 기사에서는 .NET용 Aspose.Words의 Show Hide Bookmarks 기능을 사용하는 방법을 이해하기 위해 C# 소스 코드를 살펴보았습니다. 문서에서 특정 책갈피를 표시하거나 숨기는 단계별 가이드를 따랐습니다.

### Word 문서에서 북마크 숨기기에 대한 FAQ

#### Q: 동일한 문서에서 여러 북마크를 표시하거나 숨길 수 있나요?

A: 예, 처리하려는 각 북마크에 대해 2단계와 3단계를 반복하여 동일한 문서에서 여러 북마크를 표시하거나 숨길 수 있습니다.

#### Q: 제공된 코드는 .doc 또는 .docm과 같은 다른 Word 문서 형식에서도 작동합니까?

A: 예, 제공된 코드는 .doc 및 .docm과 같이 Aspose.Words가 지원하는 다양한 Word 문서 형식에서 작동합니다. 문서를 로드하고 저장할 때 올바른 파일 이름과 경로를 사용했는지 확인하세요.

#### Q: 숨겨진 북마크를 다시 표시하려면 어떻게 해야 합니까?

 A: 숨겨진 북마크를 다시 표시하려면 동일한 북마크를 사용해야 합니다.`ShowHideBookmarkedContent` 값을 전달하는 함수`true` 북마크를 표시할지 숨길지를 나타내는 부울 매개변수입니다.

#### Q: 조건을 사용하여 문서의 병합 필드 값을 기반으로 책갈피를 표시하거나 숨길 수 있습니까?

 A: 예, 조건과 병합 필드 값을 사용하여 북마크를 표시할지 숨길지 결정할 수 있습니다. 코드를 사용자 정의할 수 있습니다.`ShowHideBookmarkedContent` 적절한 조건과 값을 고려하는 기능입니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 북마크를 어떻게 삭제할 수 있나요?

 A: .NET용 Aspose.Words를 사용하여 Word 문서에서 책갈피를 제거하려면 다음을 사용할 수 있습니다.`RemoveBookmarks` 의 방법`Document` 수업. 다음은 샘플 코드입니다.

```csharp
doc.RemoveBookmarks("BookmarkName");
```