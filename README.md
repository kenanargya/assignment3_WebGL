# **Assignment3_WebGL**

Nama : Ken Anargya Alkausar  
NRP  : 5025211168  
Kelas : Grafika Komputer A

## Soal 1
Membuat sebuah persegi dengan cara menggabungkan dua buah segitiga menggunakan Web-GL.  
  - Berikut merupakan codingan yang saya ubah untuk menggabungkan 2 segitiga menjadi persegi  

```js
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

### Segitiga pertama dengan koordinat [-0.5, -0.5, 0.5, -0.5, -0.5, 0.5]

![image](https://github.com/kenanargya/assignment3_WebGL/assets/92387421/c1831de7-a7a0-4e86-8cbd-ea91db3efa98)

### Segitiga kedua dengan koordinat [0.5, 0.5, -0.5, 0.5, 0.5, -0.5]

![image](https://github.com/kenanargya/assignment3_WebGL/assets/92387421/00f70b96-de33-4efc-a9a0-e41e7acc3496)

### Hasil penggabungan dua segitiga siku-siku

![image](https://github.com/kenanargya/assignment3_WebGL/assets/92387421/8ca913bb-69c7-4256-844a-813f2df16039)

## Soal 2
Membuat sebuah cube menggunakan WebGL dan GLMatrix  
  - Berikut merupakan codingan yang saya ubah untuk mengubah perspektif persegi menjadi kubus
```js
function draw() { 
    gl.clearColor(0,0,0,1);
    gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);
    
    /* Draw the six faces of a cube, with different colors. */
    
    drawPrimitive( gl.TRIANGLE_FAN, [0,1,1,1], [ -0.5 ,-0.5,-0.5, -0.5,0.5,-0.5, 0.5,0.5,-0.5, 0.5,-0.5,-0.5 ]); // front
    drawPrimitive( gl.TRIANGLE_FAN, [0,0,1,1], [ 0.5,0.5,0.5, -0.5,0.5,-0.5, -0.2,0.7,0.5, 0.8, 0.7, 0.5 ]); // top
    drawPrimitive( gl.TRIANGLE_FAN, [0,1,0,1], [ -0.2,-0.3,0.5, -0.2,0.7,0.5, 0.8,0.7,0.5, 0.8,-0.3,0.5 ]); // rear
    drawPrimitive( gl.TRIANGLE_FAN, [1,1,0,1], [ -0.5,0.5,-0.5, -0.5,-0.5,-0.5, -0.2,-0.3,0.5, -0.2,0.7,0.5 ]); // left
    drawPrimitive( gl.TRIANGLE_FAN, [1,0,1,1], [ 0.5,0.5,-0.5, 0.5,-0.5,-0.5, 0.8,-0.3,0.5, 0.8,0.7,0.5 ]); // right
    drawPrimitive( gl.TRIANGLE_FAN, [1,0,0,1], [ -0.5,-0.5,-0.5, -0.2,-0.3,0.5, 0.8,-0.3,0.5, 0.5,-0.5,-0.5 ]); // bottom

}
```
pada kode tersebut dilakukan perubahan koordinat agar perspektif dapat berubah menjadi kubus dan juga perubahan warna RGBA agar kubus dapat terlihat dengan jelas pada semua sisi

### Tanpa sisi depan
![image](https://github.com/kenanargya/assignment3_WebGL/assets/92387421/036562ef-21d7-4f10-896e-481c72415b08)

### Tanpa sisi samping dan depan
![image](https://github.com/kenanargya/assignment3_WebGL/assets/92387421/520e3720-d972-48b4-8e7c-58839fceae28)

### Tanpa sisi depan dan atas
![image](https://github.com/kenanargya/assignment3_WebGL/assets/92387421/508ab110-3694-4575-bca0-01a14c5af1c0)

### Kubus sempurna
![image](https://github.com/kenanargya/assignment3_WebGL/assets/92387421/081ca779-a375-4a00-a4fc-61e131dbe44b)












