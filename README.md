#include <iostream>
using namespace std;

// Fungsi untuk membalik array integer (user-defined)
void reverseArray(int arr[], int n) {
    for (int i = 0; i < n / 2; i++) {
        int temp = arr[i];
        arr[i] = arr[n - i - 1];
        arr[n - i - 1] = temp;
    }
}

int main() {
    string input;
    cin >> input; // kata asli

    int n = input.length();
    int ascii[n];

    // Simpan ASCII
    for (int i = 0; i < n; i++) {
        ascii[i] = (int)input[i];
    }

    // Balik array ASCII
    reverseArray(ascii, n);

    // Cetak sandi
    cout << "Sandi: ";
    for (int i = 0; i < n; i++) {
        cout << ascii[i] << " ";
    }
    cout << endl;

    // Kembalikan sebagian kata asli
    reverseArray(ascii, n); // balik lagi supaya dapat asli

    cout << "Kata asli: ";
    for (int i = 0; i < n; i++) {
        cout << (char)ascii[i];
    }
    cout << endl;

    return 0;
}
