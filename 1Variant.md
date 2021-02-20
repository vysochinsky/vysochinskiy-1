#include "pch.h"
#include <iostream>
#include <string>
#include <Windows.h>
using namespace std;

int main()
{
	SetConsoleCP(1251);
	SetConsoleOutputCP(1251);
	setlocale(LC_ALL, "rus");
	int N;
	string Text;
	cout << "Введите текст\n";
	getline(cin, Text);
	cout << "Задайте длину: ";
	cin >> N;
	string Text2;
	int k = 0;
	for (int i = 0; i < Text.length(); i++)
	{
		if (Text[i] == ' '|| Text[i]=='.'||Text[i]==','||Text[i]==';'||Text[i]==':' || Text[i] == '!' || Text[i] == '?')
		{
			if (k == N)
			{
				cout <<"\n" <<Text2;
			}
			Text2 = "";
			k = 0;
		}
		else
		{
			Text2 += Text[i];
			k++;
		}
	}
	if (k == N)
	{
		cout << Text2;
		Text2 = "";
	}
}
