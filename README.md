# -3-
If17 Figure24
#include <iostream>
using namespace std;

int main() {
    cout << "************* If17 *************\n";

    double A, B, C;
    cout << "Enter A B C: ";
    cin >> A >> B >> C;

    // Перевірка чи числа впорядковані
    bool increasing = (A < B) && (B < C);
    bool decreasing = (A > B) && (B > C);

    if (increasing || decreasing) {
        // Якщо впорядковані — подвоїти
        A *= 2;
        B *= 2;
        C *= 2;
        cout << "Ordered (increasing/decreasing) -> doubled\n";
    } else {
        // Інакше — змінити знак
        A = -A;
        B = -B;
        C = -C;
        cout << "Not ordered -> sign flipped\n";
    }

    cout.setf(ios::fixed);
    cout.precision(3);

    cout << "Result: A = " << A << ", B = " << B << ", C = " << C << endl;
    return 0;
}

#include <iostream>
#include <cmath>
using namespace std;

/*
  ЛАБОРАТОРНА РОБОТА №3
  Завдання 2 — Геометрія (варіант 24)

  Умова:
  На площині задано квадрат зі стороною a, центр у (0,0),
  та коло радіуса r з тим самим центром.
  Визначити, чи належить точка (x,y) області:
    - правий-нижній квадрант (x >= 0, y <= 0)
    - всередині квадрата (|x| <= a/2, |y| <= a/2)
    - всередині кола (x^2 + y^2 <= r^2)
*/

int main() {
    cout << "********* Geometry (variant 24) *********\n";

    double a, r;
    cout << "Enter a (square side) and r (circle radius): ";
    cin >> a >> r;

    if (a <= 0 || r <= 0) {
        cerr << "Error: a and r must be positive.\n";
        return 0;
    }

    double x, y;
    cout << "Enter point coordinates (x y): ";
    cin >> x >> y;

    bool inSquare = (fabs(x) <= a/2.0) && (fabs(y) <= a/2.0);
    bool insideCircle = (x*x + y*y) <= r*r;
    bool inQ4 = (x >= 0.0) && (y <= 0.0);

    bool belongs = inSquare && insideCircle && inQ4;

    cout << boolalpha;
    cout << "\nIn square: " << inSquare;
    cout << "\nInside circle: " << insideCircle;
    cout << "\nIn 4th quadrant: " << inQ4;

    cout << "\n\nResult: ";
    if (belongs)
        cout << "Point belongs to the area (variant 24).\n";
    else
        cout << "Point is outside the area (variant 24).\n";

    return 0;
}
