---
title: 테이블 내용 정렬을 사용하여 마크다운으로 내보내기
linktitle: 테이블 내용 정렬을 사용하여 마크다운으로 내보내기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 다양한 정렬로 테이블 콘텐츠를 Markdown 파일로 내보내는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
다음은 .NET용 Aspose.Words 라이브러리를 사용하여 테이블 콘텐츠 정렬을 통해 콘텐츠를 Markdown 파일로 내보내는 데 도움이 되는 다음 C# 소스 코드를 설명하는 단계별 가이드입니다. 이 코드를 사용하기 전에 프로젝트에 Aspose.Words 라이브러리를 포함했는지 확인하세요.

## 1단계: 문서 디렉터리 경로 설정

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

편집된 문서가 저장될 문서 디렉토리의 올바른 경로를 지정하십시오.

## 2단계: 문서 및 문서 생성기 만들기

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 여기서 우리는`Document` 클래스와 인스턴스`DocumentBuilder` 문서를 조작하고 요소를 추가할 수 있는 클래스입니다.

## 3단계: 단락 정렬이 다른 표에 셀 삽입

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

문서 작성기를 사용하여 테이블에 셀을 삽입하고 각 셀에 대해 서로 다른 단락 정렬을 설정합니다.

## 4단계: Markdown 내보내기 옵션 설정 및 수정된 문서 저장

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

다양한 테이블 내용 정렬로 Markdown 내보내기 옵션을 설정한 다음 각 정렬 옵션을 사용하여 수정된 문서를 저장합니다.

### .NET용 Aspose.Words를 사용하여 테이블 내용 정렬과 함께 Markdown으로 내보내는 예제 소스 코드

```csharp

            
	// 문서 디렉터리의 경로입니다.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// 표 안의 모든 단락을 정렬합니다.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// 이 경우 정렬은 해당 표 열의 첫 번째 단락에서 가져옵니다.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// 수정된 문서를 저장하세요
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
