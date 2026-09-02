#include <iostream>
using namespace std;

class Complex {
private:
    float real, imag;

public:
    void input() {
        cout << "Enter real part: ";
        cin >> real;
        cout << "Enter imaginary part: ";
        cin >> imag;
    }

    void display() {
        if (imag >= 0)
            cout << real << " + " << imag << "i";
        else
            cout << real << " - " << -imag << "i";
    }

    Complex add(Complex c) {
        Complex temp;
        temp.real = real + c.real;
        temp.imag = imag + c.imag;
        return temp;
    }

    Complex subtract(Complex c) {
        Complex temp;
        temp.real = real - c.real;
        temp.imag = imag - c.imag;
        return temp;
    }

    Complex multiply(Complex c) {
        Complex temp;
        temp.real = (real * c.real) - (imag * c.imag);
        temp.imag = (real * c.imag) + (imag * c.real);
        return temp;
    }

    Complex divide(Complex c) {
        Complex temp;
        float denominator = (c.real * c.real) + (c.imag * c.imag);

        temp.real = ((real * c.real) + (imag * c.imag)) / denominator;
        temp.imag = ((imag * c.real) - (real * c.imag)) / denominator;

        return temp;
    }
};

int main() {
    Complex c1, c2, result;
    int choice;

    cout << "Enter first complex number:\n";
    c1.input();

    cout << "\nEnter second complex number:\n";
    c2.input();

    do {
        cout << "\n\n===== Complex Number Calculator =====\n";
        cout << "1. Addition\n";
        cout << "2. Subtraction\n";
        cout << "3. Multiplication\n";
        cout << "4. Division\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                result = c1.add(c2);
                cout << "Result = ";
                result.display();
                break;

            case 2:
                result = c1.subtract(c2);
                cout << "Result = ";
                result.display();
                break;

            case 3:
                result = c1.multiply(c2);
                cout << "Result = ";
                result.display();
                break;

            case 4:
                result = c1.divide(c2);
                cout << "Result = ";
                result.display();
                break;

            case 5:
                cout << "Exiting program...";
                break;

            default:
                cout << "Invalid choice! Please try again.";
        }

    } while (choice != 5);

    return 0;
}
