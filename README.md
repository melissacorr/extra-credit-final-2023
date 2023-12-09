//Description: this program will allow the user to play 
//Tom-And-Jerry game against a randomized computer opponent

#include <iostream>
#include <ctime>
#include <cstdlib>
using namespace std;

int main()
{
    int user_num;  //user's choice
    int comp_num;  //computer's choice

    // Generate the computer's choice randomly:
    srand(time(NULL));
    comp_num = rand() % 3 + 1;

    // Get the user's choice:
    cout << "Tom-And-Jerry Game" << endl
         << " 1. Spike" << endl
         << " 2. Tom" << endl
         << " 3. Jerry" << endl
         << "Enter a number : ";
    cin >> user_num;
    cout << endl;


    //TODO: Determine if the user wins, loses, or ties 
    //(or enters invalid input):
    if (user_num < 1 || user_num > 3)
    {
        cout << "ERROR - Invalid Input. Terminating Program." << endl;
        return 1; 
    }
    
    if (user_num == comp_num)
    {
        cout << "You both chose ";
        if (user_num == 1)
            cout << "Spike!";
        else if (user_num == 2)
            cout << "Tom!";
        else
            cout << "Jerry!";
        cout << " It's a tie!" << endl;
    }
    else if ((user_num == 1 && comp_num == 2) || 
    (user_num == 2 && comp_num == 3) || (user_num == 3 && comp_num == 1))
    {
        cout << "Tom beats Jerry! You won!" << endl;
    }
    else
    {
        cout << "Computer chose ";
        if (comp_num == 1)
            cout << "Spike!";
        else if (comp_num == 2)
            cout << "Tom!";
        else
            cout << "Jerry!";
        cout << " Computer won!" << endl;
    }

    // Exit the program:
    return 0;
}
