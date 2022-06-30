# TikTakTu #
```cpp
#include <conio.h>
#include <iostream>
#include <windows.h>
#include <MMsystem.h>
using namespace std;

char peta [3][3]={{'1', '2', '3'}, {'4', '5', '6'}, {'7', '8', '9'}};
int baris;
int kolom;
char token='X';
bool seri=false;

struct player{
	string nama;
	int suit;
};
	//Variabel Global
	string hasilSuit1, hasilSuit2;
	player player1;
	player player2;
	
void setcolor(unsigned short color)
{
	HANDLE hCon = GetStdHandle(STD_OUTPUT_HANDLE);
	SetConsoleTextAttribute(hCon, color);
}

void setcolor(unsigned short color);
	
void playAgain();

//Matrix Peta
void matrixPeta()
{
   	cout << "   |    |   \n";
    cout << " " << peta[0][0] << " |  " << peta[0][1] << " |  " << peta[0][2] << "  \n";
    cout << "___|____|___\n";
    cout << "   |    |   \n";
    cout << " " << peta[1][0] << " |  " << peta[1][1] << " |  " << peta[1][2] << "  \n";
    cout << "___|____|___\n";
    cout << "   |    |   \n";
    cout << " " << peta[2][0] << " |  " << peta[2][1] << " |  " << peta[2][2] << "  \n";
    cout << "   |    |   \n\n";  
}

void inputDigit();

//Penentuan Menang-Kalah
bool menangKalah()
{	
	for (int i=0; i<3; i++)
	{
		if (peta[i][0]==peta[i][1] && peta[i][0]==peta[i][2] || peta[0][i]==peta[1][i] && peta[0][i]==peta[2][i])
		return true;
	}
	
	if (peta[0][0]==peta[1][1] && peta[1][1]==peta[2][2] || peta[0][2]==peta[1][1] && peta[1][1]==peta[2][0])
	{
		return true;
	}
	
	for (int i=0; i<3; i++)
	{
		for (int j=0; j<3; j++)
		{
			if (peta[i][j] != 'X' && peta[i][j] != 'O')
			{
				return false;
			}
		}
	}
	seri=true;
	return false;
}

//Input Nama, Deklarasi Pemenang, Program Utama
int main()
{
	
	cout<<"Masukkan nama pemain pertama: ";
    cin>>player1.nama;
    cout<<"Masukkan nama pemain kedua: ";
    cin>>player2.nama;
	
	//Suit
	suitSeri:
	cout<<"\nSebelum bermain, suit terlebih dahulu untuk menentukan yang jalan duluan. \n";
	cout << "1. Gajah\n2. Semut\n3. Orang\n\n";
	cout <<player1.nama<< " Silahkan Pilih : ";
	cin>>player1.suit;
	system ("cls");
	cout << "1. Gajah\n2. Semut\n3. Orang\n\n";
	cout <<player2.nama<< " Silahkan Pilih : ";
	cin>>player2.suit;
	system ("cls");
	
	//Eksekusi Suit
	if (player1.suit==1 && player2.suit==2 || player1.suit==2 && player2.suit==3 || player1.suit==3 && player2.suit==1)
	{
		hasilSuit1=player2.nama;
		hasilSuit2=player1.nama;
		cout<<hasilSuit1<<" jalan duluan.\n\n";
	}
	else if (player2.suit==1 && player1.suit==2 || player2.suit==2 && player1.suit==3 || player2.suit==3 && player1.suit==1)
	{
		hasilSuit1=player1.nama;
		hasilSuit2=player2.nama;
		cout<<hasilSuit1<<" jalan duluan.\n\n";
	}
	else if (player1.suit==1 && player2.suit==1 || player1.suit==2 && player2.suit==2 || player1.suit==3 && player2.suit==3)
	{
		cout<<"Hasil suit seri, suit kembali. \n";
		goto suitSeri;
		
	} 
	else
	{
		cout<<"Invalid.";
		goto suitSeri;
	}
		  
	//Loop Game
	while (!menangKalah())
	{
		matrixPeta();
		inputDigit();
		menangKalah();
	}
	
	//Deklarasi Game
	if (token=='X' && seri==false)
	{
		cout<<"Permainan Selesai. "<<player2.nama<<" Menang \n";
		playAgain();
	}
	
	else if (token=='O' && seri==false)
	{
		cout<<"Permainan Selesai. "<<player1.nama<<" Menang \n";
		playAgain();
	}
	
	else
	{
		cout<<"It's a draw \n";
		playAgain();
	}
}

//Input Digit
void inputDigit(){
	
	int digit;
	
	if (token=='X')
	{
		cout<<hasilSuit1<<" silahkan pilih nomer blok: ";
		cin>>digit;
	}
	
	if (token=='O')
	{
		cout<<hasilSuit2<<" silahkan pilih nomer blok: ";
		cin>>digit;
	}
	
	
	if (digit==1)
	{
		baris=0;
		kolom=0;
		
	}
	
	if (digit==2)
	{
		baris=0;
		kolom=1;
		
	}
	
	if (digit==3)
	{
		baris=0;
		kolom=2;
	}
	
	if (digit==4)
	{
		baris=1;
		kolom=0;
	}
	
	if (digit==5)
	{
		baris=1;
		kolom=1;
	}
	
	if (digit==6)
	{
		baris=1;
		kolom=2;
	}
	
	if (digit==7)
	{
		baris=2;
		kolom=0;
	}
	
	if (digit==8)
	{
		baris=2;
		kolom=1;
	}
	
	if (digit==9)
	{
		baris=2;
		kolom=2;
	}
	
	else if (digit<1 || digit>9)
	{
		cout<<"Invalid"<<endl;
	}
	
	//Eksekusi Input Digit
	if (token=='X' && peta[baris][kolom] !='X' && peta[baris][kolom] !='O')
	{
		peta[baris][kolom]='X';
		token='O';
	}
	
	else if (token=='O' && peta[baris][kolom] !='X' && peta[baris][kolom] !='O')
	{
		peta[baris][kolom]='O';
		token='X';
	}
	
	else
	{
		cout<<"There is no empty space!"<<endl;
	}
	
	  system ("cls");
	
}

//Function Play Again
void playAgain(){
	int mainLagi;

	cout<<	"1. Ya\n"
		  	"2. Tidak\n";
	cout<<"Ingin Bermain Kembali?";
	cin>>mainLagi;
	
	switch (mainLagi){
		case 1:
			main();
		break;
		case 2:
			cout<<"\nTerimakasih sudah bermain! \n";
		break;
	}
}
```
#Link Youtube
https://youtu.be/3TUuWoLyQw4
