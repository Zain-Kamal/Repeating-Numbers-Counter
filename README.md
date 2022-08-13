# Repeating-Numbers-Counter
## C++ code that counts the amount of repeating numbers in an interval


```
#include <iostream>
using namespace std;

int main() {
    int intervalA, intervalB, remainder;
    cout << "Enter two integers that represent an interval [A, B]: " << endl;
    cin >> intervalA >> intervalB;
    int counter = 0;
    for (int x = intervalA ; x <= intervalB ; x++) {
        if (x > 0 && x < 10)
            counter++;
        else if (x > 10 && x < 100)
            if (x % 11 == 0)
                counter++;
        else {
            for (int i = 11, tens = 100; i <= intervalB; i += tens) {
                while (x >= tens) {
                    i += tens;
                    tens *= 10;
                }
                if (x % i == 0 && x != 0) {
                counter++;
                break;
                }
            }
        }

    }
    cout << counter;

    return 0;

}
```  





