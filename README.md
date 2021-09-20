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
 // функция загрузки файла
bool LoadFileToRead() {
PhoneList chel;
cout << "Введите имя файла: ";
cin >> name;
ifstream fout;
fout.open(name, ios::binary | ios::in);
if (!fout.is_open() || fout.peek() == EOF) {
cout << "Ошибка открытия файла или он пуст!" << endl;
return false;
}
else {
while (fout.peek() != EOF) {
fout.read((char*)&chel, sizeof(PhoneList));
}
cout << "Запись гуд)" << endl;
}
fout.close();
return true;
}
// функция вывода содержимого файла
void ReadFromFile() {
ifstream fout;
PhoneList chel;
fout.open(name, ios::binary | ios:: in);
cout << left << setw(8) << "Телефон" << setw(20) << "ФИО" << setw(21) << "Улица" << setw(8) <<
"Дом" << setw(10) << "Этаж" << endl <<
"_____________________________________________________________" << endl;
while(fout.peek() != EOF){
fout.read((char*)&chel, sizeof(PhoneList));
cout << left << setw(8) << chel.Phone << setw(20) << chel.FIO << setw(21) << chel.street
<< setw(10) << chel.House << setw(10) << chel.Flat << endl;
}
fout.close();
}

  
  
  
  
  
  
  
  
  
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


  
