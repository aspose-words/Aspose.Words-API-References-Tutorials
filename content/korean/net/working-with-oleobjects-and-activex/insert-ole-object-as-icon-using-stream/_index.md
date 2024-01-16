---
title: 스트림을 사용하여 Ole 객체를 아이콘으로 삽입
linktitle: 스트림을 사용하여 Ole 객체를 아이콘으로 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words가 포함된 스트림을 사용하여 OLE 개체를 아이콘으로 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

다음은 .NET용 Aspose.Words가 포함된 스트림을 사용하여 OLE 개체를 아이콘으로 삽입하는 방법을 보여주는 C# 소스 코드를 설명하는 단계별 가이드입니다.

## 1단계: 필요한 참조 가져오기
시작하기 전에 Aspose.Words for .NET을 사용하는 데 필요한 참조를 프로젝트에 가져왔는지 확인하세요. 여기에는 Aspose.Words 라이브러리를 가져오고 소스 파일에 필요한 네임스페이스를 추가하는 작업이 포함됩니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## 2단계: 새 문서 및 문서 생성기 만들기
 이 단계에서는 다음을 사용하여 새 문서를 만듭니다.`Document` 클래스와 문서 작성기를 사용하는`DocumentBuilder` 수업.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 스트림에서 OLE 개체를 아이콘으로 삽입
 문서 작성기 사용`InsertOleObjectAsIcon` 스트림의 아이콘으로 OLE 개체를 문서에 삽입하는 방법입니다. 데이터 스트림, 개체 유형, 아이콘 경로 및 포함된 개체 이름을 지정합니다.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## 4단계: 문서 저장
 문서의 내용을 사용하세요`Save` 문서를 파일로 저장하는 방법입니다.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### .NET용 Aspose.Words가 포함된 스트림을 사용하여 OLE 개체를 아이콘으로 삽입하기 위한 예제 소스 코드

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

이것은 .NET용 Aspose.Words가 포함된 스트림을 사용하여 OLE 개체를 아이콘으로 삽입하기 위한 전체 코드 샘플입니다. 필요한 참조를 가져오고 이전에 설명한 단계에 따라 이 코드를 프로젝트에 통합하십시오.

## 결론

위의 단계별 가이드에서는 Aspose.Words for .NET의 흐름을 사용하여 Word 문서에 OLE 개체를 아이콘으로 삽입하는 방법을 설명합니다. 설명된 단계를 따르면 이 기능을 프로젝트에 통합할 수 있습니다. 필요한 참조를 가져오고, 새 문서 및 문서 생성기를 만들고, OLE 개체를 스트림의 아이콘으로 삽입한 다음 문서를 저장하십시오. 제공된 샘플 코드를 시작점으로 사용하고 필요에 맞게 사용자 정의하세요.

### FAQ

#### Q. Aspose.Words for .NET을 사용하기 위해 필요한 참조를 어떻게 가져오나요?

A. 필요한 참조를 가져오려면 다음 단계를 수행해야 합니다.

 다음을 추가하세요`using` 소스 파일 상단에 있는 명령문:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
프로젝트에 Aspose.Words 라이브러리를 추가했는지 확인하세요.

#### Q. Aspose.Words for .NET을 사용하여 새 문서 및 문서 빌더를 만드는 방법은 무엇입니까?

A. 새 문서 및 문서 생성기를 만들려면 다음 단계를 따르세요.

 사용`Document` 새 문서를 생성하는 클래스:

```csharp
Document doc = new Document();
```
 사용`DocumentBuilder`이전에 생성된 문서와 연결된 문서 빌더를 생성하는 클래스:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. Aspose.Words for .NET을 사용하여 스트림에서 OLE 개체를 아이콘으로 삽입하는 방법은 무엇입니까?

A. OLE 개체를 스트림의 아이콘으로 삽입하려면 다음 단계를 수행하세요.

 사용`InsertOleObjectAsIcon` OLE 개체를 삽입하는 문서 생성기의 메서드:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### Q. 문서를 파일로 저장하는 방법은 무엇인가요?

A.  문서를 파일로 저장하려면`Save` 대상 경로를 지정하는 문서의 메소드:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Q. 스트림의 아이콘으로 OLE 개체를 내 프로젝트에 삽입하기 위한 코드를 어떻게 포함합니까?

A. OLE 개체를 스트림의 아이콘으로 프로젝트에 삽입하기 위한 코드를 포함하려면 다음 단계를 따르세요.
-  적절한 참조를 추가하여 필요한 참조를 가져옵니다.`using` 진술.
-  다음을 사용하여 새 문서와 문서 작성기를 만듭니다.`Document` 그리고`DocumentBuilder` 클래스.
- 스트림에서 OLE 개체를 아이콘으로 삽입하는 코드를 사용합니다.
-  다음을 사용하여 문서를 저장합니다.`Save` 적절한 대상 경로를 사용하는 메소드입니다.

다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 스트림에서 아이콘으로 OLE 개체를 성공적으로 삽입할 수 있습니다. 원하는 결과를 얻으려면 지침을 따르고 필요한 참조를 가져와야 합니다.