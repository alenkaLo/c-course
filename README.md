# c-course#include <iostream>
#include <conio.h>
#include <stdio.h>
#include <math.h>
#include <locale>

int main()
{
	setlocale(LC_ALL, "RUS");
	int  month, year, x, y, day, day_of_week;
	int days_of_Month[] = { 31, 30, 31, 31, 30, 30, 31, 30, 31 , 31, 31, 28};

	do
	{
		printf("Введите год от 1582 до 4902гг: ");
		scanf_s("%d", &year);
	} while ((year < 1582) || (year > 4902));  // проверили верность ввода года


	y = (year % 100); //младшие числа года
	x = (year / 100); // старшие числа года

	do
	{
		printf("Введите номер месяца: ");
		scanf_s("%d", &month);
	} while ((month < 1) || (month > 12)); // проверим верность месяца

	if (month > 2) month -= 2;
	else month += 10;  //сделаем так чтоб 1-март ... 12-февраль
	
	if ((year % 4 == 0) && (year % 100 != 0))
		days_of_Month[12] = 29;       // если год весокосный то в феврале 29 дней

	do {
		printf("Введите день: ");
		scanf_s("%d", &day);
	} while ((day < 0) || (day > days_of_Month[month])); // проверка верноти дня

	

	 day_of_week = ((int)(2.6 * month - 0.2) + day + y + (int)(y / 4) + (int)(x / 4) - 2 * x) % 7;
	 if (day_of_week < 0) day_of_week += 7;
	switch (day_of_week)

	{

	case 0: printf("Воскресенье");

		break;

	case 1: printf("Понедельник");

		break;

	case 2: printf("Вторник");

		break;

	case 3: printf("Среда");

		break;

	case 4: printf("Четверг");

		break;

	case 5: printf("Пятница");

		break;

	case 6: printf("Суббота");

		break;

	default:

		break;
	}
	return 0;

}
