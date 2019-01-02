# py-blender-export-to-java
A Blender Add-on that allows geometric data for Mesh objects to be exported to a Java source file.

### Introduction

This exporter generates a Java source file containing the geometric data for one or more mesh objects in Blender. The exporter exports geometric data for Mesh objects that are active/selected at the time of export. Vertex positions, vertex normals, and vertex UV texture coordinates (if present) are exported.

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

Download the `export-to-java.py` script and follow [this guide](https://blender.stackexchange.com/a/1689) to install the script.

This Blender Add-on is listed under the "Import-Export" Add-on category "Export to Java (.java)":
![1](/doc/install-1.jpg)

### Usage

1. Select the Mesh objects in your project that are to be exported to a Java source file.

2. From Blender's file menu, select Java Source File from the Export menu:
![1](/doc/usage-1.jpg)

3. From the export dialog, the Java Package for the exported source file can be specified via the "Package Name" field (if no package name is provided "defaultpackage" will be used):
![1](/doc/usage-2.jpg)

4. Enter a filename and click "Export to Java":
![1](/doc/usage-3.jpg) 