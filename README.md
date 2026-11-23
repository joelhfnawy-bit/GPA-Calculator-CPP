# GPA-Calculator-CPP
A simple C++ program to calculate GPA using grades and credit hours

#include <iostream>
#include <iomanip>
using namespace std;

double convertToGPA(double mark) {
    if (mark >= 90) return 4.0;
    else if (mark >= 85) return 3.7;
    else if (mark >= 80) return 3.3;
    else if (mark >= 75) return 3.0;
    else if (mark >= 70) return 2.7;
    else if (mark >= 65) return 2.3;
    else if (mark >= 60) return 2.0;
    else if (mark >= 50) return 1.0;
    else return 0.0;
}

int main() {
    int subjects;
    double mark, hours;
    double totalPoints = 0;
    double totalHours = 0;

    cout << "Enter number of subjects: ";
    cin >> subjects;

    for (int i = 1; i <= subjects; i++) {
        cout << "\nSubject " << i << endl;

        cout << "Enter mark out of 100: ";
        cin >> mark;

        cout << "Enter credit hours: ";
        cin >> hours;

        double points = convertToGPA(mark);

        totalPoints += points * hours;
        totalHours += hours;
    }

    if (totalHours > 0) {
        double GPA = totalPoints / totalHours;

        cout << fixed << setprecision(2);
        cout << "\nYour GPA = " << GPA << " / 4.00";
    }

    return 0;
}
