---
title: Aspose.Words for Java에서 OLE 개체 및 ActiveX 컨트롤 사용
linktitle: OLE 개체 및 ActiveX 컨트롤 사용
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java에서 OLE 개체와 ActiveX 컨트롤을 사용하는 방법을 알아보세요. 대화형 문서를 쉽게 만드세요. 지금 시작하세요!
type: docs
weight: 21
url: /ko/java/using-document-elements/using-ole-objects-and-activex/
---
이 튜토리얼에서는 Aspose.Words for Java에서 OLE(Object Linking and Embedding) 개체와 ActiveX 컨트롤을 사용하여 작업하는 방법을 살펴보겠습니다. OLE 개체 및 ActiveX 컨트롤은 스프레드시트, 멀티미디어 파일 또는 대화형 컨트롤과 같은 외부 콘텐츠를 포함하거나 연결하여 문서를 향상시킬 수 있는 강력한 도구입니다. 코드 예제를 자세히 살펴보고 이러한 기능을 효과적으로 사용하는 방법을 알아보세요.

### 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  Aspose.Words for Java: Java 프로젝트에 Aspose.Words 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/java/).

2. Java 개발 환경: 시스템에 Java 개발 환경이 설정되어 있어야 합니다.

### OLE 개체 삽입

Word 문서에 OLE 개체를 삽입하는 것부터 시작해 보겠습니다. 간단한 Word 문서를 만든 다음 웹 페이지를 나타내는 OLE 개체를 삽입하겠습니다.

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

이 코드에서는 새 문서를 만들고 Aspose 웹 사이트를 표시하는 OLE 개체를 삽입합니다. URL을 원하는 콘텐츠로 바꿀 수 있습니다.

### OlePackage를 사용하여 OLE 개체 삽입

다음으로 OlePackage를 사용하여 OLE 개체를 삽입하는 방법을 살펴보겠습니다. 이를 통해 외부 파일을 문서에 OLE 개체로 포함할 수 있습니다.

```java
@Test
public void insertOleObjectWithOlePackage() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    byte[] bs = FileUtils.readFileToByteArray(new File("Your Directory Path" + "Zip file.zip"));
    try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
    {
        Shape shape = builder.insertOleObject(stream, "Package", true, null);
        OlePackage olePackage = shape.getOleFormat().getOlePackage();
        olePackage.setFileName("filename.zip");
        olePackage.setDisplayName("displayname.zip");
        doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
    }
}
```

이 예에서는 OlePackage를 사용하여 OLE 개체를 삽입하므로 외부 파일을 포함 개체로 포함할 수 있습니다.

### OLE 개체를 아이콘으로 삽입

이제 OLE 개체를 아이콘으로 삽입하는 방법을 살펴보겠습니다. 이는 포함된 파일을 나타내는 아이콘을 표시하려는 경우에 유용합니다.

```java
@Test
public void insertOleObjectAsIcon() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObjectAsIcon("Your Directory Path" + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico", "My embedded file");
    doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
}
```

이 코드에서는 OLE 개체를 아이콘으로 삽입하여 포함된 콘텐츠를 시각적으로 더욱 매력적으로 표현합니다.

### ActiveX 컨트롤 속성 읽기

이제 ActiveX 컨트롤로 초점을 옮겨 보겠습니다. Word 문서 내에서 ActiveX 컨트롤의 속성을 읽는 방법을 알아봅니다.

```java
@Test
public void readActiveXControlProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "ActiveX controls.docx");
    String properties = "";
    for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
    {
        if (shape.getOleFormat() == null) break;
        OleControl oleControl = shape.getOleFormat().getOleControl();
        if (oleControl.isForms2OleControl())
        {
            Forms2OleControl checkBox = (Forms2OleControl) oleControl;
            properties = properties + "\nCaption: " + checkBox.getCaption();
            properties = properties + "\nValue: " + checkBox.getValue();
            properties = properties + "\nEnabled: " + checkBox.getEnabled();
            properties = properties + "\nType: " + checkBox.getType();
            if (checkBox.getChildNodes() != null)
            {
                properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
            }
            properties += "\n";
        }
    }
    properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
    System.out.println("\n" + properties);
}
```

이 코드에서는 Word 문서의 도형을 반복하고 ActiveX 컨트롤을 식별하고 해당 속성을 검색합니다.

### 결론

축하해요! Aspose.Words for Java에서 OLE 객체와 ActiveX 컨트롤로 작업하는 방법을 배웠습니다. 이러한 기능은 역동적이고 대화형 문서를 생성할 수 있는 가능성의 세계를 열어줍니다.

### 자주 묻는 질문

### Word 문서에서 OLE 개체의 목적은 무엇입니까? 
   - OLE 개체를 사용하면 파일이나 웹 페이지와 같은 외부 콘텐츠를 Word 문서에 포함하거나 연결할 수 있습니다.

### 내 문서에서 OLE 개체의 모양을 사용자 정의할 수 있나요? 
   - 예, 아이콘 및 파일 이름 설정을 포함하여 OLE 개체의 모양을 사용자 정의할 수 있습니다.

### ActiveX 컨트롤이란 무엇이며 내 문서를 어떻게 향상시킬 수 있습니까? 
   - ActiveX 컨트롤은 양식 컨트롤이나 멀티미디어 플레이어와 같은 Word 문서에 기능을 추가할 수 있는 대화형 요소입니다.

### Aspose.Words for Java는 엔터프라이즈급 문서 자동화에 적합합니까? 
   - 예, Aspose.Words for Java는 Java 애플리케이션에서 문서 생성 및 조작을 자동화하는 강력한 라이브러리입니다.

### Java용 Aspose.Words에 어디서 액세스할 수 있나요? 
   -  Java용 Aspose.Words는 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/java/).

지금 Aspose.Words for Java를 시작하고 문서 자동화 및 사용자 정의의 잠재력을 최대한 활용하세요!
