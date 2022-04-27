# Trabajo Practico Nro 1 - Comparativa de Lenguajes POO

Comparativa de la misma porcion de codigo en los siguientes lenguajes:
- C#
- C
- Java
- Javascript
- PHP
- Python
- Ruby

----------------------------------------------------------------

### Clase Abstracta

- C#:

```
public abstract class Figura {
    public abstract string Tipo();
    public abstract string Color();
}

public class Triangulo : Figura {
    public override string Tipo() {
        return "Triangulo";
    }
    public override string Color() {
        return "Azul";
    }
}

Triangulo t = new Triangulo();
Console.WriteLine(t.Tipo() + " " + t.Color());
```

- C:

No existe el concepto de programacion orietada a objetos en C, lo mas parecido a una clase abstracta seria:

```
#include <stdio.h>
#include <string.h>

typedef struct Figuras {
   char tipo[50];
   char color[50];
} Figura;

int main( ) {
    Figuras triangulo
    strcpy( triangulo.tipo, "escaleno"); 
    strcpy( triangulo.color, "blanco");
    printf( "Triangulo tipo : %s\n", triangulo.tipo);
    printf( "Triangulo color : %s\n", triangulo.color);
    return 0;
}
```

- Java:

```
abstract class Figura{
    abstract void nombre();
}

class Triangulo extends Figura{
    @override
    void tipo(){
        System.out.println("Escaleno");
    }
}

public class Geometria{
    public static void main(String[] args){
        Triangulo t_escaleno = new Triangulo();
        t_escaleno.tipo();
    }
}
```

- Javascript:

```
class Figura{
    constructor(){
        if (this.constructor == Figura){
            throw new Error("Clase abstracta, debe ser instanciada");
        }
    }
    tipo(){
        throw new Error("Metodo Tipo, debe ser implementado");
    }
    color(){
        throw new Error("Metodo Color, debe ser implementado");
    }

}

class Triangulo extends Figura{
    tipo(){
        console.log("Escaleno");
    }
    color(){
        console.log("Rojo");
    }
}

new Triangulo().tipo();
new Triangulo().color();
```

- PHP:

```
abstract class Figura{
    abstract public function setTipo($tipo);
    abstract public function getTipo();
    abstract public function setColor($color);
    abstract public function getColor();
}

class Triangulo extends Figura{
    public function setTipo($tipo){
        $this->tipo = $tipo;
    }
    public function getTipo(){
        return $this->tipo;
    }
    public function setColor($color){
        $this->color = $color;
    }
    public function getColor(){
        return $this->color;
    }
}

$triangulo = new Triangulo();
$triangulo->setTipo("Equilatero");
$triangulo->setColor("Verde");
echo "El triangulo es de tipo: ".$triangulo->getTipo()." y de color: ".$triangulo->getColor();
```

- Python:

```
from abc import ABC, abstractmethod

class Figura(ABC):
    @abstractmethod
    def __init__(self, tipo)-> None:
        self._tipo = tipo

class Triangulo(Figura):
    def __init__(self, tipo, color) -> None:
        super().__init__(tipo)
        self._color = color
    
    @property
    def mostrar_triangulo(self):
        return f'{self._tipo} {self._color}'

triangulito = Triangulo('escaleno', 'rojo')
print(triangulito.mostrar_triangulo)
```

- Ruby:

```
class Figuras
    def initialize
        raise "No se puede inicializar la clase Figura, debe ser instanciada."
    end

    def mostrar_tipo_color
        puts "Figura: #{figura}"
    end
    
    def figura
        raise "No se puede obtener el nombre de la figura."
    end
    
end

class Triangulo < Figuras
    attr_reader :tipo
    attr_reader :color
    
    def initialize(tipo, color)
        @tipo = tipo
        @color = color
    end

    private

    def figura
        "Triangulo. Tipo: #{@tipo}. Color: #{@color}"
    end
end

t = Triangulo.new("Equilatero", "Rojo")
t.mostrar_tipo_color
```

----------------------------------------------------------------

### Bucle FOR

- C#:

```

for (int i = 0; i < 3; i++)
{
    Console.Write(i);
}
```

- C:

```
for (i = 0; i < 3; i++)
{
    printf("%i",i);
}
```

- Java:

```
for (int i = 0; i < 3; i++) {
  System.out.println(i);
}

```

- Javascript:

```
for (let i = 0; i < 3; i++) {
  console.log(i);
}
```

- PHP:

```
for ($i = 1; $i <= 3; $i++) {
    echo $i;
}
```

- Python:

```
for i in range (3):
    print(i)
```

- Ruby:

```
for i in 1..5 do
    puts i
```

----------------------------------------------------------------

### Escritura de archivos de texto

- C#:

```
String texto = "Hola Mundo, escribiendo archivos de texto en C#";
File.WriteAllText("archivotexto.txt", texto);
```

- C:

```
FILE *f_archivo;
f_archivo = fopen("archivotexto.txt","w");
fprintf(f_archivo,"Hola Mundo, escribiendo archivos de texto en C");
fclose(f_archivo);
```

- Java:

```
FileWriter f_archivo = new FileWriter("archivotexto.txt");
f_archivo.write("Hola Mundo, escribiendo archivos de texto en Java");
f_archivo.close();
```

- Javascript:
Por razones de seguridad no se puede acceder a los archivos de usuario usando directamente Javascript.
Pero se puede utilizar el framework NodeJS para hacerlo, por ejemplo:

```
<script>
const fsLibrary  = require('fs')
let texto = "Hola Mundo, escribiendo archivos de texto en Javascript/NodeJS"
fsLibrary.writeFile('archivotexto.txt', texto)
</script>
```

- PHP:

```
$f_archivo = fopen("archivotexto.txt", "w") or die("No se puede abrir el archivo!");
$texto = "Hola Mundo, escribiendo archivos de texto en PHP\n";
fwrite($f_archivo, $texto);
fclose($f_archivo);
```

- Python:

```
f_archivo = open('archivotexto.txt', 'w+')
f_archivo.write("Hola Mundo, escribiendo archivos de texto en Python")
f_archivo.close()
```

- Ruby:

```
File.write('archivotexto.txt', 'Hola Mundo, escribiendo archivos de texto en Ruby')
```
