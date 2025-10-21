# Ejercicios Guiados
## Evidencia de la Actividad2: Lista Enlazada Humana 
| Evidencia 1 | Evidencia 2 | Evidencia 3 |
| :---: | :---: | :---: |
| <img src="https://github.com/user-attachments/assets/a0d4026b-86a0-42b5-93ee-3dcc941c6c94" width="200px" alt="Imagen 1"> | <img src="https://github.com/user-attachments/assets/85913981-88bd-4113-a6ea-3d5ea4828466" width="200px" alt="Imagen 2"> | <img src="https://github.com/user-attachments/assets/9b42757e-525f-46ef-bd4d-d35809cd0705" width="200px" alt="Imagen 3"> 

## Códigos de la actividad Práctica de Listas
### Lista Circular
```java
package ListasPractica;

/**Marisol Rincón Solís 
 * Este es un proyecto de repaso donde s muestra como funciona una lista circular
 * resolviendo la actividad que nos realizo el profesor el dia viernes 
 *13/Octubre/2025
 * @author DELL
 */

public class ListaCircular {
    private Nodo inicio; // Nodo de inicio

    // Clase interna Nodo
    private class Nodo {
        private String dato; // Valor del nodo
        private Nodo siguiente; // Referencia al siguiente nodo

        Nodo(String dato) {
            this.dato = dato;
        }
    }

    // Método para crear la lista con 4 nodos
    public void crear() {
        Nodo rojo = new Nodo("Rojo");
        Nodo verde = new Nodo("Verde");
        Nodo azul = new Nodo("Azul");
        Nodo amarillo = new Nodo("Amarillo");

        rojo.siguiente = verde;
        verde.siguiente = azul;
        azul.siguiente = amarillo;
        amarillo.siguiente = rojo;

        inicio = rojo;
    }

    // Método para insertar un nodo después de uno específico
    public void insertar(String nuevoDato, String despuesDe) {
        Nodo actual = inicio;

        do {
            if (actual.dato.equals(despuesDe)) {
                Nodo nuevo = new Nodo(nuevoDato);
                nuevo.siguiente = actual.siguiente;
                actual.siguiente = nuevo;
                return;
            }
            actual = actual.siguiente;
        } while (actual != inicio);
    }

    // Método para eliminar un nodo específico
    public void eliminar(String dato) {
        Nodo actual = inicio;

        do {
            if (actual.siguiente.dato.equals(dato)) {
                actual.siguiente = actual.siguiente.siguiente;
                return;
            }
            actual = actual.siguiente;
        } while (actual != inicio);
    }

    // Método para mostrar los nodos de la lista
    public void mostrar() {
        Nodo actual = inicio;

        do {
            System.out.print("[" + actual.dato + "] → ");
            actual = actual.siguiente;
        } while (actual != inicio);

        System.out.println("(vuelve a " + inicio.dato + ")");
    }

    // Método principal para probar la lista
    public static void main(String[] args) {
        ListaCircular lista = new ListaCircular();
        lista.crear();
        lista.mostrar();

        lista.insertar("Morado", "Azul");
        lista.mostrar();

        lista.eliminar("Verde");
        lista.mostrar();
    }
}
    
```
### Lista Simple
```java

package ListasPractica;

/**Marisol Rincón Solís 
 * Este es un proyecto de repaso donde s muestra como funciona una lista simple 
 * resolviendo la actividad que nos realizo el profesor el dia viernes 
 *13/Octubre/2025
 * @author DELL
 */

  
public class ListaSimple {
    private Nodo inicio; // Nodo de inicio

    // Clase interna Nodo
    private class Nodo {
        private String dato; // Valor del nodo
        private Nodo siguiente; // Referencia al siguiente nodo

        Nodo(String dato) {
            this.dato = dato;
        }
    }

    // Método para crear la lista con 4 nodos
    public void crear() {
        Nodo ana = new Nodo("Ana");
        Nodo benjamin = new Nodo("Benjamín");
        Nodo carla = new Nodo("Carla");
        Nodo diego = new Nodo("Diego");

        ana.siguiente = benjamin;
        benjamin.siguiente = carla;
        carla.siguiente = diego;

        inicio = ana;
    }

    // Método para insertar un nodo después de otro
    public void insertar(String nuevoDato, String despuesDe) {
        Nodo actual = inicio;
        while (actual != null) {
            if (actual.dato.equals(despuesDe)) {
                Nodo nuevo = new Nodo(nuevoDato);
                nuevo.siguiente = actual.siguiente;
                actual.siguiente = nuevo;
                return;
            }
            actual = actual.siguiente;
        }
    }

    // Método para eliminar un nodo con cierto valor
    public void eliminar(String dato) {
        if (inicio == null) return;

        if (inicio.dato.equals(dato)) {
            inicio = inicio.siguiente;
            return;
        }

        Nodo actual = inicio;
        while (actual.siguiente != null) {
            if (actual.siguiente.dato.equals(dato)) {
                actual.siguiente = actual.siguiente.siguiente;
                return;
            }
            actual = actual.siguiente;
        }
    }

    // Método para mostrar los nodos de la lista
    public void mostrar() {
        Nodo actual = inicio;
        while (actual != null) {
            System.out.print("[" + actual.dato + "] → ");
            actual = actual.siguiente;
        }
        System.out.println("NULL");
    }

    // Método principal para probar la lista
    public static void main(String[] args) {
        ListaSimple lista = new ListaSimple();
        lista.crear();
        lista.insertar("Elena", "Carla");
        lista.insertar("Dalia", "Diego");
        lista.eliminar("Benjamín");
        lista.mostrar();
    }
}
```
### Lista Doble
```java
  private Nodo inicio; // Nodo de inicio

    // Clase interna Nodo
    private class Nodo {
        private String dato; // Valor del nodo
        private Nodo siguiente, anterior; // Referencias al siguiente y anterior nodo

        Nodo(String dato) {
            this.dato = dato;
        }
    }

    // Método para crear la lista con 4 nodos
    public void crear() {
        Nodo prog = new Nodo("Programación");
        Nodo mate = new Nodo("Matemáticas");
        Nodo ingles = new Nodo("Inglés");
        Nodo fisica = new Nodo("Física");

        prog.siguiente = mate;
        mate.anterior = prog;

        mate.siguiente = ingles;
        ingles.anterior = mate;

        ingles.siguiente = fisica;
        fisica.anterior = ingles;

        inicio = prog;
    }

    // Método para insertar un nodo al inicio
    public void insertarInicio(String dato) {
        Nodo nuevo = new Nodo(dato);
        nuevo.siguiente = inicio;
        if (inicio != null) {
            inicio.anterior = nuevo;
        }
        inicio = nuevo;
    }

    // Método para eliminar un nodo con cierto valor
    public void eliminar(String dato) {
        Nodo actual = inicio;

        while (actual != null) {
            if (actual.dato.equals(dato)) {
                if (actual.anterior != null) {
                    actual.anterior.siguiente = actual.siguiente;
                } else {
                    inicio = actual.siguiente;
                }
                if (actual.siguiente != null) {
                    actual.siguiente.anterior = actual.anterior;
                }
                return;
            }
            actual = actual.siguiente;
        }
    }

    // Método para mostrar los nodos de la lista
    public void mostrar() {
        Nodo actual = inicio;
        while (actual != null) {
            System.out.print("[" + actual.dato + "] ↔ ");
            actual = actual.siguiente;
        }
        System.out.println("NULL");
    }

    // Método principal para probar la lista
    public static void main(String[] args) {
        ListaDoble lista = new ListaDoble();
        lista.crear();
        lista.insertarInicio("Arte");
        lista.eliminar("Matemáticas");
        lista.mostrar();
    }
}
```
