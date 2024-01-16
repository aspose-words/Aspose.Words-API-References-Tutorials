---
title: 외곽선 테두리 적용
linktitle: 외곽선 테두리 적용
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 테이블에 윤곽선 테두리를 적용하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 테이블에 윤곽선 테두리를 적용하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 Word 문서에서 표 테두리를 조작하는 방법을 명확하게 이해하게 될 것입니다.

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 여기에 Word 문서가 저장됩니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 업로드
 다음으로 Word 문서를 인스턴스로 로드해야 합니다.`Document` 수업.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3단계: 테이블에 액세스
 윤곽선 테두리를 적용하려면 문서의 테이블에 액세스해야 합니다. 그만큼`Table` 클래스는 Aspose.Words의 테이블을 나타냅니다.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## 4단계: 표를 페이지 중앙에 정렬
 이제 다음을 사용하여 테이블을 페이지 중앙에 정렬할 수 있습니다.`Alignment` 테이블의 속성입니다.

```csharp
table. Alignment = Table Alignment. Center;
```

## 5단계: 기존 표 테두리 지우기
새로운 윤곽선 테두리를 시작하려면 먼저 테이블에서 기존 테두리를 모두 지워야 합니다. 이 작업은 다음을 사용하여 수행할 수 있습니다.`ClearBorders()` 방법.

```csharp
table. ClearBorders();
```

## 6단계: 테이블 주위에 녹색 테두리 정의
 이제 다음을 사용하여 테이블 주위에 녹색 테두리를 설정할 수 있습니다.`SetBorder()` 테이블의 각 측면에 대한 방법입니다. 이 예에서는 두께가 1.5포인트이고 녹색인 "단일" 유형 테두리를 사용합니다.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## 7단계: 배경색으로 셀 채우기
테이블의 시각적 표현을 개선하기 위해 셀을 바탕 배경색으로 채울 수 있습니다.

아이디어. 이 예에서는 연한 녹색을 사용합니다.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## 8단계: 수정된 문서 저장
마지막으로 수정된 문서를 파일에 저장합니다. 출력 문서에 대한 적절한 이름과 위치를 선택할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

축하합니다! 이제 Aspose.Words for .NET을 사용하여 테이블에 윤곽선 테두리를 적용했습니다.

### .NET용 Aspose.Words를 사용하여 윤곽선 테두리 적용에 대한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// 표를 페이지 중앙에 맞춥니다.
	table.Alignment = TableAlignment.Center;
	//테이블에서 기존 테두리를 모두 지웁니다.
	table.ClearBorders();
	// 테이블 주위에 녹색 테두리를 설정하되 내부에는 설정하지 마세요.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// 연한 녹색 단색으로 셀을 채웁니다.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 테이블에 윤곽선 테두리를 적용하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 이 기능을 C# 프로젝트에 쉽게 통합할 수 있습니다. 테이블 형식을 조작하는 것은 문서 처리의 필수적인 측면이며 Aspose.Words는 이를 달성하기 위해 강력하고 유연한 API를 제공합니다. 이러한 지식을 통해 Word 문서의 시각적 표현을 개선하고 특정 요구 사항을 충족할 수 있습니다.