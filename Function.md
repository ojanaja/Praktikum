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
