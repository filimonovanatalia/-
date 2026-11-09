# -
#include <stdio.h>
#include <locale.h>
int check(double x, double y) {
    if (y >= 0 && (x * x + y * y <= 36.0) && !(x >= 0 && (x * x + y * y <= 9.0))) {
        return 1;
    }
    return 0;
}
int main() {
    setlocale(LC_CTYPE, "RUS");
    int choice;
    int cont;
        printf("\nменю\n");
        printf("1. Проверить принадлежность точки\n");
        printf("2. Нарисовать область\n");
        printf("3. Вычислить функцию (task1)\n");
        printf("4. Завершить программу.\n");
        printf("Выберите пункт: ");
        scanf("%d", &choice);
        switch (choice) {
        case 1: {
            task2();
            break;
        }
        case 2: {
            printf("\nРисуем фигуру:\n\n");
            draw_area();
            break;
        }
        case 3: {
            task1();
            break;
        }
        case 4: {
            break;
            printf("\nПрограмма завершена.\n");
            return 0;
            break;
            return 0;
        }

        default: {
            printf("\nВведено неверное число.\n");
            return 0;
            break;
        }
        }
}
void draw_area() {
    for (double y = 6.0; y >= 0.0; y -= 0.5) {
        for (double x = -6.0; x <= 6.0; x += 0.5) {
            if (check(x, y)) {
                printf("* ");
            }
            else {
                printf("  ");
            }
        }
        printf("\n");
    }
}
void task1() {
    double x1;
    printf("Введите значение x: ");
    scanf("%lf", &x1);
    if (x1 <= 13) {
        printf("Результат: %.4f\n", (-x1 * x1 * x1 + 9.0));
    }
    else {
        printf("Результат: %.4f\n", (-3.0 / (x1 + 1.0)));
    }
}
void task2() {
    double x, y;
    printf("Введите координаты x и y: ");
    scanf("%lf %lf", &x, &y);
    if (check(x, y) == 1) {
        printf("Точка принадлежит области.\n");
    }
    else {
        printf("Точка НЕ принадлежит области.\n");
    }
}
