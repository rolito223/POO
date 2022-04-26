# Trabajo Practico Nro 1 - Comparativa de Lenguajes POO
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

'''
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
'''

- Java:

'''
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
'''

- Javascript:

'''
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
'''

- PHP:

'''
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

$trianulo = new Triangulo();
$trianulo->setTipo("Equilatero");
$trianulo->setColor("Verde");
echo "El triangulo es de tipo: ".$trianulo->getTipo()." y de color: ".$trianulo->getColor();
'''

- Python:

'''
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
'''

- Ruby:

'''
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
'''

- Kotlin:


'''
abstract class Figura(forma: String, color: String){
    init(forma: forma, color: color){
        this.forma = forma
        this.color = color
    }
    abstract fun mostrarformaColor()
        println("Forma $this.forma y color $this.color")
}

class Triangulo(forma: String, color: String, tipo: String): Figura(forma, color){
    override fun mostrarformaColor() {
        println("Forma $this.forma y color $this.color. Tipo: $tipo")
    }
}


fun main(args: Array<String>) {
    val triangulo = Triangulo("Triangulo", "Rojo", "Equilatero")
    triangulo.mostrarformaColor()
}
'''
