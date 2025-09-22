#include <iostream>
#include <string>
using namespace std;

class Name {
public:
    string firstName, lastName;

    Name(string fName, string lName) {
        firstName = fName;
        lastName = lName;
    }

    // Overload + to combine names
    string operator+ (const Name &obj) {
        return firstName + " " + obj.lastName;
    }
};

int main() {
    Name n1("Mantavya", "xyz");
    Name n2("abc", "Anand");

    string combined = n1 + n2;  // Uses overloaded +
    cout << "Combined name: " << combined << endl;

    return 0;
}


//Expected Output
 Mantavya Anand
