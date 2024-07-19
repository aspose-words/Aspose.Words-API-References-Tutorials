---
title: Word 문서에서 북마크된 콘텐츠 숨기기 표시
linktitle: Word 문서에서 북마크된 콘텐츠 숨기기 표시
second_title: Aspose.Words 문서 처리 API
description: 이 상세한 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 북마크된 콘텐츠를 표시하고 숨기는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## 소개

.NET용 Aspose.Words를 사용하여 문서 조작의 세계로 뛰어들 준비가 되셨습니까? 문서 작업을 자동화하려는 개발자이거나 프로그래밍 방식으로 Word 파일을 처리하는 데 궁금한 사람이라면 올바른 위치에 있습니다. 오늘은 Aspose.Words for .NET을 사용하여 Word 문서에서 북마크된 콘텐츠를 표시하고 숨기는 방법을 살펴보겠습니다. 이 단계별 가이드를 통해 북마크를 기반으로 콘텐츠 가시성을 제어하는 전문가가 될 수 있습니다. 시작하자!

## 전제조건

핵심적인 내용으로 넘어가기 전에 필요한 몇 가지 사항이 있습니다.

1. Visual Studio: .NET과 호환되는 모든 버전.
2.  .NET용 Aspose.Words: 다운로드[여기](https://releases.aspose.com/words/net/).
3. C#의 기본 이해: 간단한 "Hello World" 프로그램을 작성할 수 있다면 좋습니다.
4. 책갈피가 있는 Word 문서: 이 튜토리얼에서는 책갈피가 있는 샘플 문서를 사용합니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이를 통해 작업에 필요한 모든 도구를 확보할 수 있습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

이러한 네임스페이스가 준비되면 우리 모두 여행을 시작할 준비가 된 것입니다.

## 1단계: 프로젝트 설정

자, Visual Studio에서 프로젝트를 설정하여 시작하겠습니다.

### 새 프로젝트 만들기

Visual Studio를 열고 새 콘솔 앱(.NET Core) 프로젝트를 만듭니다. "BookmarkVisibilityManager"와 같이 눈에 띄는 이름을 지정하십시오.

### .NET용 Aspose.Words 추가

프로젝트에 .NET용 Aspose.Words를 추가해야 합니다. NuGet 패키지 관리자를 통해 이 작업을 수행할 수 있습니다.

1. 도구 > NuGet 패키지 관리자 > 솔루션용 NuGet 패키지 관리로 이동합니다.
2. "Aspose.Words"를 검색하세요.
3. 패키지를 설치합니다.

엄청난! 이제 프로젝트가 설정되었으므로 문서를 로드해 보겠습니다.

## 2단계: 문서 로드

북마크가 포함된 Word 문서를 로드해야 합니다. 이 튜토리얼에서는 "Bookmarks.docx"라는 샘플 문서를 사용합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 이 코드 조각은 문서 디렉터리의 경로를 설정하고 문서를`doc` 물체.

## 3단계: 북마크된 콘텐츠 표시/숨기기

이제 재미있는 부분이 나옵니다. 북마크를 기반으로 콘텐츠를 표시하거나 숨기는 것입니다. 우리는`ShowHideBookmarkedContent` 이것을 처리하기 위해.

북마크된 콘텐츠의 표시 여부를 전환하는 방법은 다음과 같습니다.

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### 방법의 분석

-  북마크 검색:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` 북마크를 가져옵니다.
- 노드 순회: 북마크 내의 노드를 순회합니다.
-  가시성 토글: 노드가`Run` (연속적인 텍스트 실행)`Hidden` 재산.

## 4단계: 방법 적용

우리의 방법을 적용하여 북마크를 기반으로 콘텐츠를 표시하거나 숨기도록 하겠습니다.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

이 코드 줄은 "MyBookmark1"이라는 책갈피 내의 콘텐츠를 숨깁니다.

## 5단계: 문서 저장

마지막으로 수정된 문서를 저장해 보겠습니다.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

그러면 변경한 내용이 포함된 문서가 저장됩니다.

## 결론

그리고 거기에 있습니다! Aspose.Words for .NET을 사용하여 Word 문서에서 북마크된 콘텐츠를 표시하고 숨기는 방법을 배웠습니다. 이 강력한 도구를 사용하면 보고서를 자동화하거나, 템플릿을 만들거나, Word 파일을 만지작거리는 등 문서를 쉽게 조작할 수 있습니다. 즐거운 코딩하세요!

## FAQ

### 여러 북마크를 한 번에 전환할 수 있나요?
 예, 전화로 문의하실 수 있습니다.`ShowHideBookmarkedContent` 전환하려는 각 북마크에 대한 메서드입니다.

### 콘텐츠를 숨기면 문서 구조에 영향을 미치나요?
아니요. 콘텐츠를 숨기면 공개 여부에만 영향을 미칩니다. 내용은 문서에 남아 있습니다.

### 다른 유형의 콘텐츠에 이 방법을 사용할 수 있나요?
이 방법은 특히 텍스트 실행을 전환합니다. 다른 콘텐츠 유형의 경우 노드 순회 논리를 수정해야 합니다.

### .NET용 Aspose.Words는 무료인가요?
 Aspose.Words는 무료 평가판을 제공합니다[여기](https://releases.aspose.com/) , 그러나 프로덕션 용도로 사용하려면 정식 라이센스가 필요합니다. 구매하시면 됩니다[여기](https://purchase.aspose.com/buy).

### 문제가 발생하면 어떻게 지원을 받을 수 있나요?
 Aspose 커뮤니티에서 지원을 받을 수 있습니다[여기](https://forum.aspose.com/c/words/8).