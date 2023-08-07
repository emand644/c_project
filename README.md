# c_project
#include <iostream>
#include <cstdarg>

// Funktion, die eine variable Anzahl von Argumenten akzeptiert
double average(int num, ...) {
    va_list args;       // Variable Argumentliste
    double sum = 0;

    // Argumentliste initialisieren
    va_start(args, num);

    // Schleife, um alle Argumente zu verarbeiten
    for (int i = 0; i < num; ++i) {
        sum += va_arg(args, int); // Argument abrufen und auf die Summe addieren
    }

    // Argumentliste aufräumen
    va_end(args);

    // Durchschnitt berechnen
    return sum / num;
}

int main() {
    double result1 = average(3, 10, 15, 20);           // Durchschnitt von 10, 15 und 20
    double result2 = average(5, 2, 4, 6, 8, 10);      // Durchschnitt von 2, 4, 6, 8 und 10

    std::cout << "Durchschnitt 1: " << result1 << std::endl;
    std::cout << "Durchschnitt 2: " << result2 << std::endl;

    return 0;
}
