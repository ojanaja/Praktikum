# Tugas Struct
```cpp
#include <iostream>
using namespace std;

struct item{
	int plusBasicAttack;
	int plusAttackSpeed;
};


void buff(int basicAttack, int attackSpeed, int plusBasicAttack, int plusAttackSpeed){
	int buffBasicAttack=basicAttack+plusBasicAttack;
	int buffAttackSpeed=attackSpeed+plusAttackSpeed;
	
	cout<<"Basic attack: "<<basicAttack<<" + "<<plusBasicAttack<<" Setelah membeli item menjadi "<<buffBasicAttack<<"\n";
	cout<<"Attack speed: "<<attackSpeed<<" + "<<plusAttackSpeed<<" Setelah membeli item menjadi "<<buffAttackSpeed<<"\n";
}

int main(){
	
	buff(250, 150, 50, 20);
	
	return 0;
}
```
