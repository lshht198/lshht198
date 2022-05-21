#include <stdio.h>

int arr[5][5];// 전역으로 선언됬음 2가지 함수 이용
void Writerecord(void) // 학생별 성적 합계
{

	int sum;
	int i, j;
	for (i = 0; i < 4; i++)
	{
		sum = 0;
		printf("%d번쨰 학생의 성적 입력\n", i + 1);
		for (j = 0; j < 4; j++)
		{
			printf("과목:%d", j + 1);

			scanf_s("%d", &arr[i][j]);
			sum += arr[i][j];
		}
		arr[i][4] = sum;
	}
	
}
void WriteSumRecord(void)//과목별 성적 합계
{
	int sum;
	int i, k;
	for (i = 0; i < 4; i++)
	{
		sum = 0;
		for (k = 0; k < 4; k++)
		{
			sum += arr[k][i];
		}
		arr[4][k] = sum;
		arr[4][4] += sum;
	}
}
void ShowAllRecord(void)//배열 전체 출력
{
	int i, k;
	for (i = 0; i < 5; i++)
	{
		for (k = 0; k < 5; k++)
		{
			printf("%d ", arr[i][k]);
		}
		printf("\n");
	}
}
int main(void)
{
	Writerecord();
	WriteSumRecord();
	ShowAllRecord();
	return 0;

	}
