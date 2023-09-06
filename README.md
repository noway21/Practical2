#include <stdio.h>

int findGCD(int a, int b) {
    while (b != 0)  {
        int temp = b;
        b = a % b;
        a = temp;
   }
    return a;
}

int findLCM(int arr[], int n){
    int result = arr[0];
    for (int i = 1; i < n; i++) {
        int gcd = findGCD(result, arr[i]);
        result = (result * arr[i]) / gcd;
    }
    return result;
}

int main() {
    int n;
    printf("Введіть кількість чисел: ");
    scanf("%d", &n);

    int numbers[n];
    printf("Введіть %d натуральних чисел, розділених пробілом: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &numbers[i])
    }

    int lcm = findLCM(numbers , n);
    printf("Найменше спільне кратне: %d\n", lcm);

    return lcm;  // 
}
