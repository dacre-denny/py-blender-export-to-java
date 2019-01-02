# py-blender-export-to-java
A Blender add-on that allows geometric data for Mesh objects to be exported to a Java source file.

### Introduction

This exporter generates a Java source file containing the geometric data for one or more mesh objects in Blender. The exporter was a quick side project that was used during development of [this Android app](https://play.google.com/store/apps/details?id=nz.co.mooce.newzealandnative3d). 

The exporter writes geometric data for Mesh objects that are active/selected at the time of export. Vertex positions, vertex normals, and (if present)vertex texture coordinates are exported.

The structure of the exported Java source file is as follows:

```
public class ExportedFilename {

    public static class Mesh {

        private static float[] vertexPositions = {
            1.00f, -1.00f, 1.00f,
            1.00f, -1.00f, -1.00f,
            -1.00f, -1.00f, -1.00f,
            1.00f, -1.00f, 1.00f
        };

        private static float[] vertexNormals = 
        {
            0.00f, 0.00f, -1.00f,
            0.00f, 0.00f, -1.00f,
            0.00f, 0.00f, -1.00f,
            0.00f, 0.00f, -1.00f
        };
    
        private static float[] vertexUVs = 
        {
            0.00f, 0.00f,
            1.00f, 0.00f,
            1.00f, 1.00f,
            0.00f, 1.00f
        };
    }

    public static class Mesh_001 {

        private static float[] vertexPositions = {
            1.00f, -1.00f, 1.00f,
            1.00f, -1.00f, -1.00f,
            -1.00f, -1.00f, -1.00f
        };

        private static float[] vertexNormals = 
        {
            0.00f, 0.00f, -1.00f,
            0.00f, 0.00f, -1.00f,
            0.00f, 0.00f, -1.00f
        };
    
        private static float[] vertexUVs = 
        {
            0.00f, 0.00f,
            1.00f, 0.00f,
            1.00f, 1.00f
        };
    }
}
```

### Installation

Download [export-to-java.py](https://raw.githubusercontent.com/dacre-denny/py-blender-export-to-java/master/export-to-java.py) and follow [this guide](https://blender.stackexchange.com/a/1689) to install the script.

This Blender Add-on is listed under the Import-Export add-on category as "Export to Java (.java)":
![1](/doc/install-1.jpg)

### Usage

1. Select Mesh objects in your Blender scene to be exported to the Java source file.

2. From Blender's file menu, select "Java Source File (.java)" from the Export sub-menu:
![1](/doc/usage-1.jpg)

3. From the export dialog, the Package for the exported source file can be specified via the "Package Name" field (if no package name is provided "defaultpackage" will be used):
![1](/doc/usage-2.jpg)

4. Enter a filename for the source file and click "Export to Java":
![1](/doc/usage-3.jpg) 