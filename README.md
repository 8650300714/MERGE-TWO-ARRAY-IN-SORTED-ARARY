# MERGE-TWO-ARRAY-IN-SORTED-ARARY
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter the size of array 1: ";
    cin >> n;
    int arr1[20];
    cout << "Enter the sorted elements of array 1:" << endl;
    for (int i = 0; i < n; i++) {
        cout << "Element " << i << ": ";
        cin >> arr1[i];
    }

    int m;
    cout << "Enter the size of array 2: ";
    cin >> m;
    int arr2[40];
    cout << "Enter the sorted elements of array 2:" << endl;
    for (int j = 0; j < m; j++) {
        cout << "Element " << j << ": ";
        cin >> arr2[j];
    }

    int o = n + m;
    int arr3[60];
    int i = 0, j = 0, k = 0;

    // Merge the two arrays into arr3
    while (i < n && j < m) {
        if (arr1[i] < arr2[j]) {
            arr3[k] = arr1[i];
            i++;
        } else {
            arr3[k] = arr2[j];
            j++;
        }
        k++;
    }

    // Copy remaining elements of arr1, if any
    while (i < n) {
        arr3[k] = arr1[i];
        i++;
        k++;
    }

    // Copy remaining elements of arr2, if any
    while (j < m) {
        arr3[k] = arr2[j];
        j++;
        k++;
    }

    // Print the merged sorted array
    cout << "Merged sorted array:" << endl;
    for (int k = 0; k < o; k++) {
        cout << arr3[k] << " ";
    }
    cout << endl;

    return 0;
}
