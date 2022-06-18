# Total Belanja

```cpp
#include <iostream>
using namespace std;

void hitungHarga(int hargaSatuan, int jumlahBeli, int diskon) {
    
    int totalHarga=hargaSatuan*jumlahBeli;
    int totalDiskon = totalHarga*diskon/100;
    int totalHargaKurangDiskon=totalHarga-totalDiskon;
    
    cout << "Total harga setelah diskon : " << totalHargaKurangDiskon;
}

int main() {
    
    int apel, hargaApel;
    
    cout<<"Harga apel satuan: ";
    cin>>hargaApel;
    
    cout<<"Jumlah apel yang dibeli: ";
	cin>>apel;
	
	hitungHarga(hargaApel, apel, 20);

    return 0;
}
```
# Nilai Akhir

```cpp

#include <iostream>
using namespace std;

void nilaiDiTranskrip(int nilaiAkhir) {
    
    string index;
    
    if(nilaiAkhir >= 75) {
        index = "A";
    } else if(nilaiAkhir > 64) {
        index = "B";
    } else if(nilaiAkhir > 49) {
        index = "C";
    } else if(nilaiAkhir > 29) {
        index = "D";
    } else if(nilaiAkhir > 10){
    	index = "E";
	}
    
    
    cout << "Nilai akhirnya " << nilaiAkhir << ", maka indexnya adalah " << index;
}

int main() {
	
	int nilai;
	
	cout<<"Input Nilai: ";
	cin>>nilai;
	
    nilaiDiTranskrip(nilai);

    return 0;
}

```

# Rumus

```cpp
#include <iostream>
using namespace std;

void loop();
void persegiPanjang(){
	int panjang; int lebar;
    int luasPersegiPanjang;
    cout<<"Panjang: ";
    cin>>panjang;
    cout<<"Lebar: ";
    cin>>lebar;
    luasPersegiPanjang=panjang*lebar;
    cout<<"Luas Persegi Panjang: "<<luasPersegiPanjang<<"\n\n";
    loop();
}

void lingkaran(){
	int jariJari;
    float kelilingLingkaran;
    cout<<"Jari-Jari: ";
    cin>>jariJari;
    kelilingLingkaran=2*3.14*jariJari;
    cout<<"Keliling Lingkarang: "<<kelilingLingkaran<<"\n\n";
    loop();
}

void segitiga(){
	int alas; int tinggi;
    float luasSegitiga;
    cout<<"Alas: ";
    cin>>alas;
    cout<<"Tinggi: ";
    cin>>tinggi;
    luasSegitiga=0.5*alas*tinggi;
    cout<<"Luas Segitiga: "<<luasSegitiga<<"\n\n";
    loop();
}

int main(){
    int rumus;
    cout<<  "Pilihan Rumus \n"
            "1. Luas Persegi Panjang \n"
            "2. Keliling Lingkaran \n"
            "3. Luas Segitiga \n";
    cout<<"Masukkan Pilihan: ";
    cin>>rumus;

    switch (rumus){
        case 1:
        persegiPanjang();
        break;
        case 2:
        lingkaran();
        break;
        case 3:
        segitiga();
        break;
    }
    
}

void loop(){
	int loop;
	cout<<"Apakah Anda ingin mencoba rumus yang lain? \n"
			"1. Ya \n"
			"2. Tidak \n";
	cout<<"Masukkan Pilihan: ";
	cin>>loop;
	
	switch (loop){
		case 1:
		main();
		break;
		
		case 2:
		cout<<"Terimakasih, Sampai Jumpa!";
		break;
		
	}
}
```
