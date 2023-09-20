#include <iostream>
#include <map>
#include <vector>
int main()
{
    int n; // Розмір масиву
    std::cout << "Введіть розмір масиву (n <= 500): ";
    std::cin >> n;
    if (n <= 0 || n > 500)
    {
        std::cerr << "Розмір масиву має бути в межах [1, 500]." << std::endl;
        return 1;
    }
    double arr[500];
    std::map<double, int> frequency; // Мапа для зберігання частоти кожного числа
    std::cout << "Введіть елементи масиву: ";
    for (int i = 0; i < n; i++)
    {
        std::cin >> arr[i];
        frequency[arr[i]]++; // Збільшуємо частоту даного числа у мапі
    }
    double sumRepeated = 0.0;
    double productNonRepeated = 1.0;
    for (int i = 0; i < n; i++)
    {
        if (frequency[arr[i]] > 1)
        {
            // Якщо число повторюється, додаємо його до суми
            sumRepeated += arr[i];
        }
        else
        {
            // Якщо число не повторюється, множимо його до добутку
            productNonRepeated *= arr[i];
        }
    }
    std::cout << "Сума повторюються чисел: " << sumRepeated << std::endl;
    std::cout << "Добуток неповторюються чисел: " << productNonRepeated << std::endl;
    return 0;
}
