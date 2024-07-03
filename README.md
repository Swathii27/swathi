#include <iostream>
#include<stdexcept>

using namespace std;

int main() {
    try {
        int age;
        cout << "Enter your age: ";
        cin >> age;

        if (age < 0) {
            throw invalid_argument("Error: Age cannot be negative.");
        } else if (age < 16) {
            throw invalid_argument("Error: You must be 16 or older to pre-register to vote.");
        } else if (age < 18) {
            cout << "You are not yet eligible to vote, but you can pre-register to vote once you turn 18.\n";
        } else {
            cout << "You are eligible to vote!\n";
        }
    } catch (const invalid_argument& e) {
        cerr << e.what() << endl;
    }

    return 0;
}
