#include<iostream>
using namespace std;
int health = 100;
string inventory[10];
void Npc(int npc);
void Battle(int monsterHealth, char type);
int main() {

	int room = 1;

	string input;
	
	string shop;
	int turns = 0;
	


	cout << " You wake up after blacking out, you look down to find youself all dirty. All you remember was getting lost in a forest that looked way too big for a human to be walking around. You look around to find yourself in a cage, but through the cage you see that everything looks huge. It looks like an old temple built by giants, try finding your way outside and escape before you run into something dangerous.  " << endl;

	do {
		switch (room) {
		case 1:
			
			if (inventory[4] != "sword") {
				cout << " you got a sword!" << endl;
				inventory[4] = "sword";
			}
			cout << "You are in room 1. You can go to the left, middle or right" << endl;
			cin >> input;
			if (input == "m")
				room = 2;
			else if (input == "l")
				room = 3;
			else if (input == "r")
				room = 4;
			else if (input == "p")

				inventory[0] = "key";
			else if (input == "t")
				Npc(rand () % 3);
			else
				cout << "sorry, not an option." << endl;
			break;
		case 2:
			cout << "You are in room 2. It's a deadend" << endl;
			cin >> input;
			if (input == "b")
				room = 1;
			else
				cout << "sorry, not an option." << endl;
			break;
		case 3:
			cout << "You are in room 3. It's a deadend" << endl;
			cin >> input;
			if (input == "b")
				room = 1;
			else
				cout << "sorry, not an option." << endl;
			break;
		case 4:
			cout << "You are in room 4, you can go down " << endl;
			cin >> input;
			if (input == "d")
				room = 5;
			else if (input == "t")
				Npc(rand() % 3);
		
			else
				cout << "sorry, not an option." << endl;
			break;
		case 5:
			cout << "you are in room 5, you can go right" << endl;
			cin >> input;
			if (input == "r")
				room = 6;
			else
				cout << " sorry, not an option." << endl;
			break;
		case 6:
			cout << "You are in room 6, you can go down. " << endl;
			cin >> input;
			if (input == "d")
				room = 7;
			else
				cout << "sorry, not an option." << endl;
			break;
		case 7:
			cout << "You are in room 7, you can go down or you can go left" << endl;
			cin >> input;
			if (input == "d")
				room = 8;
			else if (input == "l")
				room = 9;
			else if (input == "t")
				Npc(rand() % 3);
			else
				cout << " sorry not an option." << endl;
			break;
		case 8:
			cout << "you are in room 8, it's a dead end. Go back to room 7" << endl;
			cin >> input;
			if (input == "b")
				room = 7;
			else
				cout << " sorry not an option." << endl;
			break;
		case 9:
			cout << " you are in room 9, you can go left " << endl;
			cin >> input;
			if (input == "l")
				room = 10;
			else
				cout << " sorry not an option." << endl;
			break;
		case 10:
			cout << " you are infront of the exit, you need a key" << endl;
			cin >> input;


		}

	} while (input != "q");
}	
		
	


	void monster() {  //monster gen
		int num = rand() % 100 + 1;
		if (num < 20) {
			cout << " a skeleton" << endl;
			Battle(30, 's');
		}
		else if (num < 50) {
			cout << " zombie" << endl;
			Battle(30, 's');
		}
		else if (num < 75) {
			cout << " spider" << endl;
			Battle(30, 's');
		}
		else
			cout << "no monsters" << endl;
	
	}


	void Battle(int monsterHealth, char type) {
		int damage= 0;
		string input;
		while (health > 0 && monsterHealth > 0) {

			if (type == 'p') {
				if (inventory[6] == "shield") {
					damage = rand() % 10;
					cout << " your shield blocks parts of the damage" << endl;
				}

				else
					damage = rand() % 20;
			}

			else if (type == 's')
				damage = rand() % 30;
			else if (type == 'z')
				damage = 30;


			cout << " the monster bites you" << damage << " damage." << endl;
			health -= damage;
			cout << " press 1 to fight, 2 for maguc, 3 to run" << endl;
			cin >> input;
			if (input == "1") {}

			if (inventory[4] == "sword") {
				damage = rand() % 60 + 20;
				cout << " you use your sword against the enemy" << endl;
			}
			else {
				damage = rand() % 50 + 10;
				cout << " you hit the monster with your fist" << endl;
			}
			damage = rand() % 21 + 30;
			cout << " you it the monster for" << damage << "damage" << endl;
			monsterHealth -= damage;
			cout << " the monnster has " << monsterHealth << " health left" << endl;
			cout << " press any key to continue . . ." << endl;
			cin >> input;
		}
		if (monsterHealth <= 0)
			cout << " you defeated the mnonster!" << endl << endl;
		else cout << " you died." << endl << endl;
	}
	void Npc( int npc) {
		if (npc == 0){
			int num = rand() % 3;
			if (num == 0) { cout << " They captured you too eh? " << endl; }
			if (num == 1) { cout << " The annanukis dont let anyone be in their territory and wont let anyone out of the temple. Not like there' s a way out anyway  " << endl; }
			if (num == 2) { cout << " Be careful with the creatures here, they're ten times bigger than normally. " << endl; }
			//generate random number here
			//have more if statements here, choose one based on the number generated
		
		}
		if (npc == 1) {
			int num = rand() % 3;
			if (num == 0) { cout << " " << endl; }
			if (num == 1) { cout << " " << endl; }
			if (num == 2) { cout << " " << endl; }
			
		}
		if (npc == 2) {
			int num = rand() % 3;
			if (num == 0) { cout << " " << endl; }
			if (num == 1) { cout << " " << endl; }
			if (num == 2) { cout << " " << endl; }
			
		}
	}


		
