#include<iostream>
#include<vector>
#include<array>

using namespace std;
int main()
{
        string username;
        int password;
        cout << "Please Enter the username" << endl;
        cin >> username;
        cout << "Please Enter the password" << endl;
        cin >> password;
        if (username == "Teacher") {
            cout << "Welcome" << endl;
        }
        else if(username!="Teacher") {
            cout << "Invalid username" << endl;
          
        }
        if (password == 999)
        {
            cout << "login" << endl;
        }
        else if(password!=999) {

            cout << "Invalid Password!" << endl;
            return 0;

        }
    cout << "**  welcome to the school database **" << endl;
    char choice;
    string AddStudant;
    string RemoveStudant;
    int countnum;
    string studantGrade;
    string newStudent;
    string UpdateStudant;
    string displayStudant;
    string ExitProgram;
    string fullinformation;
    vector<string> studantarray;
    string temp;
    do {
        cout << " a. Add Studant  " << endl;
        cout << " b. RemoveStudant" << endl;
        cout << " c. Empty database" << endl;
        cout << " d. show number of studants" << endl;
        cout << " e. show all of studants" << endl;
        cout << "f . quit" << endl;
        cin >> choice;
        if (choice == 'f') {
            printf("Terminating the program...");
        }

        else if (choice == 'a')
        {
            cout << "Please Enter The Studant Name" << endl;
            cin >> AddStudant;
            cout << "Please Enter The studantGrade" << endl;
            cin >> studantGrade;
            fullinformation = AddStudant + " " + studantGrade;
            studantarray.push_back(fullinformation);
        }

        else if (choice == 'b')
        {
            cout << "Please Enter studant name to delete" << endl;
            cin >> RemoveStudant;
            for (int i = 0; i < studantarray.size(); i++) {
                if (studantarray[i].find(RemoveStudant) != -1) {
                    studantarray.erase(studantarray.begin() + i);
                    break;
                }
            }
            cout << " " << endl;
            cout << "studant has been removed" << endl;
            cout << " " << endl;
        }
        else if (choice == 'c')
        {
            studantarray.clear();
            cout << "DataBase cleared" << endl;
            cout << " " << endl;
        }
       
        else if (choice == 'd')
        {
            countnum = studantarray.size();
            cout << "Number Of studant " << countnum << endl;
        }
        else if (choice == 'e')
        {
            cout << "Name of studant in Array" << endl;
            for (int i = 0; i < studantarray.size(); i++) {
                cout << i << " " << studantarray[i] << " " << endl;
            }
        }
         
    } while (choice != 'f');
    return 0;
}
