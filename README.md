# c-courseУгадай число
#include <stdio.h>
#include <stdlib.h> // нужен для вызова функций rand(), srand()
#include <time.h> // нужен для вызова функции time()
#include<locale>
int main()
{
	setlocale(LC_ALL, "RUS");
	// Установить начальную точку генерирования последовательности
	// использовать функцию time(NULL)
	srand(time(NULL));
	int random_number, number_of_attempts, entered_number, i, max, min, y;
	max = 100;
	min = 0;
	// Получить случайное число
	random_number = rand() % (max - min + 1) + min;
	y = 0;
	do {
		printf("Введите количество попыток :");
		scanf_s("%d", &number_of_attempts);
		for (i = 0; i < number_of_attempts; ++i) {
			printf(" Введите число :");
			scanf_s("%d", &entered_number);
			if (entered_number == random_number) {
				printf("Правильно. Угадано с %d попытки \n", i+1);
				return  0;
			}
			else
			{
				if (entered_number < random_number)
					printf("загаданное число больше чем %d \n", entered_number);
				else
					printf("загаданное число меньше чем %d \n", entered_number);
			}
		}
			printf("Попытки закончились. \n Продолжить игру Yes/No (Нажать 1, если завершить) ");
			scanf_s("%d", &y);
	} while (y != 1);
	printf("загаданное число: %d", random_number);
		return 0;
}
