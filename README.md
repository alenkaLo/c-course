# c-Анализ текста 1
#include<conio.h>
#include<stdio.h>
#include <locale.h>
#define IN 1
#define OUT 0
int main(void) {
	setlocale(LC_ALL, "RUS");
	int i, symbol, nword, state = OUT;
	int nletter[50] = {  };
	nword = 0;
	printf("Введите текст. По окончанию ввода нажмите Ctrl/Z \n");
	while ((symbol = getchar()) != EOF)
	{
		if (symbol == ' ' || symbol == '\n' || symbol == '\t')
		{
			state = OUT;
		}
		else {

			if (state == OUT) {
				state = IN;
				nword++;
				printf("\n");
			}
			i = nword;
			nletter[i]++;
		}
	}

	printf("количество слов=%d\n", nword);
	for (i = 0; i <= nword; i++) {
		for (int k = 1; k <= nletter[i]; k++) printf("*");
		printf("\n");
	}
	return 0;
}
