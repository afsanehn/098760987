#include <iostream>
using namespace std;
const int maxCol = 10;
void multiply(const int A[][maxCol], const int B[][maxCol], int m, int p, int n, int C[][maxCol]) {
    int i, j, k, sum;
    for (i = 0; i < m; i++)
        for (j = 0; j < n; j++) {
            sum = 0;
            for (k = 0; k < p; k++)
                sum += A[i][k] * B[k][j];

            C[i][j] = sum;
        }
}

void printMatrix(const int matrix[][maxCol], int row, int col) {
    for (int i = 0; i < row; i++) {
        for (int j = 0; j < col; j++)
            cout << matrix[i][j] << " ";
        cout << "\n";
    }
}

void inputMatrix(int matrix[][maxCol], int row, int col) {
    cout << "Enter elements of the matrix (" << row << "x" << col << "):\n";
    for (int i = 0; i < row; i++)
        for (int j = 0; j < col; j++)
            cin >> matrix[i][j];
}

int main() {
    int m, p, n;

    cout << "Enter rows and columns of first matrix: ";
    cin >> m >> p;
    int matrix1[maxCol][maxCol];
    inputMatrix(matrix1, m, p);

    cout << "Enter columns of second matrix (rows are " << p << "): ";
    cin >> n;
    int matrix2[maxCol][maxCol];
    inputMatrix(matrix2, p, n);

    int result[maxCol][maxCol];
    multiply(matrix1, matrix2, m, p, n, result);

    cout << "\nMatrix 1:\n";
    printMatrix(matrix1, m, p);
    cout << "\nMatrix 2:\n";
    printMatrix(matrix2, p, n);
    cout << "\nMultiplication Result:\n";
    printMatrix(result, m, n);

    return 0;
}


2. تابع inputMatrix برای دریافت مقدار هر ماتریس از ورودی اضافه شده است.


3. حفظ محدودیت maxCol برای سادگی مدیریت حافظه در آرایه‌های دو‌بعدی.


4. نمایش نتایج: ماتریس‌های ورودی و حاصل ضرب نمایش داده می‌شوند.



این کد انعطاف‌پذیرتر است و برای ماتریس‌هایی با ابعاد مختلف قابل استفاده خواهد بود.
