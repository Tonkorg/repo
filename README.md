#include <iostream>
#include <iomanip>
#include <fstream>
#include <string>
#include <Windows.h>
#include "PHONELIST.h"
  
 
using namespace std;
void SearchByPhone();
bool LoadFileToRead();
void ReadFromFile(PhoneList *chel);
void SerchByFIO();
string name;
  
  
  
  
  
  
  
  
  
  
  int main() {
bool flag = true;
SetConsoleCP(1251);
SetConsoleOutputCP(1251);
while (flag) {
int a;
cout << "=========Меню=========" << endl << endl;
cout << "1: Загрузить файл" << endl;
cout << "2: Поиск по телефону" << endl;
cout << "3: Поиск по фаимилии" << endl;
cout << "4: Выйти из системы" << endl;
cout << "Ваш выбор (1-4): "; cin >> a;
switch (a) {
case 1: LoadFileToRead(); break;
case 2: SearchByPhone(); break;
case 3: SearchByFIO(); break;
case 4: flag = false; break;
case 5: ReadFromFile(); break;
default: cout << "Введите числа от 1 до 4"; break;
}
}
return 0;
}


  
