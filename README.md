# Laboratorio 1 Graficos
Para el laboratorio de hoy, deben crear un algoritmo que pueda rellenar polígonos de más de 4 puntos. Les recomiendo empezar dibujando las líneas entre los puntos para que puedan entender mejor la imágenes.

No pueden usar librerías externas.

Para obtener la nota completa de ésta tarea deben entregar lo siguiente:

- La nota máxima es 100.
- Los puntos se darán así: Si rellenan el 100% del polígono 1 tienen 30 puntos, si rellenan el 90% tienen el 90% de los 30 puntos. Si se salen de las lineas, pierden puntos de la misma manera.
-Envíen su código fuente renderizando todos los polígonos en un solo render, los puntos ya están puestos para que no se traslapen.
- Se les anima a que usen el Discord para discutir entre sus compañeros diferentes soluciones o recursos que hayan encontrado.
- En caso de que encuentren una solución usando herramientas de inteligencia artificial, adjunten con su entrega la conversación que tuvieron con el AI y una explicación de cómo lo aplicaron a su solución.
- Tiene que haber una primera entrega para el final del día de clases que se asignó esta actividad. Sin esta primera entrega, no se les calificará la actividad. Sin embargo, a lo largo de la semana aún tendrán oportunidad de hacer múltiples entregas en caso de que sepan como mejorar lo que tiene.

## Inicialización

 El Rasterizador puede ser ejecutado mediante la ejecución del archivo ```Main.py```, dentro de una ventana de shell, navegar al directorio donde se encuentran los archivos y correr el siguiente comando:
  ```bash
    python3 Main.py
  ```  

## Resultado
Al ejecutar el progama se debe obtener un archivo llamado ```output.bmp``` la cual tendra un tamaño de 1000x1000px con la imagen de una estrella blanca, un rombo rojo, un triangulo verde y una tetera azul.
Además en el repositiorio se encuentran 5 archivos ```.bmp``` con la imagen de cada objeto individualmente creado.

## Herramientas Externas
En este laboratorio se utilizo el apoyo de la herramienta externa ChatGPT para crear una algoritmo que determinará si un punto se encontraba dentro del poligono, de esta manera determinar si pintar o no ese punto. La conversación fue la siguiente:
https://chat.openai.com/share/fdd46937-dae2-4c39-981c-025a54139578

Al inicio se le pidio encontrar si un punto se encontraba dentro de un triangúlo pero la respuesta incluía un algoritmo ya suficientemente util para determinar si los puntos se encuentran dentro de cada poligono individualmente. 
El algoritmo funciona de la siguiente manera:

- Se encuentra la cantidad de vertices en cada poligono
- Se encuentra el ultimo indice de los vertices
- Para cada vertice se encuentra el punto x y el punto y, luego se determina si el punto es menor o mayor que los puntos del vertice, luego se compara con otro vertice, en el caso del primer vertice, se compara con el ultimo, para todos los otros vertices se utiliza el ultimo vertice usado.
- Si se encuentra que el punto esta dentro del poligono, se retorna un booleano Verdadero, si se determina que el punto esta fuera del poligono se retorna un booleano Falso
