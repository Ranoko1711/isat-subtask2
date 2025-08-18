# isat-subtask2
#include <iostream>
#include <bitset>
#include <string>
#include <sstream>

using namespace std;

// Function to convert Decimal to Binary
string decimalToBinary(int num) {
    return bitset<16>(num).to_string(); // 16-bit representation
}

// Function to convert Binary to Decimal
int binaryToDecimal(string bin) {
    return stoi(bin, nullptr, 2);
}

// Function to convert Decimal to Hexadecimal
string decimalToHex(int num) {
    stringstream ss;
    ss << hex << uppercase << num;
    return ss.str();
}

// Function to convert Decimal to Octal
string decimalToOctal(int num) {
    stringstream ss;
    ss << oct << num;
    return ss.str();
}

// Demo function
void demo() {
    cout << "\n--- Demo Conversions ---\n";
    cout << "Decimal 10 -> Binary: " << decimalToBinary(10) << endl;
    cout << "Binary 1010 -> Decimal: " << binaryToDecimal("1010") << endl;
    cout << "Decimal 255 -> Hexadecimal: " << decimalToHex(255) << endl;
    cout << "Decimal 64 -> Octal: " << decimalToOctal(64) << endl;
    cout << "------------------------\n\n";
}

int main() {
    int choice, num;
    string bin;

    do {
        cout << "\n===== Number Converter Menu =====\n";
        cout << "1. Decimal to Binary\n";
        cout << "2. Binary to Decimal\n";
        cout << "3. Decimal to Hexadecimal\n";
        cout << "4. Decimal to Octal\n";
        cout << "5. Demo Examples\n";
        cout << "0. Exit\n";
        cout << "Choose an option: ";
        cin >> choice;

        switch(choice) {
            case 1:
                cout << "Enter Decimal number: ";
                cin >> num;
                cout << "Binary: " << decimalToBinary(num) << endl;
                break;
            case 2:
                cout << "Enter Binary number: ";
                cin >> bin;
                cout << "Decimal: " << binaryToDecimal(bin) << endl;
                break;
            case 3:
                cout << "Enter Decimal number: ";
                cin >> num;
                cout << "Hexadecimal: " << decimalToHex(num) << endl;
                break;
            case 4:
                cout << "Enter Decimal number: ";
                cin >> num;
                cout << "Octal: " << decimalToOctal(num) << endl;
                break;
            case 5:
                demo();
                break;
            case 0:
                cout << "Exiting program...\n";
                break;
            default:
                cout << "Invalid choice, try again.\n";
        }
    } while(choice != 0);

    return 0;
}
