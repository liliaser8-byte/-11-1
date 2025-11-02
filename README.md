<img width="889" height="201" alt="image" src="https://github.com/user-attachments/assets/a02b3034-5096-4b74-8ea2-dd1a1a3cfabc" />
<img width="833" height="66" alt="image" src="https://github.com/user-attachments/assets/472594e1-8652-4a37-8ac6-1af610ad656e" />
Програма створює квадратну матрицю 4×4, зчитує її елементи, після чого для кожного стовпця обчислює середнє арифметичне тільки додатних чисел. Якщо у стовпці немає додатних елементів, програма повідомляє про це. Результати виводяться для кожного стовпця окремо.

```
#include <iostream>
#include <windows.h>
using namespace std;

// Функція для обчислення середнього арифметичного додатних елементів кожного стовпця
void calculateColumnAverages(double arr[4][4]) {
    for (int j = 0; j < 4; j++) {
        double sum = 0;
        int count = 0;

        // Перебір елементів у стовпці j
        for (int i = 0; i < 4; i++) {
            if (arr[i][j] > 0) {
                sum += arr[i][j];
                count++;
            }
        }

        // Вивід результату
        if (count > 0) {
            cout << "Середнє арифметичне додатних елементів стовпця "
                << j + 1 << " = " << sum / count << endl;
        }
        else {
            cout << "У стовпці " << j + 1 << " немає додатних елементів." << endl;
        }
    }
}

int main() {
    SetConsoleCP(1251);
    SetConsoleOutputCP(1251);

    double matrix[4][4];

    cout << "Введіть елементи матриці 4x4:" << endl;

    // Введення матриці
    for (int i = 0; i < 4; i++) {
        for (int j = 0; j < 4; j++) {
            cout << "matrix[" << i << "][" << j << "] = ";
            cin >> matrix[i][j];
        }
    }

    cout << "\nОбчислення середніх арифметичних додатних елементів кожного стовпця:\n";
    calculateColumnAverages(matrix);

    return 0;
}
```
