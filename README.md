# Zadacha
Первое домашнее задание по C++
#include <iostream>
#include <iomanip>
double average(const int* arr, int n) {
    int sum = 0;
    for (int i = 0; i < n; ++i) sum += arr[i];
    return static_cast<double>(sum) / n;
}
int minimum(const int* arr, int n) {
    int m = arr[0];
    for (int i = 1; i < n; ++i) if (arr[i] < m) m = arr[i];
    return m;
}
int maximum(const int* arr, int n) {
    int m = arr[0];
    for (int i = 1; i < n; ++i) if (arr[i] > m) m = arr[i];
    return m;
}
int frostyDays(const int* arr, int n) {
    int cnt = 0;
    for (int i = 0; i < n; ++i) if (arr[i] < 0) ++cnt;
    return cnt;
}
int main() {
    int n;
    std::cin >> n;
    int* temps = new int[n];
    for (int i = 0; i < n; ++i) std::cin >> temps[i];
    std::cout << std::fixed << std::setprecision(1) << average(temps, n) << "\n";
    std::cout << minimum(temps, n) << " " << maximum(temps, n) << "\n";
    std::cout << frostyDays(temps, n) << "\n";
    delete[] temps;
    return 0;
}
