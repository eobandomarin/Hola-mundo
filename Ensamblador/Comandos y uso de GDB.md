## Comandos Ensamblador

### Dar valor a registros
mov regname,valor

### Declaracion de variables
Se crea una seccion de datos y se establecen los mismos:

.section data
##### Variable vacia
db nombrevariable

##### Strings
Nombre_variable: <ver.tipo>
###### String: db 'texto',0xa
###### Longitud de string: equ $-variablestring
  
  
  
  
  
### Instrucciones
Se cra una seccion de instrucciones o cuerpo de programa y se establecen las etiquetas a usar:

.section text
  global _etiqueta1
  global _etiqueta2
  
_etiqueta1:
Dar valor a registros y hacer llamadas al sistema

#### Escritura en pantalla:
rax=1 ;syswrite
rdi=1
rsi=string
rdx=stringlength

#### Input Teclado
rax=0 ;sysread
rdi=0 ;standard input= teclado
rsi=variable
rdx=cantidad_teclas

#### Ejecutar instrucciones
syscall

#### Terminar Programa
rax=60
rdi=0

## Ensamblar con NASM
1. Preparar archivo .asm
2. nasm -f elf64 -o salida.o archivo.asm
3. ld -o ejecutable salida.o






## Uso de GDB

gdb <archivo.ejecutable>

run

continue

break _nombre.etiqueta

info registers

print/x $<registro> para visualizar en formato hexadecimal 
  
print/d $<registro> para visualizar en formato decimal 
  
print/t $<registro> para visualizar en formato binario 
  
print/c $<registro> para visualizar en formato de caracter 

x/c <direccion de memoria> imprime el contenido de una direccion en formato de caracter
  


