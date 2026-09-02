#include <iostream>
using namespace std;

// Convert meters to centimeters
void convert(float meters, int) {
    cout << meters << " meters = " << meters * 100 << " centimeters" << endl;
}

// Convert kilometers to meters
void convert(float kilometers, double) {
    cout << kilometers << " kilometers = " << kilometers * 1000 << " meters" << endl;
}

int main() {
    float value;
    int choice;

    cout << "===== Unit Conversion =====" << endl;
    cout << "1. Meters to Centimeters" << endl;
    cout << "2. Kilometers to Meters" << endl;
    cout << "Enter your choice: ";
    cin >> choice;

    cout << "Enter value: ";
    cin >> value;

    switch (choice) {
        case 1:
            convert(value, 0);
            break;

        case 2:
            convert(value, 0.0);
            break;

        default:
            cout << "Invalid choice!" << endl;
    }

    return 0;
}
