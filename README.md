# Cpp-basic-Projects

//Login page in Cpp


#include <iostream>
#include <string>
using namespace std;


void registerUser(string& regUsername, string& regPassword);
bool loginUser(const string& regUsername, const string& regPassword);

int main() {
    string registeredUsername, registeredPassword;
    int choice;

    cout << "Welcome to the Login System\n";
    cout << "1. Register\n";
    cout << "2. Login\n";
    cout << "3. Exit\n";

    do {
        cout << "\nEnter your choice (1-3): ";
        cin >> choice;

        switch (choice) {
        case 1:
            registerUser(registeredUsername, registeredPassword);
            break;

        case 2:
            if (loginUser(registeredUsername, registeredPassword)) {
                cout << "Login successful! Welcome, " << registeredUsername << "!\n";
            } else {
                cout << "Login failed. Please try again.\n";
            }
            break;

        case 3:
            cout << "Exiting the program. Goodbye!\n";
            break;

        default:
            cout << "Invalid choice. Please select 1, 2, or 3.\n";
        }
    } while (choice != 3);

    return 0;
}


void registerUser(string& regUsername, string& regPassword) {
    cout << "Register a new user\n";
    cout << "Enter a username: ";
    cin >> regUsername;
    cout << "Enter a password: ";
    cin >> regPassword;
    cout << "Registration successful!\n";
}

bool loginUser(const string& regUsername, const string& regPassword) {
    string username, password;

    cout << "Login\n";
    cout << "Enter your username: ";
    cin >> username;
    cout << "Enter your password: ";
    cin >> password;

    return (username == regUsername && password == regPassword);
}
