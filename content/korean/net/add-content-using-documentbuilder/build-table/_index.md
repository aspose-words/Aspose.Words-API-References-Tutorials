---
title: Word 문서에서 테이블 작성
linktitle: Word 문서에서 테이블 작성
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 테이블을 작성하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/build-table/
---
이 단계별 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 테이블을 작성하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 DocumentBuilder 클래스를 사용하여 사용자 정의 형식과 내용이 포함된 테이블을 만들 수 있습니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 새 문서 만들기
시작하려면 Document 클래스를 사용하여 새 문서를 만듭니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 테이블 시작
다음으로 DocumentBuilder 클래스의 StartTable 메서드를 사용하여 테이블 작성을 시작합니다.

```csharp
Table table = builder.StartTable();
```

## 3단계: 셀 삽입 및 콘텐츠 추가
이제 DocumentBuilder 클래스의 InsertCell 및 Write 메서드를 사용하여 테이블에 셀을 삽입하고 내용을 추가할 수 있습니다. 필요에 따라 셀 서식을 사용자 정의합니다.

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## 4단계: 행 종료
첫 번째 행의 셀에 내용을 추가한 후 DocumentBuilder 클래스의 EndRow 메서드를 사용하여 행을 끝냅니다.

```csharp
builder.EndRow();
```

## 5단계: 행 서식 사용자 정의
RowFormat 및 CellFormat 객체의 속성을 설정하여 행 형식을 사용자 정의할 수 있습니다.

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## 6단계: 테이블 종료
테이블을 완성하려면 DocumentBuilder 클래스의 EndTable 메서드를 사용하세요.

```csharp
builder.EndTable();
```

### .NET용 Aspose.Words를 사용하여 테이블을 작성하기 위한 예제 소스 코드
다음은 .NET용 Aspose.Words를 사용하여 테이블을 작성하기 위한 전체 소스 코드입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## 결론
축하해요! Aspose.Words for .NET을 사용하여 Word 문서에서 테이블을 작성하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 사용자 정의 형식으로 테이블을 만들 수 있습니다.

### Word 문서의 테이블 빌드에 대한 FAQ

#### Q: .NET용 Aspose.Words가 무엇인가요?

A: Aspose.Words for .NET은 개발자가 .NET 애플리케이션에서 Microsoft Word 문서를 프로그래밍 방식으로 생성, 읽기, 편집 및 변환할 수 있는 강력한 문서 처리 라이브러리입니다. 텍스트 조작, 표 생성, 문서 보호, 서식 등과 같은 Word 문서 작업에 필요한 다양한 기능을 제공합니다.

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서에서 표를 어떻게 만들 수 있나요?

A: .NET용 Aspose.Words를 사용하여 Word 문서에 테이블을 작성하려면 다음 단계를 따르세요.
1.  새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 물체.
2.  사용`StartTable` 의 방법`DocumentBuilder`테이블 만들기를 시작하는 수업입니다.
3.  테이블에 셀을 삽입하고`InsertCell` 그리고`Write` 방법`DocumentBuilder` 수업.
4.  다음을 사용하여 행을 종료합니다.`EndRow` 의 방법`DocumentBuilder` 수업.
5.  속성을 설정하여 행 형식을 사용자 정의합니다.`RowFormat` 그리고`CellFormat` 사물.
6.  다음을 사용하여 테이블을 종료합니다.`EndTable` 의 방법`DocumentBuilder` 수업.
7. 문서를 저장합니다.

#### Q: 표와 해당 셀의 서식을 어떻게 사용자 정의할 수 있나요?

 A: 테이블의 다양한 속성을 설정하여 테이블과 해당 셀의 서식을 사용자 정의할 수 있습니다.`RowFormat` 그리고`CellFormat` 사물. 예를 들어 셀 정렬, 수직 및 수평 텍스트 방향, 셀 높이, 행 높이 등을 조정할 수 있습니다. 이러한 속성을 사용하면 테이블과 해당 내용에 대해 원하는 모양을 얻을 수 있습니다.

#### Q: 병합된 셀과 기타 고급 기능을 사용하여 복잡한 테이블을 만들 수 있습니까?

 A: 예, Aspose.Words for .NET은 병합된 셀, 중첩 테이블 및 복잡한 테이블 레이아웃에 대한 지원을 포함하여 복잡한 테이블을 구축하는 고급 기능을 제공합니다. 당신은 사용할 수 있습니다`MergeCells` 셀을 병합하는 방법,`StartTable`중첩된 테이블을 만드는 방법과 원하는 테이블 구조를 얻는 다른 방법이 있습니다.

#### Q: Aspose.Words for .NET은 다른 Word 문서 형식과 호환됩니까?

A: 예, Aspose.Words for .NET은 DOC, DOCX, RTF 등을 포함한 다양한 Word 문서 형식과 호환됩니다. 레거시 형식(DOC)과 최신 XML 기반 형식(DOCX)을 모두 지원하며 문제 없이 다양한 형식의 문서 작업을 수행할 수 있습니다.

#### Q: Aspose.Words for .NET에 대한 추가 정보와 문서는 어디서 찾을 수 있나요?

 A: 다음에서 포괄적인 문서와 코드 예제를 찾을 수 있습니다.[API 참조](https://reference.aspose.com/words/net/). 설명서에서는 라이브러리 기능과 이를 .NET 애플리케이션에서 사용하는 방법에 대한 자세한 정보를 제공합니다.