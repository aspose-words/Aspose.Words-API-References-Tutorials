---
title: Word 문서에 Ole 개체 삽입
linktitle: Word 문서에 Ole 개체 삽입
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에 OLE 개체를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-oleobjects-and-activex/insert-ole-object/
---

다음은 .NET용 Aspose.Words를 사용하여 Word 문서에 OLE 개체를 삽입하는 방법을 보여주는 C# 소스 코드를 설명하는 단계별 가이드입니다.

## 1단계: 필요한 참조 가져오기
시작하기 전에 Aspose.Words for .NET을 사용하는 데 필요한 참조를 프로젝트에 가져왔는지 확인하세요. 여기에는 Aspose.Words 라이브러리를 가져오고 소스 파일에 필요한 네임스페이스를 추가하는 작업이 포함됩니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 2단계: 새 문서 및 문서 생성기 만들기
 이 단계에서는 다음을 사용하여 새 문서를 만듭니다.`Document` 클래스와 문서 작성기를 사용하는`DocumentBuilder` 수업.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: OLE 개체 삽입
 문서 작성기 사용`InsertOleObject`문서에 OLE 개체를 삽입하는 방법입니다. OLE 개체 URL, 개체 유형, 표시 옵션 및 기타 필요한 설정을 지정합니다.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

## 4단계: 문서 저장
 문서의 내용을 사용하세요`Save` 문서를 파일로 저장하는 방법입니다.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### .NET용 Aspose.Words를 사용하여 OLE 개체를 삽입하기 위한 예제 소스 코드

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

이것은 .NET용 Aspose.Words를 사용하여 OLE 개체를 삽입하기 위한 완전한 코드 샘플입니다. 필요한 참조를 가져오고 이전에 설명한 단계에 따라 이 코드를 프로젝트에 통합하십시오.

## 결론

결론적으로, Word 문서에 OLE 개체를 삽입하는 것은 Aspose.Words for .NET이 제공하는 강력한 기능입니다. 이 라이브러리를 사용하면 HTML 파일, Excel 스프레드시트, PowerPoint 프레젠테이션 등과 같은 OLE 개체를 Word 문서에 쉽게 포함할 수 있습니다.

이 기사에서는 Word 문서에 OLE 개체를 삽입하는 방법을 보여주는 C# 소스 코드를 단계별로 설명했습니다. 필요한 참조, 새 문서 및 문서 생성기 만들기, OLE 개체 삽입 및 문서 저장 단계를 다루었습니다.

### Word 문서에 OLE 개체를 삽입하는 데 대한 FAQ

#### Q: Aspose.Words for .NET을 사용하려면 어떤 자격 증명을 가져와야 합니까?

A: .NET용 Aspose.Words를 사용하려면 다음 참조를 가져와야 합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q: 새 문서와 문서 생성기를 만드는 방법은 무엇입니까?

 A: 다음을 사용하여 새 문서를 만들 수 있습니다.`Document` 클래스와 문서 작성기를 사용하는`DocumentBuilder` 클래스는 아래와 같습니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q: 문서에 OLE 개체를 삽입하는 방법은 무엇입니까?

 답변:`InsertOleObject` 문서 작성기의 메소드(`DocumentBuilder`) 문서에 OLE 개체를 삽입합니다. OLE 개체 URL, 개체 유형, 표시 옵션 및 기타 필요한 설정을 지정합니다. 예는 다음과 같습니다.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

#### Q: 문서를 어떻게 저장하나요?

 A: 문서를 사용하세요`Save`문서를 파일로 저장하는 방법입니다. 예는 다음과 같습니다.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### Q: .NET용 Aspose.Words를 사용하여 OLE 개체를 삽입하는 완전한 예를 제공할 수 있습니까?

A: 다음은 .NET용 Aspose.Words를 사용하여 OLE 개체를 삽입하는 전체 샘플 코드입니다. 필요한 참조를 가져오고 이전에 설명한 단계에 따라 이 코드를 프로젝트에 통합해야 합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
