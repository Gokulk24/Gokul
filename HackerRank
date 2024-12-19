#include <stdio.h>
#include <stdlib.h>

long arrayManipulation(int n, int m, int queries[m][3]) {
    long *arr = (long *)calloc(n + 1, sizeof(long));
    
    // Apply the prefix sum technique
    for (int i = 0; i < m; i++) {
        int a = queries[i][0];
        int b = queries[i][1];
        int k = queries[i][2];

        arr[a - 1] += k;
        if (b < n) {
            arr[b] -= k;
        }
    }

    // Calculate the maximum value using prefix sum
    long max_value = 0;
    long current_value = 0;
    for (int i = 0; i < n; i++) {
        current_value += arr[i];
        if (current_value > max_value) {
            max_value = current_value;
        }
    }

    free(arr);
    return max_value;
}

int main() {
    int n, m;
    scanf("%d %d", &n, &m);

    int queries[m][3];
    for (int i = 0; i < m; i++) {
        scanf("%d %d %d", &queries[i][0], &queries[i][1], &queries[i][2]);
    }

    long result = arrayManipulation(n, m, queries);
    printf("%ld\n", result);

    return 0;
}
