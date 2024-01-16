---
title: 앵커댓글
linktitle: 앵커댓글
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 특정 텍스트에 주석 응답을 고정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-comments/anchor-comment/
---

이 포괄적인 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 특정 텍스트에 주석 응답을 고정하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 주석을 문서의 특정 텍스트와 연결할 수 있게 됩니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 새 문서 만들기 및 텍스트 추가
시작하려면 Document 클래스를 사용하여 새 문서를 만들고 원하는 텍스트를 추가합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## 2단계: 댓글 생성 및 댓글 범위 추가
다음으로 CommentRangeStart 및 CommentRangeEnd 개체를 사용하여 주석을 만들고 이를 특정 텍스트와 연결합니다.

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## 3단계: 문서 저장
주석을 특정 텍스트에 고정한 후 Document 클래스의 Save 메서드를 사용하여 문서를 파일에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### .NET용 Aspose.Words를 사용하는 앵커 댓글 응답의 소스 코드 예
다음은 .NET용 Aspose.Words를 사용하여 댓글 응답을 고정하기 위한 전체 소스 코드입니다.

```csharp
// 문서의 인스턴스를 만듭니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// 세 개의 Run 개체를 만듭니다.
// 처음 두 개는 텍스트를 실행하고 세 번째는 설명을 실행합니다.

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// 각 Run 개체에는 연결된 CommentRangeStart 및 CommentRangeEnd 개체가 있습니다.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### FAQ

#### Q: Aspose.Words for .NET의 댓글 앵커란 무엇입니까?

A: Aspose.Words for .NET에서 주석 앵커는 주석을 문서의 특정 위치에 연결하는 표식입니다.

#### Q: Aspose.Words for .NET 문서에 주석 앵커를 어떻게 추가할 수 있나요?

A: Aspose.Words for .NET 문서에 주석 앵커를 추가하려면 튜토리얼에 언급된 단계를 따르세요.

#### Q: .NET용 Aspose.Words의 기존 주석 앵커에 어떻게 액세스합니까?

 A: Aspose.Words for .NET의 기존 주석 앵커에 액세스할 수 있습니다.`Comment.Anchor` 재산.

#### Q: Aspose.Words for .NET에서 댓글 앵커를 제공할 수 있나요?

 A: 예, Aspose.Words for .NET에서 다음을 사용하여 주석 앵커를 제거할 수 있습니다.`Comment.Remove` 방법.

#### Q: Aspose.Words for .NET의 댓글 앵커에 연결된 댓글 텍스트를 어떻게 편집할 수 있나요?

 A: .NET용 Aspose.Words의 주석 앵커에 바인딩된 주석 텍스트를 수정하려면`Comment.Text` 해당 속성`Comment` 개체를 선택하고 필요에 따라 텍스트를 수정합니다.

