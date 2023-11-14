#include <iostream>
#include <fstream>
#include <string>
using namespace std;
int main() {
    ofstream batch_att;
    batch_att.open("classname.txt");
    if (!batch_att) {
        cout <<"File may not be open "<< endl;
        exit(1);
    }
    cout << "Enter your course name: ";
    string a;
    getline(cin, a); cout<<endl;
    int student_total;
    cout << "How many students are in class: ";
    cin >> student_total;
    cin.ignore(); cout << endl;
    string student_names[student_total]; string student_ids[student_total];
    cout << "Enter students names and IDs: " << endl;
    for (int i =0; i<student_total;i++) {
        cout << "Student " <<(i+1)<< " name: ";
        getline(cin, student_names[i]);

        cout << "Student " << (i+1) << " ID: ";
        getline(cin, student_ids[i]);
    }

    batch_att << "Your course is: " << a << endl;
    batch_att << "Total students are: " << student_total << endl;
    batch_att << "Student names along with their IDs " << endl;
    for (int i = 0; i < student_total; i++) {
        batch_att << student_names[i] << "  " << student_ids[i] << endl;
    }

    batch_att.close(); 
    cout << "All done" << endl;

    return 0;
}
