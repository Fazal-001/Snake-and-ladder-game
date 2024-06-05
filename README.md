# Snake-and-ladder-game



















 
#include<iostream>
#include<conio.h>
#include<stdlib.h>
#include<stdio.h>
#include<time.h>
using namespace std;
void draw_line(int n, char ch);
int main()
{
	int dicenumber, p1position = 1, p2position = 1, turn = 2;

	cout << "\n\n";					//These lines of code is to tell the head and tail of snake and to tell entry and exit point of ladder .
	draw_line(50, '-');
	cout << "\n\t\tSNAKE AT POSITION\n";
	draw_line(50, '-');
	cout << "\n\tFrom 98 to 28 \n\tFrom 95 to 24\n\tFrom 92 to 51\n\tFrom 83 to 19\n\tFrom 73 to 1\n\tFrom 69 to 33\n\tFrom 64 to 36\n\tFrom 59 to 17\n\tFrom 55 to 7\n\tFrom 52 to 11\n\tFrom 48 to 9\n\tFrom 46 to 5\n\tFrom 44 to 22\n\n";
	draw_line(50, '-');
	cout << "\n\t\t LADDER AT POSITION\n";
	draw_line(50, '-');
	cout << "\n\tFrom 8 to 26\n\tFrom 21 to 82\n\tFrom 43 to 77\n\tFrom 50 to 91\n\tFrom 62 to 96\n\tFrom 66 to 87\n\tFrom 80 to 100\n";
	draw_line(50, '-');
	cout << endl;

	int j = 100, array[10][10];

	for (int i = 0; i < 10; i++)				//This nested for loop is for giving each square a value from 1 to 100.
	{
		for (int x = 0; x < 10; x++)
		{
			array[i][x] = j--;
		}
	}
	for (int i = 0; i < 10; i++)
	{
		cout << endl;													//This nested for loop is for displaying the board.
		for (int x = 0; x < 10; x++)
		{
			if (array[i][x] == 100)											// this condition checks if it is a 100 box or not.
			{
				cout << "[   " << array[i][x] << "  ]";
			}
			else if (array[i][x] < 10)											//This condition is to check if that square in a single digit square or not.
			{
				cout << "[    " << array[i][x] << "   ]";
			}
			else																//if square has not any of above property then it has to be a two digit square.
			{
				cout << "[   " << array[i][x] << "   ]";
			}
		}
	}
	cout << "\nPress any key to start the game." << endl;
	_getch();

	while (turn != 0)
	{
		if (turn != 2)
		{
			if (turn % 2 == 0)
			{
				cout << "\n\nPress any key to clear screen." << endl;
				_getch();
				system("CLS");
			}
		}
		cout << "\n";
		cout << "\n";
		cout << "\n";
		cout << "\n";
		cout << "\n";

		srand(time(0));
		dicenumber = (rand() % 6) + 1;	//This line gives random number from 1 to 6 to variable 'dicenumber' which is used to determine each player location on board.

		if (turn % 2 == 0)					//if turn variable has odd number in it then it is player 1 move and vice versa.
		{
			cout << "\nPLAYER 1 Press any key to roll the dice and get the number. " << endl;
			_getch();
			cout << "Dice number of player 1 is : " << dicenumber << endl;
			switch(dicenumber)
				{
					case 1:
						cout << "___________________" << endl;
						cout << "|                 |" << endl;
						cout << "|                 |" << endl;
						cout << "|        *        |" << endl;
						cout << "|                 |" << endl;
						cout << "|_________________|" << endl;
					break;
					case 2:
						cout << "___________________" << endl;
						cout << "|                 |" << endl;
						cout << "|  *              |" << endl;
						cout << "|                 |" << endl;
						cout << "|              *  |" << endl;
						cout << "|_________________|" << endl;
						break;
					case 3:
						cout << "___________________" << endl;
						cout << "|                 |" << endl;
						cout << "|  *              |" << endl;
						cout << "|        *        |" << endl;
						cout << "|              *  |" << endl;
						cout << "|_________________|" << endl;
						break;
					case 4:
						cout << "___________________" << endl;
						cout << "|                 |" << endl;
						cout << "|  *           *  |" << endl;
						cout << "|                 |" << endl;
						cout << "|  *           *  |" << endl;
						cout << "|_________________|" << endl;
						break;
					case 5:
						cout << "___________________" << endl;
						cout << "|                 |" << endl;
						cout << "|  *           *  |" << endl;
						cout << "|        *        |" << endl;
						cout << "|  *           *  |" << endl;
						cout << "|_________________|" << endl;
						break;
					case 6:
						cout << "___________________" << endl;
						cout << "|                 |" << endl;
						cout << "|  *     *     *  |" << endl;
						cout << "|                 |" << endl;
						cout << "|  *     *     *  |" << endl;
						cout << "|_________________|" << endl;
						break;
				}
			if (dicenumber + p1position > 100)
			{
				cout << "Dice number is large cannot move. " << endl;
			}
			else
			{
				p1position = p1position + dicenumber;
			}
		}
		else
		{
			cout << "\nPLAYER 2 Press any key to roll the dice and get the number. " << endl;
			_getch();
			cout << "Dice number of player 2 is : " << dicenumber << endl;
			switch (dicenumber)
			{
				case 1:
					cout << "___________________" << endl;
					cout << "|                 |" << endl;
					cout << "|                 |" << endl;
					cout << "|        *        |" << endl;
					cout << "|                 |" << endl;
					cout << "|_________________|" << endl;
				break;
				case 2:
					cout << "___________________" << endl;
					cout << "|                 |" << endl;
					cout << "|  *              |" << endl;
					cout << "|                 |" << endl;
					cout << "|              *  |" << endl;
					cout << "|_________________|" << endl;
				break;
				case 3:
					cout << "___________________" << endl;
					cout << "|                 |" << endl;
					cout << "|  *              |" << endl;
					cout << "|        *        |" << endl;
					cout << "|              *  |" << endl;
					cout << "|_________________|" << endl;
				break;
				case 4:
					cout << "___________________" << endl;
					cout << "|                 |" << endl;
					cout << "|  *           *  |" << endl;
					cout << "|                 |" << endl;
					cout << "|  *           *  |" << endl;
					cout << "|_________________|" << endl;
				break;
				case 5:
					cout << "___________________" << endl;
					cout << "|                 |" << endl;
					cout << "|  *           *  |" << endl;
					cout << "|        *        |" << endl;
					cout << "|  *           *  |" << endl;
					cout << "|_________________|" << endl;
				break;
				case 6:
					cout << "___________________" << endl;
					cout << "|                 |" << endl;
					cout << "|  *     *     *  |" << endl;
					cout << "|                 |" << endl;
					cout << "|  *     *     *  |" << endl;
					cout << "|_________________|" << endl;
				break;
			}
			if (dicenumber + p2position > 100)
			{
				cout << "Dice number is large cannot move. " << endl;
			}
			else
			{
				p2position = p2position + dicenumber;
			}
		}
		switch (p1position)
		{
		case 97:					//SNAKE START FOR PLAYER 1
			p1position = 78;
			cout << "Player 1 got bitten by snake." << endl;
			break;
		case 95:
			p1position = 56;
			cout << "Player 1 got bitten by snake." << endl;
			break;
		case 88:
			p1position = 24;
			cout << "Player 1 got bitten by snake." << endl;
			break;
		case 62:
			p1position = 18;
			cout << "Player 1 got bitten by snake." << endl;
			break;
		case 48:
			p1position = 26;
			cout << "Player 1 got bitten by snake." << endl;
			break;
		case 36:
			p1position = 6;
			cout << "Player 1 got bitten by snake." << endl;
			break;
		case 32:
			p1position = 10;
			cout << "Player 1 got bitten by snake." << endl;
			break;					//SNAKE END FOR PLAYER 1
		case 80:					//LADDER START FOR PLAYER 1
			p1position = 99;
			cout << "Player 1 climbed by ladder." << endl;
			break;
		case 71:
			p1position = 92;
			cout << "Player 1 climbed by ladder." << endl;
			break;
		case 50:
			p1position = 67;
			cout << "Player 1 climbed by ladder." << endl;
			break;
		case 28:
			p1position = 76;
			cout << "Player 1 climbed by ladder." << endl;
			break;
		case 21:
			p1position = 42;
			cout << "Player 1 climbed by ladder." << endl;
			break;
		case 8:
			p1position = 18;
			cout << "Player 1 climbed by ladder." << endl;
			break;
		case 4:
			p1position = 14;
			cout << "Player 2 climbed by ladder." << endl;
			break;					//LADDER END FOR PLAYER 1
		}
		switch (p2position)
		{
		case 97:					//SNAKE START FOR PLAYER 2
			p2position = 78;
			cout << "Player 2 got bitten by snake." << endl;
			break;
		case 95:
			p2position = 56;
			cout << "Player 2 got bitten by snake." << endl;
			break;
		case 88:
			p2position = 24;
			cout << "Player 2 got bitten by snake." << endl;
			break;
		case 62:
			p2position = 18;
			cout << "Player 2 got bitten by snake." << endl;
			break;
		case 48:
			p2position = 26;
			cout << "Player 2 got bitten by snake." << endl;
			break;
		case 36:
			p2position = 6;
			cout << "Player 2 got bitten by snake." << endl;
			break;
		case 32:
			p2position = 10;
			cout << "Player 2 got bitten by snake." << endl;
			break;					//SNAKE END FOR PLAYER 2
		case 80:					//LADDER START FOR PLAYER 2
			p2position = 99;
			cout << "Player 2 climbed by ladder." << endl;
			break;
		case 71:
			p2position = 92;
			cout << "Player 2 climbed by ladder." << endl;
			break;
		case 50:
			p2position = 67;
			cout << "Player 2 climbed by ladder." << endl;
			break;
		case 28:
			p2position = 76;
			cout << "Player 2 climbed by ladder." << endl;
			break;
		case 21:
			p2position = 42;
			cout << "Player 2 climbed by ladder." << endl;
			break;
		case 8:
			p2position = 18;
			cout << "Player 2 climbed by ladder." << endl;
			break;
		case 4:
			p2position = 14;
			cout << "Player 2 climbed by ladder." << endl;
			break;					//LADDER END FOR PLAYER 2
		}
		for (int i = 0; i < 10; i++)
		{
			cout << endl;
			for (int x = 0; x < 10; x++)
			{
				if (p1position == array[i][x] && p2position == array[i][x])				//This if statement will check of player 1 and player 2 are on same square.
				{
					cout << "[ p1 , p2]";												//if they are on same square then it will print this.
				}
				else if (p1position == array[i][x] || p2position == array[i][x])		//This conditional statement will check if there is either player 1 or player 2 on that particular square.
				{
					if (p1position == array[i][x])										// This will check if it is player 1 on that particular square.
					{
						cout << "[Player 1]";
					}
					if (p2position == array[i][x])										// This will check if it is player 2 on that particular square.
					{
						cout << "[Player 2]";
					}
				}
				else if (array[i][x] == 100)											//after checking for both player 1 and player 2 positions controal will come to this condition and check if it is a 100 box or not.
				{
					cout << "[   " << array[i][x] << "  ]";
				}
				else if (array[i][x] < 10)											//This condition is to check if that square in a single digit square or not.
				{
					cout << "[    " << array[i][x] << "   ]";
				}
				else																//if square has not any of above property then it has to be a two digit square.
				{
					cout << "[   " << array[i][x] << "   ]";
				}
			}
		}
		turn++;
		if (p1position == 100 || p2position == 100)
		{
			if (p1position == 100)
			{
				cout << "\nPlayer 1 is Winner.";
			}
			if (p2position == 100)
			{
				cout << "\nPlayer 2 is Winner.";
			}
			turn = 0;
		}
	}
	_getch();
	return 0;
}
void draw_line(int n, char ch)
{
	for (int i = 0; i < n; i++)
		cout << ch;
}
