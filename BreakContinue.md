# Tugas Praktikum Break #
```cpp


#include <iostream>

using namespace std;

struct player_t {
  int id;
  string nama;
  string tebakan;
};

int main() {
	
	cout << "Permainan jumlah tebak banyak hari (26-05-2022)\n\n";
  player_t player[] = {
    {
      1,
      "Jan",
      "170"
    },
    {
      2,
      "Yo",
      "245"
    },
    {
      3,
      "Kiw",
      "355"
    },
    {
      4,
      "Lang",
      "123"
    },
    {
      5,
      "Jamal",
      "145"
    }
  };

  int idPlayerYangHarusDikeluarkan = 5;

  player[1].nama = "Yo";

  for (int i = 0; i <= 5; i++) {

    if (player[i].id == idPlayerYangHarusDikeluarkan) {
      cout << player[i].nama << " menebak " << player[i].tebakan << " tebakan Jamal benar!\n";
      

      break;
    }

    cout << player[i].nama << " menebak " << player[i].tebakan << "\n";
  }

}
```


# Tugas Praktikum Continue #

```cpp

#include <iostream>
using namespace std;

struct siswa_t {
    int id;
    string nama;
    string jajanan;
    int harga;
};

int main() {
    
    int duitJajan = 5000;
    
    siswa_t siswa[] = {
        {1, "Adi", "Cilok", 4000},
        {2, "Firman", "Pentol", 4500},
        {3, "Sifa", "Cilor", 3000},
        {4, "Nunu", "Basreng", 2000},
        {5, "Pahri", "Jamur", 10000},
    };
    
    for(int i = 0; i < 5; i++) {
        
        if(siswa[i].harga >= duitJajan) {
            continue;
        }
        
        cout << siswa[i].nama << " bisa jajan " << siswa[i].jajanan << "\n";
    }
    
}

```
