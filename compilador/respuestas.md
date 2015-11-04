RESPUESTAS DEL EJERCICIO DE COMPILADOR:

1. Los pasos a seguir son 4:

PREPROCESADOR:
Se realiza un primer procesamiento. Se evita tener que definir funciones y
macros “usuales”. 

Sentencia: gcc -E calculator.c -o calculator.pp.c 


COMPILACION I:
Se realiza la traducción de C a lenguaje assembler. Es la parte mas pesada del
proceso.

Sentencia: gcc -masm=intel -S calculator.c -o calculator.asm 


COMPILACION II:
Se realiza la traduccion de assembler a lenguaje de maquina. Se generan los 
objetos binarios.

Sentencia: gcc -c calculator.c -o calculator.o

LINKEO:
Se realiza el linkeo para poder generar el archivo ejecutable a partir del 
binario generado en el paso anterior.

Sentencia: gcc calculator.o -o calculator.e 


2. Luego de ejecutar 'make preprocessing' aparece un nuevo archivo llamado 
calculator.pp.c y agrega todas las definiciones de las funciones (que hace la 
funcion aparece en el linkeo).

3. En el archivo 'calculator.asm' aparece la funcion main (dentro de ella las 
funciones add_numbers y printf) y la definicion de la funcion add_numbers.

4. Los simbolos que se crean en el objeto son las funciones.

5. En el objeto aparecen unicamente las funciones add_numbers, main y printf,
con esta ultima undef (U).
En el ejecutable aparecen todas las funciones que requiere el printf para
funcionar y el link de la funcion printf a la libreria dinamica.










