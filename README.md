#include <iostream>
#include <iomanip>
using namespace std;

const int MAX = 100;
const int MAX_MATRIZ = 20;

void pausar() {
    cout << "\nPresione ENTER para continuar...";
    cin.ignore();
    cin.get();
}

void leerDatosAritmeticaVector(int &a1, int &d, int &n) {
    cout << "Ingrese el primer termino (a1): ";
    cin >> a1;

    cout << "Ingrese la diferencia (d): ";
    cin >> d;

    cout << "Ingrese la cantidad de terminos (n): ";
    cin >> n;
}

void llenarVectorAritmetico(int vector[], int n, int a1, int d) {
    for (int i = 0; i < n; i++) {
        vector[i] = a1 + (i * d);
    }
}

void mostrarVectorAritmetico(int vector[], int n) {
    cout << "\nVector: ";

    for (int i = 0; i < n; i++) {
        cout << vector[i];

        if (i < n - 1) {
            cout << ", ";
        }
    }

    cout << endl;
}

void mostrarSumaVector(int vector[], int n) {
    int suma = 0;

    for (int i = 0; i < n; i++) {
        suma = suma + vector[i];
    }

    cout << "Suma: " << suma << endl;
}

void mostrarMayorMenorVector(int vector[], int n) {
    int mayor = vector[0];
    int menor = vector[0];

    for (int i = 1; i < n; i++) {

        if (vector[i] > mayor) {
            mayor = vector[i];
        }

        if (vector[i] < menor) {
            menor = vector[i];
        }
    }

    cout << "Mayor: " << mayor << endl;
    cout << "Menor: " << menor << endl;
}

void mostrarPromedioVector(int vector[], int n) {
    int suma = 0;

    for (int i = 0; i < n; i++) {
        suma = suma + vector[i];
    }

    double promedio = (double)suma / n;

    cout << "Promedio: " << promedio << endl;
}

void ejercicio1() {

    int vector[MAX];
    int a1, d, n;

    cout << "\n======================================" << endl;
    cout << "   EJERCICIO 1: SERIE ARITMETICA" << endl;
    cout << "          EN VECTOR" << endl;
    cout << "======================================" << endl;

    leerDatosAritmeticaVector(a1, d, n);

    if (n <= 0 || n > MAX) {
        cout << "Cantidad de terminos no valida." << endl;
        pausar();
        return;
    }

    llenarVectorAritmetico(vector, n, a1, d);

    mostrarVectorAritmetico(vector, n);
    mostrarSumaVector(vector, n);
    mostrarMayorMenorVector(vector, n);
    mostrarPromedioVector(vector, n);

    pausar();
}

void leerDatosAritmeticaMatriz(int &a1, int &d, int &filas, int &columnas) {

    cout << "Ingrese el primer termino (a1): ";
    cin >> a1;

    cout << "Ingrese la diferencia (d): ";
    cin >> d;

    cout << "Ingrese cantidad de filas: ";
    cin >> filas;

    cout << "Ingrese cantidad de columnas: ";
    cin >> columnas;
}

void llenarMatrizAritmetica(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas,
    int a1,
    int d
) {

    int termino = a1;

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            matriz[i][j] = termino;

            termino = termino + d;
        }
    }
}

void mostrarMatrizAritmetica(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    cout << "\n--- MATRIZ ---" << endl;

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            cout << setw(5) << matriz[i][j];
        }

        cout << endl;
    }
}

void mostrarSumaMatriz(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    int suma = 0;

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            suma = suma + matriz[i][j];
        }
    }

    cout << "Suma: " << suma << endl;
}

void mostrarMayorMenorMatriz(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    int mayor = matriz[0][0];
    int menor = matriz[0][0];

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            if (matriz[i][j] > mayor) {
                mayor = matriz[i][j];
            }

            if (matriz[i][j] < menor) {
                menor = matriz[i][j];
            }
        }
    }

    cout << "Mayor: " << mayor << endl;
    cout << "Menor: " << menor << endl;
}

void mostrarPromedioMatriz(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    int suma = 0;

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            suma = suma + matriz[i][j];
        }
    }

    int cantidad = filas * columnas;

    double promedio = (double)suma / cantidad;

    cout << "Promedio: " << promedio << endl;
}

void ejercicio2() {

    int matriz[MAX_MATRIZ][MAX_MATRIZ];

    int a1, d;
    int filas, columnas;

    cout << "\n======================================" << endl;
    cout << "   EJERCICIO 2: SERIE ARITMETICA" << endl;
    cout << "          EN MATRIZ" << endl;
    cout << "======================================" << endl;

    leerDatosAritmeticaMatriz(a1, d, filas, columnas);

    if (filas <= 0 || columnas <= 0 ||
        filas > MAX_MATRIZ || columnas > MAX_MATRIZ) {

        cout << "Dimensiones no validas." << endl;
        pausar();
        return;
    }

    llenarMatrizAritmetica(
        matriz,
        filas,
        columnas,
        a1,
        d
    );

    mostrarMatrizAritmetica(
        matriz,
        filas,
        columnas
    );

    mostrarSumaMatriz(
        matriz,
        filas,
        columnas
    );

    mostrarMayorMenorMatriz(
        matriz,
        filas,
        columnas
    );

    mostrarPromedioMatriz(
        matriz,
        filas,
        columnas
    );

    pausar();
}

void leerDatosRepetidoVector(int &n) {

    cout << "Ingrese la cantidad de terminos (n): ";
    cin >> n;
}

void llenarVectorRepetido(int vector[], int n) {

    for (int i = 0; i < n; i++) {

        vector[i] = (i / 2) + 1;
    }
}

void mostrarVectorRepetido(int vector[], int n) {

    cout << "Serie: ";

    for (int i = 0; i < n; i++) {

        cout << vector[i];

        if (i < n - 1) {
            cout << ", ";
        }
    }

    cout << endl;
}

void mostrarSumaRepetidoVector(int vector[], int n) {

    int suma = 0;

    for (int i = 0; i < n; i++) {

        suma = suma + vector[i];
    }

    cout << "Suma: " << suma << endl;
}

void mostrarMayorMenorRepetidoVector(int vector[], int n) {

    int mayor = vector[0];
    int menor = vector[0];

    for (int i = 1; i < n; i++) {

        if (vector[i] > mayor) {
            mayor = vector[i];
        }

        if (vector[i] < menor) {
            menor = vector[i];
        }
    }

    cout << "Mayor: " << mayor << endl;
    cout << "Menor: " << menor << endl;
}

void mostrarPromedioRepetidoVector(int vector[], int n) {

    int suma = 0;

    for (int i = 0; i < n; i++) {

        suma = suma + vector[i];
    }

    double promedio = (double)suma / n;

    cout << "Promedio: " << promedio << endl;
}

void ejercicio3() {

    int vector[MAX];
    int n;

    cout << "\n======================================" << endl;
    cout << "   EJERCICIO 3: SERIE REPETIDA" << endl;
    cout << "          EN VECTOR" << endl;
    cout << "======================================" << endl;

    leerDatosRepetidoVector(n);

    if (n <= 0 || n > MAX) {

        cout << "Cantidad de terminos no valida." << endl;
        pausar();
        return;
    }

    llenarVectorRepetido(vector, n);

    mostrarVectorRepetido(vector, n);
    mostrarSumaRepetidoVector(vector, n);
    mostrarMayorMenorRepetidoVector(vector, n);
    mostrarPromedioRepetidoVector(vector, n);

    pausar();
}

void leerDatosRepetidoMatriz(int &filas, int &columnas) {

    cout << "Ingrese el numero de filas: ";
    cin >> filas;

    cout << "Ingrese el numero de columnas: ";
    cin >> columnas;
}

void llenarMatrizRepetida(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    int numero = 1;
    int contador = 0;

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            matriz[i][j] = numero;

            contador++;

            if (contador == 2) {

                numero++;
                contador = 0;
            }
        }
    }
}

void mostrarMatrizRepetida(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    cout << "\n--- MATRIZ ---" << endl;

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            cout << setw(5) << matriz[i][j];
        }

        cout << endl;
    }
}

void mostrarSumaTotalRepetida(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    int suma = 0;

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            suma = suma + matriz[i][j];
        }
    }

    cout << "Suma total: " << suma << endl;
}

void mostrarMayorMenorRepetida(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    int mayor = matriz[0][0];
    int menor = matriz[0][0];

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            if (matriz[i][j] > mayor) {
                mayor = matriz[i][j];
            }

            if (matriz[i][j] < menor) {
                menor = matriz[i][j];
            }
        }
    }

    cout << "Mayor: " << mayor << endl;
    cout << "Menor: " << menor << endl;
}

void mostrarPromedioRepetida(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    int suma = 0;

    for (int i = 0; i < filas; i++) {

        for (int j = 0; j < columnas; j++) {

            suma = suma + matriz[i][j];
        }
    }

    double promedio = (double)suma / (filas * columnas);

    cout << fixed << setprecision(2);
    cout << "Promedio: " << promedio << endl;
}

void mostrarSumaPorFilas(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    cout << "\n--- SUMA POR FILAS ---" << endl;

    for (int i = 0; i < filas; i++) {

        int sumaFila = 0;

        for (int j = 0; j < columnas; j++) {

            sumaFila = sumaFila + matriz[i][j];
        }

        cout << "Fila " << i + 1 << ": "
             << sumaFila << endl;
    }
}

void mostrarSumaPorColumnas(
    int matriz[][MAX_MATRIZ],
    int filas,
    int columnas
) {

    cout << "\n--- SUMA POR COLUMNAS ---" << endl;

    for (int j = 0; j < columnas; j++) {

        int sumaColumna = 0;

        for (int i = 0; i < filas; i++) {

            sumaColumna = sumaColumna + matriz[i][j];
        }

        cout << "Columna " << j + 1 << ": "
             << sumaColumna << endl;
    }
}

void ejercicio4() {

    int matriz[MAX_MATRIZ][MAX_MATRIZ];
    int filas, columnas;

    cout << "\n======================================" << endl;
    cout << "   EJERCICIO 4: SERIE REPETIDA" << endl;
    cout << "          EN MATRIZ" << endl;
    cout << "======================================" << endl;

    leerDatosRepetidoMatriz(filas, columnas);

    if (filas <= 0 || columnas <= 0 ||
        filas > MAX_MATRIZ || columnas > MAX_MATRIZ) {

        cout << "Dimensiones no validas." << endl;
        pausar();
        return;
    }

    llenarMatrizRepetida(
        matriz,
        filas,
        columnas
    );

    mostrarMatrizRepetida(
        matriz,
        filas,
        columnas
    );

    mostrarSumaTotalRepetida(
        matriz,
        filas,
        columnas
    );

    mostrarMayorMenorRepetida(
        matriz,
        filas,
        columnas
    );

    mostrarPromedioRepetida(
        matriz,
        filas,
        columnas
    );

    mostrarSumaPorFilas(
        matriz,
        filas,
        columnas
    );

    mostrarSumaPorColumnas(
        matriz,
        filas,
        columnas
    );

    pausar();
}

void mostrarMenu() {

    cout << "\n========================================" << endl;
    cout << "          MENU PRINCIPAL - C++" << endl;
    cout << "========================================" << endl;
    cout << "  1. Serie aritmetica en vector" << endl;
    cout << "  2. Serie aritmetica en matriz" << endl;
    cout << "  3. Serie repetida en vector" << endl;
    cout << "  4. Serie repetida en matriz" << endl;
    cout << "  5. Salir" << endl;
    cout << "========================================" << endl;
}

int main() {

    int opcion;

    do {

        mostrarMenu();

        cout << "Ingrese una opcion: ";
        cin >> opcion;

        switch (opcion) {

            case 1:
                ejercicio1();
                break;

            case 2:
                ejercicio2();
                break;

            case 3:
                ejercicio3();
                break;

            case 4:
                ejercicio4();
                break;

            case 5:
                cout << "\n========================================" << endl;
                cout << "    Gracias por usar el programa" << endl;
                cout << "========================================" << endl;
                break;

            default:
                cout << "\n*** OPCION NO VALIDA ***" << endl;
                cout << "Ingrese una opcion del 1 al 5." << endl;
                pausar();
        }

    } while (opcion != 5);

    return 0;
}
