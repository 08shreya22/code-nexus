//# code-nexus
//The Talking Elevator

#include <iostream>
using namespace std;

int main() {
    int F;
    cout << "\nEnter top floor (F): ";
    cin >> F;

    int totalRings = 0, waitCount = 0
    int travelTime = 0; 

    for (int floor = 1; floor <= F; ++floor) 
    {
        // Time to move to this floor
        travelTime += 2;

        // No ring or wait if divisible by both 4 and 7
        if (floor % 4 == 0 && floor % 7 == 0)
        {
            continue;
        }

        if (floor % 2 != 0) {
            totalRings += 1;
        }
        else if (floor % 4 == 0) {
            totalRings += 2;
        }

        if (floor % 7 == 0) {
            waitCount++;
            travelTime += 5;
        }
    }

    cout << "\nElevator Report:\n";
    cout << "Total Ring Sounds: " << totalRings << endl;
    cout << "Total Waits: " << waitCount << endl;
    cout << "Total Time: " << travelTime << " seconds\n";

    return 0;
}

