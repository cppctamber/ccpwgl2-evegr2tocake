# ccpwgl2-cake
Converts eve online `.gr2` files to a ccpwgl2 `.cake` format. 

# cake format
The base file format is a text file.
Each line represents a new element declaration.

###supported
* **Vertex Position**: POSITION:[Float, Float, Float]
* **Vertex Texture coordinates 0**: TEXCOORD0:[Float, Float]
* **Vertex Texture coordinates 1**: TEXCOORD1:[Float, Float]
* **Vertex Normal**: NORMAL:[Float, Float, Float]
* **Vertex Tangent**: TANGENT:[Float, Float, Float, Float]
* **Vertex BiTangent**: BITANGENT[Float, Float, Float, Float]
* **Area Name**: AREA:String (Directly proceeds its faces)
* **Area Face**: FACE:[Integer, Integer, Integer]

###unsupported
- Animations
- Curves
- Bones

#about
Based on `evegr2toobj.exe` who's author I cannot identify :(
I couldn't correctly calculate valid vertex tangents for eve online's shaders using `.obj` format so made this format instead.

#build
1. install MinGW
2. place `granny2.dll` into the MinGW `/lib` directory
3. if on windows add MinGW `/bin` directory to paths
4. `g++ main.cpp -o evegr2tocake.exe -l granny2` 

#usage
`evegr2tocake sourcefilename.gr2 destinationfilename.obj`
