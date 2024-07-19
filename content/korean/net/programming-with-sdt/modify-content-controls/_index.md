---
title: 콘텐츠 컨트롤 수정
linktitle: 콘텐츠 컨트롤 수정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 콘텐츠 컨트롤 내에서 텍스트, 드롭다운 목록 및 이미지를 수정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-sdt/modify-content-controls/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 다양한 유형의 콘텐츠 컨트롤을 수정하는 방법을 설명합니다. 텍스트, 드롭다운 목록의 선택한 값을 업데이트하거나 콘텐츠 컨트롤 내의 이미지를 바꿀 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드 및 콘텐츠 컨트롤 반복
 다음을 사용하여 Word 문서를 로드합니다.`Document` 생성자, 문서 경로를 매개변수로 전달합니다. 다음을 사용하여 문서의 모든 구조화된 문서 태그를 반복합니다.`foreach` 고리.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // 콘텐츠 제어 유형에 따라 작업 수행
}
```

## 3단계: 일반 텍스트 콘텐츠 제어 수정
 유형의 콘텐츠 컨트롤의 경우`SdtType.PlainText`, 기존 하위 항목을 모두 제거하고 새 단락을 만든 다음 원하는 텍스트가 포함된 실행을 추가합니다.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## 4단계: 드롭다운 목록 콘텐츠 제어 수정
 유형의 콘텐츠 컨트롤의 경우`SdtType.DropDownList` , 선택한 값을 특정 값으로 설정하여 업데이트합니다.`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## 5단계: 사진 콘텐츠 컨트롤 수정
 유형의 콘텐츠 컨트롤의 경우`SdtType.Picture`, 콘텐츠 컨트롤 내에서 모양을 검색하고 해당 이미지를 새 이미지로 바꿉니다.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## 6단계: 수정된 문서 저장
 수정된 문서를 다음을 사용하여 지정된 디렉터리에 저장합니다.`Save`방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithSdt.ModifyContentControls.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### .NET용 Aspose.Words를 사용하여 콘텐츠 컨트롤 수정에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

그게 다야! Aspose.Words for .NET을 사용하여 Word 문서에서 다양한 유형의 콘텐츠 컨트롤을 성공적으로 수정했습니다.