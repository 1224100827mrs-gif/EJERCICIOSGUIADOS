# Codigo Colas 
## Marisol Rincón Solís

``` java
package Cola;

/**
 * Clase Cola
 * 
 * @autor Marisol Rincón Solís
 * Fecha: 24 de octubre de 2025
 * 
 * Esta clase implementa una cola genérica (FIFO) usando nodos enlazados.
 * Permite insertar, quitar y ver elementos, además de mostrar la cola completa.
 */

import java.util.Scanner;

public class Cola<T> {

    private Nodo<T> cabeza; // primer nodo de la cola
    private Nodo<T> cola;   // último nodo de la cola
    private int tamano;     // número de elementos en la cola

    // Constructor: inicializa la cola vacía
    public Cola() {
        cabeza = null;
        cola = null;
        tamano = 0;
    }

    // Verifica si la cola está vacía
    public boolean colaVacia() {
        return cabeza == null;
    }

    // Inserta un elemento al final de la cola
    public void insertar(T elemento) {
        Nodo<T> nuevo = new Nodo<>(elemento);
        if (colaVacia()) {
            // Si la cola está vacía, el nuevo nodo es cabeza y cola
            cabeza = nuevo;
            cola = nuevo;
        } else {
            // Si no, se agrega al final y se actualiza la cola
            cola.setDerecha(nuevo);
            cola = nuevo;
        }
        tamano++;
    }

    // Quita el elemento al frente de la cola
    public T quitar() {
        if (colaVacia()) {
            System.out.println("La cola esta vacia.");
            return null;
        }
        T dato = cabeza.getDato();
        cabeza = cabeza.getDerecha();
        if (cabeza == null) {
            // Si la cola queda vacía, cola también es null
            cola = null;
        }
        tamano--;
        return dato;
    }

    // Devuelve el elemento al frente de la cola sin quitarlo
    public T frente() {
        if (colaVacia()) {
            System.out.println("La cola esta vacia.");
            return null;
        }
        return cabeza.getDato();
    }

    // Devuelve el tamaño actual de la cola
    public int getTamano() {
        return tamano;
    }

    // Muestra todos los elementos de la cola
    public void mostrarCola() {
        if (colaVacia()) {
            System.out.println("No hay tareas en la cola.");
            return;
        }
        Nodo<T> actual = cabeza;
        while (actual != null) {
            System.out.println(actual.getDato());
            actual = actual.getDerecha();
        }
    }

    // Programa principal para interactuar con la cola
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        Cola<String> colaTareas = new Cola<>();
        int opcion;

        do {
            // Menú de opciones
            System.out.println("\n--- Menu de Tareas ---");
            System.out.println("1. Agregar tarea");
            System.out.println("2. Mostrar tamano de la cola");
            System.out.println("3. Ver tarea al frente");
            System.out.println("4. Quitar tarea");
            System.out.println("5. Mostrar todas las tareas");
            System.out.println("6. Salir");
            System.out.print("Elige una opcion: ");
            opcion = teclado.nextInt();
            teclado.nextLine(); // limpia el buffer

            switch (opcion) {
                case 1:
                    // Opción 1: Agregar una nueva tarea a la cola
                    System.out.print("Ingresa la tarea: ");
                    String tarea = teclado.nextLine();
                    colaTareas.insertar(tarea);
                    break;

                case 2:
                    // Opción 2: Mostrar el tamaño actual de la cola
                    System.out.println("Tamano: " + colaTareas.getTamano());
                    break;

                case 3:
                    // Opción 3: Mostrar la tarea que está al frente de la cola
                    String frente = colaTareas.frente();
                    if (frente != null)
                        System.out.println("Tarea al frente: " + frente);
                    break;

                case 4:
                    // Opción 4: Quitar (ejecutar) la tarea que está al frente de la cola
                    String quitada = colaTareas.quitar();
                    if (quitada != null)
                        System.out.println("Tarea ejecutada: " + quitada);
                    break;

                case 5:
                    // Opción 5: Mostrar todas las tareas de la cola
                    colaTareas.mostrarCola();
                    break;

                case 6:
                    // Opción 6: Salir del programa
                    System.out.println("Saliendo...");
                    break;

                default:
                    // Si se ingresa un número no válido
                    System.out.println("Opcion no valida.");
            }
        } while (opcion != 6);
    }
}
```
