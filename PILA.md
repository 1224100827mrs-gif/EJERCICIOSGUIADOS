# Códigos PILA
## Marisol Rincón Solís 


### Primer código realizado 
```java
package Pila;

/**
 * Ejercicio guiado 
 * Una pila es una colección ordenada de elementos a los cuales sólo se puede 
 * acceder por un único lugar o extremo de la pila.
 *14 de Octubre de 2025
 * @author Marisol Rincón Solís
 */
public interface IStack<T> {
   void push(T element);
    T  pop();
    T peek();
   boolean isEmpty();
    
}

```

### Segundo Código realizado 
#### Actividad Especificación de la Pila enviada por el profesor por medio de whatsApp
```java

/**
 * Tema: PILA
 * Esta clase implementa una pila (estructura LIFO) genérica utilizando un arreglo.
 * Permite almacenar elementos de cualquier tipo y realizar operaciones básicas:
 * - push(): insertar un elemento en la cima de la pila
 * - pop(): eliminar y devolver el elemento de la cima
 * - peek(): consultar el elemento en la cima sin eliminarlo
 * - isEmpty(): verificar si la pila está vacía
 *17/Octubre/2025
 * @author Marisol Rincón Solís 
 */

package Pila;



public class StackArrays<T> implements IStack<T> {
    private T[] elements; // Estructura interna (Array)
    private int top; // Índice de la cima

    // Constructor por defecto: pila con 30 elementos
    public StackArrays() {
        elements = (T[]) new Object[30];
        top = -1; // <-- Inicialización 
    }

    // Constructor con tamaño definido
    public StackArrays(int size) {
        elements = (T[]) new Object[size];
        top = -1; // <-- Inicializacion
    }
//Insertar
    @Override
    public void push(T element) {
        if (top < elements.length - 1) {
            top++;
            elements[top] = element;
        } else {
            System.out.println("La pila está llena");
        }
    }
//Eliminar
    @Override
    public T pop() {
        if (isEmpty()) {
            System.out.println("La pila está vacía");
            return null;
        } else {
            T element = elements[top];
            elements[top] = null;
            top--;
            return element;
        }
    }
//Imprimir el ultimo sin eliminarlo
    @Override
    public T peek() {
        if (isEmpty()) {
            System.out.println("Pila vacía");
            return null;
        }
        return elements[top];
    }
// Verificar si esta vacia la pila
    @Override
    public boolean isEmpty() {
        return top == -1;
    }

    public static void main(String[] args) {
        StackArrays<String> nombres = new StackArrays<>();
        nombres.push("Elsy");
        nombres.push("Angel");
        nombres.push("Yos");

        System.out.println(nombres.pop());
        System.out.println(nombres.pop());
        System.out.println(nombres.pop());
    }
}
```
