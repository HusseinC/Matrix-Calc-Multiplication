#include <iostream>

using namespace std;

int main() {
  // Declare variables for the sizes of the matrices
  int n, m;

  // Prompt the user to enter the sizes of the matrices
  cout << "Enter the number of rows for the first matrix: ";
  cin >> n;
  cout << "Enter the number of columns for the first matrix: ";
  cin >> m;

  // Declare the first matrix with the size specified by the user
  int matrix1[n][m];

  // Prompt the user to enter the values for the first matrix
  cout << "Enter the values for the first matrix:" << endl;
  for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
      cout << "Matrix1[" << i << "][" << j << "]: ";
      cin >> matrix1[i][j];
    }
  }

  // Declare variables for the sizes of the second matrix
  int p, q;

  // Prompt the user to enter the sizes of the second matrix
  cout << "Enter the number of rows for the second matrix: ";
  cin >> p;
  cout << "Enter the number of columns for the second matrix: ";
  cin >> q;

  // Declare the second matrix with the size specified by the user
  int matrix2[p][q];

  // Prompt the user to enter the values for the second matrix
  cout << "Enter the values for the second matrix:" << endl;
  for (int i = 0; i < p; i++) {
    for (int j = 0; j < q; j++) {
      cout << "Matrix2[" << i << "][" << j << "]: ";
      cin >> matrix2[i][j];
    }
  }

  // Check that the matrices can be multiplied (i.e., the number of columns in the first matrix is equal to the number of rows in the second matrix)
  if (m != p) {
    cout << "Error: The matrices cannot be multiplied." << endl;
    return 0;
  }

  // Declare the result matrix with the size n rows by q columns (i.e., the number of rows in the first matrix by the number of columns in the second matrix)
  int result[n][q];

  // Initialize the result matrix to all zeros
  for (int i = 0; i < n; i++) {
    for (int j = 0; j < q; j++) {
      result[i][j] = 0;
    }
  }

  // Multiply the matrices and store the result in the result matrix
  for (int i = 0; i < n; i++) {
    for (int j = 0; j < q; j++) {
      for (int k = 0; k < m; k++) {
        result[i][j] += matrix1[i][k] * matrix2[k][j];
      }
    }
  }

  // Print the result matrix
  cout << "The result of multiplying the two matrices is: " << endl;
for (int i = 0; i < n; i++) {
for (int j = 0; j < q; j++) {
cout << result[i][j] << " ";
}
cout << endl;
}

return 0;
}

