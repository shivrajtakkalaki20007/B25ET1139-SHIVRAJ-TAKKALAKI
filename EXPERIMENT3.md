#include <iostream>
using namespace std;

// Function to read array elements
void read(int arr[], int n)
{
    cout << "Enter " << n << " numbers:" << endl;

    for (int i = 0; i < n; i++)
    {
        cin >> arr[i];
    }
}

// Function to display array elements
void display(int arr[], int n)
{
    for (int i = 0; i < n; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;
}

// Function to swap two numbers using call by reference
void swapNumbers(int &a, int &b)
{
    int temp = a;
    a = b;
    b = temp;
}

// Function to sort the array
void sortArray(int arr[], int n)
{
    for (int i = 0; i < n - 1; i++)
    {
        for (int j = 0; j < n - i - 1; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                swapNumbers(arr[j], arr[j + 1]);
            }
        }
    }
}

int main()
{
    int n;

    cout << "Enter the size of array: ";
    cin >> n;

    int arr[n];

    read(arr, n);

    cout << "Array before sorting: ";
    display(arr, n);

    sortArray(arr, n);

    cout << "Array after sorting: ";
    display(arr, n);

    return 0;
}
