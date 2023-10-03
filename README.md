# **Assignment3_WebGL**

Nama : Ken Anargya Alkausar  
NRP  : 5025211168  
Kelas : Grafika Komputer A

## Soal 1
Membuat sebuah persegi dengan cara menggabungkan dua buah segitiga menggunakan Web-GL.  
  - Berikut merupakan perubahan codingan yang saya lakukan untuk memnggabungkan 2 segitiga menjadi persegi

```
function draw() { 

    gl.clearColor(0,0,0,1);  // specify the color to be used for clearing
    gl.clear(gl.COLOR_BUFFER_BIT);  // clear the canvas (to black)

    /* Set up values for the "coords" attribute */

    let  coords = new Float32Array( [ -0.5,-0.5, 0.5,-0.5, -0.5,0.5 ] );
   
    gl.bindBuffer(gl.ARRAY_BUFFER, bufferCoords);
    gl.bufferData(gl.ARRAY_BUFFER, coords, gl.STREAM_DRAW);
    gl.vertexAttribPointer(attributeCoords, 2, gl.FLOAT, false, 0, 0);
    gl.enableVertexAttribArray(attributeCoords); 
   
    /* Set up values for the "color" attribute */
   
    let  color = new Float32Array( [ 0,0,1, 0,1,0, 1,0,0 ] );

    gl.bindBuffer(gl.ARRAY_BUFFER, bufferColor);
    gl.bufferData(gl.ARRAY_BUFFER, color, gl.STREAM_DRAW);
    gl.vertexAttribPointer(attributeColor, 3, gl.FLOAT, false, 0, 0);
    gl.enableVertexAttribArray(attributeColor); 
    
    /* Draw the triangle. */
   
    gl.drawArrays(gl.TRIANGLES, 0, 3);

    /* Set up values for the second triangle */
    let coords2 = new Float32Array([0.5, 0.5, -0.5, 0.5, 0.5, -0.5]);
    let color2 = new Float32Array([1, 1, 1, 1, 0, 0, 0, 1, 0]);

    gl.bindBuffer(gl.ARRAY_BUFFER, bufferCoords);
    gl.bufferData(gl.ARRAY_BUFFER, coords2, gl.STREAM_DRAW);
    gl.vertexAttribPointer(attributeCoords, 2, gl.FLOAT, false, 0, 0);
    gl.enableVertexAttribArray(attributeCoords);

    gl.bindBuffer(gl.ARRAY_BUFFER, bufferColor);
    gl.bufferData(gl.ARRAY_BUFFER, color2, gl.STREAM_DRAW);
    gl.vertexAttribPointer(attributeColor, 3, gl.FLOAT, false, 0, 0);
    gl.enableVertexAttribArray(attributeColor);

    gl.drawArrays(gl.TRIANGLES, 0, 3);

}
```



