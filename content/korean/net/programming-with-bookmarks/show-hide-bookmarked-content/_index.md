---
title: Word 문서에서 북마크된 콘텐츠 숨기기 표시
linktitle: Word 문서에서 북마크된 콘텐츠 숨기기 표시
second_title: Aspose.Words 문서 처리 API
description: 이 포괄적인 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 북마크된 콘텐츠를 동적으로 표시하거나 숨기는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## 소개

안녕하세요! 특정 조건에 따라 Word 문서 내 특정 콘텐츠의 표시 여부를 제어하고 싶었던 적이 있습니까? .NET용 Aspose.Words를 사용하면 단 몇 줄의 코드만으로 북마크된 콘텐츠를 동적으로 표시하거나 숨길 수 있습니다. 이 튜토리얼에서는 프로세스를 단계별로 안내하여 코드의 각 부분을 이해할 수 있도록 하겠습니다. 결국, 당신은 Word 문서에서 책갈피를 조작하는 전문가가 될 것입니다. 시작하자!

## 전제조건

튜토리얼을 시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.

1. C# 기본 지식: C# 구문과 개념에 익숙해야 합니다.
2.  .NET용 Aspose.Words: 다운로드[여기](https://releases.aspose.com/words/net/) . 구매할 준비가 되지 않았다면 다음 단계로 시작해 보세요.[무료 시험판](https://releases.aspose.com/).
3. Visual Studio: 모든 최신 버전이 작동하지만 최신 버전을 사용하는 것이 좋습니다.
4. .NET Framework: 컴퓨터에 설치되어 있는지 확인하세요.

시작할 준비가 되셨나요? 엄청난! 필요한 네임스페이스를 가져오는 것부터 시작해 보겠습니다.

## 네임스페이스 가져오기

.NET용 Aspose.Words를 사용하려면 필수 네임스페이스를 가져와야 합니다. 이 단계에서는 우리가 사용할 모든 클래스와 메서드에 액세스할 수 있는지 확인합니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

이러한 네임스페이스는 Word 문서로 작업하고 해당 내용을 조작하는 데 중요합니다.

## 1단계: 문서 설정

먼저 새 Word 문서와 문서 작성기를 만들어 보겠습니다. 문서 빌더를 사용하면 문서 내의 콘텐츠를 쉽게 추가하고 조작할 수 있습니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

이 단계에서는 새 문서와 문서 작성기를 초기화합니다. 이는 추가 작업을 위한 환경을 설정합니다.

## 2단계: 북마크된 콘텐츠 추가

다음으로 문서에 일부 내용을 추가하고 그 주위에 책갈피를 만듭니다. 이 북마크는 콘텐츠를 식별하고 조작하는 데 도움이 됩니다.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 여기서는 북마크된 콘텐츠 앞뒤에 텍스트를 추가합니다. 그만큼`StartBookmark` 그리고`EndBookmark` 메소드는 북마크의 경계를 정의합니다.

## 3단계: 조건부 필드 삽입

북마크된 콘텐츠의 가시성을 제어하기 위해 조건부 필드를 사용하겠습니다. 이 필드는 조건을 확인하고 그에 따라 내용을 표시하거나 숨깁니다.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

이 단계에서는 북마크 값을 확인하는 IF 필드를 삽입합니다. 값이 "true"이면 "Visible"이 표시됩니다. 그렇지 않으면 "숨김"이 표시됩니다.

## 4단계: 노드 재배열

다음으로 조건부 논리가 북마크된 콘텐츠에 올바르게 적용되도록 노드를 다시 정렬해야 합니다.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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
```

여기서는 조건이 북마크된 콘텐츠를 올바르게 포함하는지 확인하기 위해 노드를 이동합니다.

## 5단계: 메일 병합 실행

마지막으로 메일 병합을 실행하여 북마크 값을 설정하고 콘텐츠를 표시할지 숨길지 결정합니다.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

이 단계에서는 북마크 값을 "true"로 설정하여 조건에 따라 콘텐츠를 표시합니다.

## 6단계: 문서 저장

모든 조작이 끝나면 마지막 단계는 수정된 문서를 저장하는 것입니다.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

여기에서는 변경 사항을 나타내기 위해 설명적인 파일 이름으로 문서를 저장합니다.

## 결론

 그리고 그게 다야! Aspose.Words for .NET을 사용하여 Word 문서에서 북마크된 콘텐츠를 표시하거나 숨기는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 문서 작성, 북마크 추가, 조건 필드 삽입, 노드 재배치 및 메일 병합 실행을 다루었습니다. Aspose.Words는 다양한 기능을 제공하므로 주저하지 말고[API 문서](https://reference.aspose.com/words/net/) 더 발전된 기능을 위해.

## 자주 묻는 질문

### 1. .NET용 Aspose.Words란 무엇입니까?

Aspose.Words for .NET은 개발자가 프로그래밍 방식으로 Word 문서를 생성, 수정 및 변환할 수 있는 강력한 라이브러리입니다. 문서 자동화 작업에 널리 사용됩니다.

### 2. Aspose.Words for .NET을 무료로 사용할 수 있나요?

 다음을 사용하여 .NET용 Aspose.Words를 사용해 볼 수 있습니다.[무료 시험판](https://releases.aspose.com/). 장기간 사용하려면 라이센스를 구입해야 합니다.

### 3. 북마크의 다른 속성을 수정하려면 어떻게 해야 합니까?

 Aspose.Words를 사용하면 텍스트 및 위치와 같은 책갈피의 다양한 속성을 조작할 수 있습니다. 다음을 참조하세요.[API 문서](https://reference.aspose.com/words/net/) 자세한 지침을 보려면.

### 4. .NET용 Aspose.Words에 대한 지원을 받으려면 어떻게 해야 합니까?

방문하시면 지원을 받으실 수 있습니다.[Aspose 지원 포럼](https://forum.aspose.com/c/words/8).

### 5. Aspose.Words for .NET으로 다른 유형의 콘텐츠를 조작할 수 있나요?

예, Aspose.Words for .NET은 텍스트, 이미지, 표 등을 포함한 다양한 유형의 콘텐츠 조작을 지원합니다.