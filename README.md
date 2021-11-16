#include<iostream>
using namespace std;
int health = 100;
int main() {

	int room = 1;

	string input;
	string inventory[10];
	string shop;
	int turns = 0;
	


	cout << "You wake up to find youself inside of a mansion!" << endl;

	do {
		switch (room) {
		case 1:
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
			health -= 10;
		}
		else if (num < 50) {
			cout << " zombie" << endl;
			health -= 30;
		}
		else if (num < 75) {
			cout << " spider" << endl;
			health -= 40; 
		}
		else
			cout << "no monsters" << endl;
	
	}


	void battle(int monsterHealth) {
		int damage;
		while (monsterHealth > 0 && health > 0) {
			damage = rand() % 20; 
			cout << " the monster bites you" << damage << " damage." << endl;
				health -= damage;
			cout << " You have" << health << " healtyh left" << endl;
			damage = rand() % 21 + 30;
			cout << " you it the monster for" << damage << "damage" << endl;
			monsterHealth -= damage; 
			cout << " the monnster has "
		}
