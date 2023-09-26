---
title: Using VBA Macros in Aspose.Words for Java
linktitle: Using VBA Macros in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 25
url: /java/using-document-elements/using-vba-macros/
---

## Complete Source Code
```java
        Document doc = new Document();
        VbaProject project = new VbaProject();
        project.setName("AsposeProject");
        doc.setVbaProject(project);
        // Create a new module and specify a macro source code.
        VbaModule module = new VbaModule();
        module.setName("AsposeModule");
        module.setType(VbaModuleType.PROCEDURAL_MODULE);
        module.setSourceCode("New source code");
        // Add module to the VBA project.
        doc.getVbaProject().getModules().add(module);
        doc.save(getArtifactsDir() + "WorkingWithVba.CreateVbaProject.docm");
    }
    @Test
    public void readVbaMacros() throws Exception
    {
        Document doc = new Document(getMyDir() + "VBA project.docm");
        if (doc.getVbaProject() != null)
        {
            for (VbaModule module : doc.getVbaProject().getModules())
            {
                System.out.println(module.getSourceCode());
            }
        }
    }
    @Test
    public void modifyVbaMacros() throws Exception
    {
        Document doc = new Document(getMyDir() + "VBA project.docm");
        VbaProject project = doc.getVbaProject();
        final String NEW_SOURCE_CODE = "Test change source code";
        project.getModules().get(0).setSourceCode(NEW_SOURCE_CODE);
        doc.save(getArtifactsDir() + "WorkingWithVba.ModifyVbaMacros.docm");
    }
    @Test
    public void cloneVbaProject() throws Exception
    {
        Document doc = new Document(getMyDir() + "VBA project.docm");
        Document destDoc = new Document(); { destDoc.setVbaProject(doc.getVbaProject().deepClone()); }
        destDoc.save(getArtifactsDir() + "WorkingWithVba.CloneVbaProject.docm");
    }
    @Test
    public void cloneVbaModule() throws Exception
    {
        Document doc = new Document(getMyDir() + "VBA project.docm");
        Document destDoc = new Document(); { destDoc.setVbaProject(new VbaProject()); }
        VbaModule copyModule = doc.getVbaProject().getModules().get("Module1").deepClone();
        destDoc.getVbaProject().getModules().add(copyModule);
        destDoc.save(getArtifactsDir() + "WorkingWithVba.CloneVbaModule.docm");
    }
    @Test
    public void removeBrokenRef() throws Exception
    {
        Document doc = new Document(getMyDir() + "VBA project.docm");
        // Find and remove the reference with some LibId path.
        final String BROKEN_PATH = "brokenPath.dll";
        VbaReferenceCollection references = doc.getVbaProject().getReferences();
        for (int i = references.getCount() - 1; i >= 0; i--)
        {
            VbaReference reference = doc.getVbaProject().getReferences().get(i);
            String path = getLibIdPath(reference);
            if (BROKEN_PATH.equals(path))
                references.removeAt(i);
        }
        doc.save(getArtifactsDir() + "WorkingWithVba.RemoveBrokenRef.docm");
    }
    /// <summary>
    /// Returns string representing LibId path of a specified reference. 
    /// </summary>
    private String getLibIdPath(VbaReference reference)
    {
        switch (reference.getType())
        {
            case VbaReferenceType.REGISTERED:
            case VbaReferenceType.ORIGINAL:
            case VbaReferenceType.CONTROL:
                return getLibIdReferencePath(reference.getLibId());
            case VbaReferenceType.PROJECT:
                return getLibIdProjectPath(reference.getLibId());
            default:
                throw new IllegalArgumentException();
        }
    }
    /// <summary>
    /// Returns path from a specified identifier of an Automation type library.
    /// </summary>
    /// <remarks>
    /// Please see details for the syntax at [MS-OVBA], 2.1.1.8 LibidReference. 
    /// </remarks>
    private String getLibIdReferencePath(String libIdReference)
    {
        if (libIdReference != null)
        {
            String[] refParts = libIdReference.split("#");
            if (refParts.length > 3)
                return refParts[3];
        }
        return "";
    }
    /// <summary>
    /// Returns path from a specified identifier of an Automation type library.
    /// </summary>
    /// <remarks>
    /// Please see details for the syntax at [MS-OVBA], 2.1.1.12 ProjectReference. 
    /// </remarks>
    private String getLibIdProjectPath(String libIdProject)
    {
        return (libIdProject != null) ? libIdProject.substring(3) : "";
```
