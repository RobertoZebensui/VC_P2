# Práctica 2. Funciones básicas de OpenCV

En esta práctica se realizan las tareas propuestas en el cuaderno de la práctica 2 de la asignatura de Visión por Computador.

## Tarea 1
Se propone contar los píxeles blancos de las filas tras aplicar el detector Canny a la imagen del mandril:

<img width="512" height="512" alt="mandril" src="https://github.com/user-attachments/assets/43061054-f4cc-4edb-823b-674916f0c124" />

Tras la cuenta se realiza utilizando el método *reduce*  de **cv2**. Tras normalizar el resultado, 
nos quedamos aquella fila que tiene el máximo número de píxeles blancos. Con el método *where* de **numpy**, seleccionamos las que tengan al menos un 90%
de los píxeles blancos de la fila que más tiene. Luego, se dibuja una línea en cada fila que cumpla esta condición, mostrando finalmente la imagen resultante
y el conteo de píxeles blancos dados por Canny.

<img width="516" height="454" alt="img_tarea1_p2" src="https://github.com/user-attachments/assets/00937c1a-f002-48e7-a41b-f3adb4106d82" />

## Tarea 2
En esta tarea, se propone comparar el conteo de filas y columnas entre Canny y Sobel + Umbralización. El proceso para el conteo de filas y columnas es el mismo que
en la tarea anterior. Para obtener la imagen de Sobel, primero se pasa la imagen original a escala de grises, y se le aplica un desenfoque gaussiano. Luego, hacemos
uso del método *Sobel* de **cv2**, para obtener los bordes horizontales y verticales, y luego sacar la imagen compuesta por ambos resultados. Se saca la imagen
umbralizada con el método *threshold* de **cv2**, y se hace el conteo de los píxeles blancos a partir de este resultado. Finalmente, se comparan ambos resultados.

<img width="516" height="267" alt="img_tarea2_p2" src="https://github.com/user-attachments/assets/1c6f9b2c-2ce4-43a1-b709-a91727221cf8" />

## Tarea 3
Insipirado en **My little piece of Privacy** de Niklas Roy (https://www.niklasroy.com/project/88/my-little-piece-of-privacy), se ha creado un efecto parecido,
obteniendo la imagen de vídeo y procesándola. Primero pasándola a escala de grises y comparándola con el frame anterior, luego sacando la diferencia y aplicando
un desenfoque gaussiano. Luego se elimina el fondo gracias al método *createBackgroundSubtractorMOG2* de **cv2**. Después, como se realizó en la tarea anterior,
se hace un conteo de los píxeles blancos en las columnas, tras aplicar Sobel + Umbralización. Finalmente, se seleccionan la primera y última columna dentro de las
que cumplen que tienen más de un 5% de píxeles blancos que la columna que más tiene. Se dibujan dos rectángulos a ambos laterales, de manera que el efecto que da
es el de enmarcar a la persona que pasa de una lado a otro de la imagen, tapando el fondo. También se puede hacer como que se empujan estos bordes con las 
manos.

Enlace al vídeo de muestra: https://youtu.be/QRXUTHIN6TY

## Uso de IA
Solo se ha usado para buscar una manera eficiente en numpy de cómo seleccionar elementes dentro de un array, vector o matriz. La respuesta fue el método **where**

## Fuentes

Cuaderno de la práctica 2 de la asignatura: https://github.com/otsedom/otsedom.github.io/blob/main/VC/P2

My little piece of Privacy: https://www.niklasroy.com/project/88/my-little-piece-of-privacy

## Autor
Roberto Zebensuí Marrero Falcón [github.com/RobertoZebensui](https://github.com/RobertoZebensui)
