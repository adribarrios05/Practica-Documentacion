# **Bingo** 🍀
## **Documentación clase Bingo java**

### **Índice**
- [**Bingo** 🍀](#bingo-)
  - [**Documentación clase Bingo java**](#documentación-clase-bingo-java)
    - [**Índice**](#índice)
    - [**Introducción** ](#introducción-)
    - [**Instalación** ](#instalación-)
    - [**Cómo funciona** ](#cómo-funciona-)
    - [**Utilidad** ](#utilidad-)
    - [**Créditos** ](#créditos-)
    - [**Licencia** ](#licencia-)
    - [**Por hacer** ](#por-hacer-)

---

### **Introducción** <a name="introducción-"></a>
La *librería* **`Bingo`** proporciona funcionalidades para simular un juego de bingo en Java. Contiene métodos para crear una partida, extraer números aleatorios, verificar si la partida ha terminado y generar una representación del tablero de bingo.
![](https://www.bienestarsenior.com/media/catalog/product/cache/1/thumbnail/dd54752af4dd24b92cb028fa0c0e8552/5/0/502010300-1_1_2.jpg)

---
### **Instalación** <a name="instalación-"></a>
Para utilizar la *librería* **`Bingo`**, sigue estos pasos:
1. Descarga el archivo **`Bingo.java`**.
2. Coloca el archivo en el ***directorio*** de tu proyecto Java.
3. Importa la clase **`Bingo`** en tu código Java.
---
### **Cómo funciona** <a name="cómo-funciona-"></a>
La clase `Bingo` proporciona funcionalidades para simular un juego de bingo en Java.
Para instanciarla haríamos lo siguiente:
  > 
      public Bingo(){
          numeros = new ArrayList<Integer>();
          crearPartida();
      }
Contiene métodos para:
- `crearPartida()`: Genera los números de la partida y los baraja.
  ``` java
  public void crearPartida(){
        for(int i = 1; i<=90; i++){
            Bingo.numeros.add(i);
        }
        Collections.shuffle(numeros);
    }
- `cogerNumero()`: Extrae un número aleatorio de la partida.
  ```java
  public int cogerNumero(){
          int numeroAleatorio = numeros.remove(0);
          return numeroAleatorio;
      }

- `getNumeros()`: Obtiene la lista de números restantes en la partida.
  ```java
  public ArrayList<Integer> getNumeros() {
        return numeros;
    }
- `terminarBingo()`: Verifica si la partida ha terminado.
  ```java
  public boolean terminarBingo(){
        return Bingo.numeros.isEmpty();
    }
- `toString()`: Representa el tablero de bingo en forma de cadena de texto.
  ```java
  @Override
    public String toString() {
        String tablero = "";
        int numero = 0;
        for(int i = 0; i<9; i++){
            for(int j=1; j<=10; j++){
                numero = i*10+j;
                if(numeros.contains(numero))
                    if(i==0 && j!=10)
                        tablero = tablero+" "+RED+numero+""+RESET+" ";
                    else
                        tablero = tablero+RED+numero+""+RESET+" ";
                else
                    if(i==0 && j!=10)
                        tablero = tablero+" "+GREEN+numero+""+RESET+" ";
                    else
                        tablero = tablero+GREEN+numero+""+RESET+" ";
            } 
            tablero+="\n";
        }
        return tablero;
    }

### **Utilidad** <a name="utilidad"></a>
La librería `Bingo` es útil para simular juegos de bingo en aplicaciones Java, ya sea para propósitos de entretenimiento o educativos.

### **Créditos** <a name="créditos"></a>
>La librería `Bingo` fue desarrollada por Adrián Barrios Márquez, alumno de 1º DAM del CPIFP Alan Turing.

### **Licencia** <a name="licencia"></a>
La librería `Bingo` tiene libre uso exclusivamente educativo, su distribución comercial está totalmente prohibida.

### **Por hacer** <a name="por-hacer"></a>
- [x] Generar las bolas y el tablero
- [ ] Generar cartones aleatorios
- [ ] Hacer que los numeros de los cartones se tachen cuando salga un número con el siguiente formato
  |           |           |           |           |           |           |           |           |           |
  |-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
  |   1       |           |  24       |           |  42       |           |  66       |  76       |           |
  |           |   12      |  26       |           |  44       |   50      |           |           |  90       |
  |   8       |           |           |   39      |           |   53      |  69       |  78       |           |

<br><br>
*Contacta conmigo a través de [GitHub](https://github.com/adribarrios05) o escríbeme a <abarmar0501@g.educaand.es>*


