---
title: 앵커댓글
linktitle: 앵커댓글
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 앵커 주석을 추가하는 방법을 알아보세요. 효율적인 문서 협업을 위한 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/working-with-comments/anchor-comment/
---
## 소개

프로그래밍 방식으로 Word 문서의 특정 텍스트 섹션에 설명을 추가해야 하는 상황에 처한 적이 있습니까? 팀과 함께 문서를 공동 작업하고 있는데 다른 사람이 검토할 수 있도록 주석으로 특정 부분을 강조 표시해야 한다고 가정해 보세요. 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 앵커 주석을 삽입하는 방법에 대해 자세히 알아봅니다. 프로세스를 간단한 단계로 나누어 프로젝트를 쉽게 따라하고 구현할 수 있도록 하겠습니다.

## 전제 조건

시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.

-  .NET용 Aspose.Words: Aspose.Words 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 모든 .NET 개발 환경.
- C#에 대한 기본 이해: C# 프로그래밍에 익숙하면 단계를 쉽게 수행하는 데 도움이 됩니다.

이제 이 작업을 위해 가져와야 하는 네임스페이스에 대해 자세히 살펴보겠습니다.

## 네임스페이스 가져오기

우선 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 필수 네임스페이스는 다음과 같습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.CommentRangeStart;
using Aspose.Words.CommentRangeEnd;
```

전제 조건과 네임스페이스를 제거하고 재미있는 부분으로 넘어가겠습니다. 즉, 프로세스를 단계별로 분석해 보겠습니다.

## 1단계: 새 문서 만들기

먼저 새 Word 문서를 만들어 보겠습니다. 이는 우리의 의견을 위한 캔버스 역할을 할 것입니다.

```csharp
// 문서가 저장될 디렉터리를 정의합니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";        

// Document 클래스의 인스턴스 만들기
Document doc = new Document();
```

 이 단계에서는 새로운 것을 초기화합니다.`Document` 코멘트를 추가하는 데 사용될 객체입니다.

## 2단계: 문서에 텍스트 추가

다음으로 문서에 텍스트를 추가하겠습니다. 이 텍스트가 우리 의견의 대상이 될 것입니다.

```csharp
// 첫 번째 단락을 만들고 실행합니다.
Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

// 두 번째 단락을 만들고 실행합니다.
Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

 여기서는 일부 텍스트로 두 개의 단락을 만듭니다. 각 텍스트 조각은`Run` 개체가 단락에 추가됩니다.

## 3단계: 댓글 작성

이제 텍스트에 첨부할 주석을 작성해 보겠습니다.

```csharp
// 새 댓글 작성
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

 이 단계에서는`Comment` 개체를 선택하고 단락과 주석 텍스트가 포함된 실행을 추가합니다.

## 4단계: 설명 범위 정의

주석을 특정 텍스트에 고정하려면 주석 범위의 시작과 끝을 정의해야 합니다.

```csharp
// CommentRangeStart 및 CommentRangeEnd 정의
CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

// CommentRangeStart 및 CommentRangeEnd를 문서에 삽입합니다.
run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);

// 문서에 댓글 추가
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

 여기에서 우리는`CommentRangeStart`그리고`CommentRangeEnd` 객체를 해당 ID로 댓글에 연결합니다. 그런 다음 이러한 범위를 문서에 삽입하여 주석을 지정된 텍스트에 효과적으로 고정시킵니다.

## 5단계: 문서 저장

마지막으로 문서를 지정된 디렉터리에 저장해 보겠습니다.

```csharp
// 문서 저장
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

이 단계에서는 고정된 주석이 포함된 문서를 지정된 디렉터리에 저장합니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서의 특정 텍스트 섹션에 앵커 주석을 추가하는 방법을 성공적으로 배웠습니다. 이 기술은 문서 공동 작업에 매우 유용하므로 텍스트의 특정 부분을 쉽게 강조 표시하고 설명을 추가할 수 있습니다. 팀과 함께 프로젝트를 진행하든 문서를 검토하든 이 방법을 사용하면 생산성이 향상되고 작업 흐름이 간소화됩니다.

## FAQ

### Word 문서에서 앵커 주석을 사용하는 목적은 무엇입니까?
앵커 댓글은 텍스트의 특정 섹션을 강조하고 설명하는 데 사용되므로 보다 쉽게 피드백을 제공하고 문서에 대한 공동 작업을 수행할 수 있습니다.

### 동일한 텍스트 섹션에 여러 댓글을 추가할 수 있나요?
예, 여러 댓글 범위를 정의하여 동일한 텍스트 섹션에 여러 댓글을 추가할 수 있습니다.

### .NET용 Aspose.Words는 무료로 사용할 수 있나요?
Aspose.Words for .NET은 다운로드할 수 있는 무료 평가판을 제공합니다.[여기](https://releases.aspose.com/) . 전체 기능을 이용하려면 라이센스를 구매하세요[여기](https://purchase.aspose.com/buy).

### 댓글 모양을 맞춤설정할 수 있나요?
Aspose.Words는 기능에 중점을 두지만 Word 문서의 주석 모양은 일반적으로 Word 자체에서 제어됩니다.

### .NET용 Aspose.Words에 대한 추가 문서는 어디서 찾을 수 있나요?
 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/words/net/).