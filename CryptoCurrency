#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>

// User class to store basic user information
class User {
public:
    std::string username;
    double balance;

    User(std::string uname) : username(uname), balance(10000.0) {}  // Start with $10,000 balance
};

// Function to simulate a random price for a cryptocurrency
double getCryptoPrice() {
    return 50000.0 + (rand() % 10000);  // Random price between $50,000 and $60,000
}

// Function to display the menu and get user choice
int displayMenu() {
    int choice;
    std::cout << "\n1. Buy Crypto\n2. Sell Crypto\n3. Check Balance\n4. Exit\n";
    std::cout << "\nChoose an option: ";
    std::cin >> choice;
    return choice;
}

// Function to handle buying crypto
void buyCrypto(User &user, double price) {
    double amount;
    std::cout << "Enter amount to buy: ";
    std::cin >> amount;

    double cost = amount * price;
    if (user.balance >= cost) {
        user.balance -= cost;
        std::cout << "Bought " << amount << " units at $" << price << " each.\n";
    } else {
        std::cout << "Insufficient balance.\n";
    }
}

// Function to handle selling crypto
void sellCrypto(User &user, double price) {
    double amount;
    std::cout << "Enter amount to sell: ";
    std::cin >> amount;

    double earnings = amount * price;
    user.balance += earnings;
    std::cout << "\nSold " << amount << " units at $" << price << " each.\n";
}

// Main function to run the program
int main() {
    srand(static_cast<unsigned int>(time(0)));  // Seed for random price simulation

    std::string username;
    std::cout << "Enter your username: ";
    std::cin >> username;

    User user(username);
    std::cout << "\nWelcome, " << user.username << "! Your starting balance is $" << user.balance << ".\n";

    int choice;
    do {
        double price = getCryptoPrice();  // Get the current simulated price
        std::cout << "\nCurrent Crypto Price: $" << price << "\n";
        
        choice = displayMenu();

        if (choice == 1) {
            buyCrypto(user, price);
        } else if (choice == 2) {
            sellCrypto(user, price);
        } else if (choice == 3) {
            std::cout << "\nYour balance is $" << user.balance << ".\n";
        } else if (choice != 4) {
            std::cout << "Invalid option. Please try again.\n";
        }

    } while (choice != 4);

    std::cout << "\nGoodbye!";

    return 0;
}
