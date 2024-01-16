---
title: 병합 필드 이름 바꾸기
linktitle: 병합 필드 이름 바꾸기
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서에서 병합 필드의 이름을 바꾸는 방법을 배웁니다.
type: docs
weight: 10
url: /ko/net/working-with-fields/rename-merge-fields/
---

다음은 .NET용 Aspose.Words의 병합 필드 이름 변경 기능을 사용하는 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

## 1단계: 문서 디렉터리 설정

제공된 코드에서 문서의 디렉터리를 지정해야 합니다. "YOUR DOCUMENT DIRECTORY" 값을 문서 디렉토리에 대한 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 만들기 및 병합 필드 삽입

새 문서를 만들고`DocumentBuilder` 병합 필드를 삽입합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## 3단계: 병합 필드 이름 바꾸기

문서 범위의 각 필드를 반복하고 병합 필드인 경우 "를 추가하여 필드 이름을 바꿉니다._이름이 변경되었습니다." 접미사.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## 4단계: 문서 저장

 마지막으로 우리는`Save()` 수정된 문서를 저장하는 방법입니다.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### .NET용 Aspose.Words를 사용하여 병합 필드 이름을 바꾸는 소스 코드 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 만들고 병합 필드를 삽입합니다.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// 병합 필드의 이름을 바꿉니다.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// 문서를 저장합니다.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

.NET용 Aspose.Words를 사용하여 문서의 병합 필드 이름을 바꾸려면 다음 단계를 따르세요.

### FAQ

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서에서 병합된 필드의 이름을 어떻게 바꿀 수 있습니까?

 A: .NET용 Aspose.Words를 사용하여 Word 문서에서 병합된 필드의 이름을 바꾸려면 다음을 사용하여 문서의 필드를 반복할 수 있습니다.`FieldMergingArgs` 클래스를 사용하고`FieldMergingArgs.FieldName` 필드 이름을 바꾸는 방법.

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서에서 병합된 특정 필드만 이름을 바꿀 수 있습니까?

A: 예, Aspose.Words for .NET을 사용하면 Word 문서에서 병합된 특정 필드만 이름을 바꿀 수 있습니다. 필드 이름이나 기타 관련 속성과 같은 특정 기준을 사용하여 이름을 바꿀 필드를 필터링할 수 있습니다. 그런 다음 다음을 사용하여 해당 필드의 이름을 바꿀 수 있습니다.`FieldMergingArgs.FieldName` 방법.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 병합된 필드의 이름이 성공적으로 바뀌었는지 어떻게 확인할 수 있나요?

 A: .NET용 Aspose.Words를 사용하여 Word 문서에서 병합된 필드의 이름이 성공적으로 변경되었는지 확인하려면 다음을 사용할 수 있습니다.`FieldMergedArgs` 수업을 듣고 액세스`FieldMergedArgs.IsMerged` 적중으로 필드 이름이 바뀌었는지 확인하는 속성입니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 병합된 필드의 이름을 바꾸면 어떤 결과가 발생합니까?

A: .NET용 Aspose.Words를 사용하여 Word 문서에서 병합된 필드의 이름을 바꾸면 문서의 필드 이름이 변경되어 필드 이름에 의존하는 다른 기능이나 프로세스에 영향을 미칠 수 있습니다. 병합된 필드의 이름을 바꾸기 전에 이러한 잠재적인 결과를 고려해야 합니다.

#### Q: .NET용 Aspose.Words를 사용하여 이름을 바꾼 후 병합된 필드의 원래 이름을 복원할 수 있습니까?

A: 예, .NET용 Aspose.Words를 사용하여 이름을 바꾼 후 병합된 필드의 원래 이름을 복원할 수 있습니다. 필드의 원래 이름을 변수나 목록에 저장한 다음 필요한 경우 해당 정보를 사용하여 원래 이름을 복원할 수 있습니다.