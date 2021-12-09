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
			else#include<iostream>
#include <string>
using namespace std;
int health = 100;
string inventory[5] = { "bread", " ", " ", " ", " "};
void Npc(int npc);
void monster();
void Battle(int monsterHealth, char type);
int main() {

	int room = 1;

	string input;



	cout << "You wake up after blacking out, you look down to find youself all dirty and wet. All you remember was getting lost in a forest that looked like it was made for big dinosaurs." << endl;
	cout << "You look around to find yourself in a cage, but through the cage you see that everything looks huge.The cage is big     enough to walk out of it.It looks like an old temple built by giants, try finding your way out and escape before you run into something dangerous." << endl;
	cout << " " << endl;
	do {
		switch (room) {
		case 1:

			if (inventory[0] != "bread") {
				cout << " you have bread!" << endl;
				inventory[0] = "bread";
			}
			cout << "It's chilly in here, or should I say out here! You can fit mountains in this place. There a throne in the center and pillars that seem to be holding this place together. Reminds me of the history books we used to read in class about egyptian's pyramids." << endl;
			cout << "There's 3 openings, You can go to the opening on the Left, Right or the Middle " << endl; 
			cout << " Who is that old man there ? (Press 't' to talk)" << endl;
			cin >> input;
			if (input == "middle")
				room = 2;
			else if (input == "left")
				room = 3;
			else if (input == "right")
				room = 4;
			
			else if (input == "t")
				Npc(rand() % 3);

			else
				cout << "sorry, not an option." << endl;
			break;
		case 2:
			cout << "This room seems to be a type of blacksmith room. Everything is twice my size, no way I can carry any of this. These weapons look so hazardous. " << endl;
			cout << " There seems to be no other opening ahead. (press 'b' to go back)" << endl;
			cout << " you see something shine in the corner of the room. (Press 'p' to pick up items)" << endl;
			cin >> input;
			if (input == "b")
				room = 1;
			else if (input == "p" && inventory[3] == " ") {

				cout << " you reach down and find a sword" << endl;
				inventory[3] = "Sword";
			}
			else
				cout << "sorry, not an option." << endl;
			break;
		case 3:
			cout << "This place gives me chills, there's drawings of what seems to be giants fighting humans. I need to get out of this place fast!" << endl;
			cout << " (Press 'b' to go back)" << endl;
			cin >> input;
			if (input == "b")
				room = 1;
			else
				cout << "sorry, not an option." << endl;
			break;
		case 4:
			cout << "The roof on this place looks like it got shorter, or is the floor just getting steeper? Can't really tell. This place doesnt have much... besides those giant stairs going Down..." << endl;
			cin >> input;
			if (input == "down")
				room = 5;
			else if (input == "b")
				room = 1;

			else
				cout << "sorry, not an option." << endl;
			break;
		case 5:
			cout << "*gasping for air* That was tiring, hopefully there wont be a need to go back there." << endl;
			cout << " This room seems a little strange. It's just sandy filled with big *gulp* spiderwebs." << endl;
			cout << " There's another opening to the Right." << endl;
			cin >> input;
			if (input == "right")
				room = 6;
			else if (input == "b") {
				room = 4;
				monster();
			}
			else
				cout << " sorry, not an option." << endl;
			break;
		case 6:
			cout << "Blood stains on the ground. They dont look too old... Kind of looks like a execution place. The axe is giant, Bigger than the ones in that weaponary room from earlier. It stinks in here! There's another opening Down" << endl;
			cin >> input;
			if (input == "down")
				room = 7;
			else if (input == "b")
				room = 5;
			else
				cout << "sorry, not an option." << endl;
			break;
		case 7:
			cout << "I feel like this place will never end! Endless cycle of rooms (T-T) Though this place has more openings then the other few rooms. The endless hallway going to the Right or a dark room going Down " << endl;
			cout << " What's tha shiny thing on the floor ( Press 'p' to pick up)" << endl;
			cin >> input;
			if (input == "down")
				room = 8;
			else if (input == "right")
				room = 9;
			else if (input == "b")
				room = 6;
			else if (input == "p" && inventory[4] == " ") {

				cout << " you reach down and find a sheild" << endl;
				inventory[4] = "shield";
			}
			else
				cout << " sorry not an option." << endl;
			break;
		case 8:
			cout << "I can't see anything! It's pitch black. I could only the light from where I came from." << endl;
			cout << " (press 'b' to go back)" << endl;
			cin >> input;
			 if (input == "flashlight" && inventory[1] == "flashlight") {

				cout << " you turn on the light and find a key" << endl;
				inventory[2] = "key";
			}
			
			 else if (input == "b")
				room = 7;
			else
				cout << " sorry not an option." << endl;
			break;

		case 9:
			cout << " Just keep Straight! Almost there! " << endl;
			cin >> input;
			if (input == "Straight")
				room = 10;
			else if (input == "b")
				room = 8;
			else
				cout << " sorry not an option." << endl;
			break;
		case 10:
			cout << " you are infront of the exit, you need a key" << endl;
			
			if ( inventory[2] == "key") {

				cout << " you have escaped the temple. As you walk out of the temple you look out to see hundreds of giants walking around. There is no way out of this place, ahead is a forest that looks as endless as the ocean. As you look up you get picked up by a giant and get put back from where you first started chained up. There's no escape" << endl;
			}
			else
				cout << " You did not get the key and you got stepped on " << endl;
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
			cout << " Giant Hand" << endl;
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
				if (inventory[4] == "shield") {
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
			cout << " press 1 to fight, 2 for magic, 3 to run" << endl;
			cin >> input;
			if (input == "1") {}

			if (inventory[3] == "sword") {
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
			if (num == 1) { cout << " The giants dont let anyone be in their territory and wont let anyone out of the temple. Not like there's a way out anyway  " << endl; }
			if (num == 2) { cout << " Be careful with the creatures here, they're ten times bigger than normally. " << endl; }
			//generate random number here
			//have more if statements here, choose one based on the number generated
		
		}
		if (npc == 1) {
			int num = rand() % 3;
			if (num == 0) { cout << "*coughs*" << endl; }
			if (num == 1) { cout << "I've searched everywhere for an escape. There's not way" << endl; }
			if (num == 2) { cout << "I was trying to discover something. I regret it now" << endl; }
			
		}
		if (npc == 2) {
			int num = rand() % 3;
			if (num == 0) { cout << " People who discover something new a large amount of money, I tried to do the same and look where it got me, hehe " << endl; }
			if (num == 1) { cout << " These Chains are so heavy, they make me lose energy more everyday  " << endl; }
			if (num == 2) { cout << " I'm so hungry, do you have any food by chance ? " << endl; }
			
		}
		{
			cout << " (type 'b' to give bread, L to leave)" << endl;
				if (inventory[0] == "bread") {
			inventory[0] = " ";
			cout << " you give the prisoner bread, in exchnage he gives you a flashlight" << endl;
			inventory[1] = "flashlight";
		}
		}
	}


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


		
