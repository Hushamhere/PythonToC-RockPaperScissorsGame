#include <iostream>
#include <ctime>
#include <string>
using namespace std;

void StartPage(){
    cout <<"\n______ROCK, PAPER, SCISSORS, BAZOOKA: THE GAME______\n" <<endl;
}

void introduction(){
    cout<<"---->Rock beats Scissors\n";
    cout<<"---->Paper beats Rock\n";
    cout<<"---->Scissors beats Paper\n";
    cout<<"---->Bazooka beats EVERYTHING\n"<<endl;
    
}

int randomNumber(){
    srand(time(NULL));
    int x;
    x = (rand() %4)+1;
    
    return x;
}

int choice(){
    bool verified = false;
    while(!verified){
    
    cout <<"Enter 0 to exit\n";
    cout <<"!CHOOSE YOUR WEAPON!\n";
    cout <<"Enter 1: Rock\n";
    cout <<"Enter 2: Paper\n";
    cout <<"Enter 3: Scissor\n";
    cout <<"Enter 4: BAZOOKA\n" <<endl;
    
    int x;
    cin >> x;
    
    if(x==0) {
        verified = true;
        return x;
    } else if(x >=5){
        std::cout << "\nEnter a Correct Number" << std::endl;
    } else {
        verified = true;
        return x;
    }
}
}

string convert(int converts){
    int number = converts;
    
    if(number == 1){
        return "Rock";
    } else if(number == 2){
        return "Paper";
    } else if(number == 3){
        return "Scissor";
    } else if(number == 4) {
        return "BAZOOKA";
    }
    
}



int main()
{
    bool verified = false;
    while(!verified){
    StartPage();
    introduction();
    
    int userChoice = choice();
    int compChoice = randomNumber();
        cout <<"\nUser Choice:  " <<convert(userChoice);
        cout <<"\nComp Choice:  " <<convert(compChoice)<<endl;
    
    if(userChoice == compChoice){
        cout <<"\nDRAW! Try again"<<endl;
    } else if(userChoice == 4){
        cout <<"\nBAZOOKA ALWAYS WINS!"<<endl;
    } else if(compChoice == 4){
        cout <<"\nYOU LOOOOOOOOSE!"<<endl;
    } else if(userChoice == 1 && compChoice == 2){
        cout <<"\nYOU LOOOOOOOOSE!"<<endl;
    }  else if(userChoice == 1 && compChoice == 3){
        cout <<"\nYOU WIN!"<<endl;
    }  else if(userChoice == 2 && compChoice == 1){
        cout <<"\nYOU WIN!"<<endl;
    }  else if(userChoice == 2 && compChoice == 3){
        cout <<"\nYOU LOOOOOOOOSE!"<<endl;
    }  else if(userChoice == 3 && compChoice == 1){
        cout <<"\nYOU LOOOOOOOOSE!"<<endl;
    }  else if(userChoice == 3 && compChoice == 2){
        cout <<"\nYOU WIN!"<<endl;
    } else if(userChoice = 0){
        verified ==true;
    }

}
return 0;
}
