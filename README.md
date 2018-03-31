#include <iostream>
#include <string>
#include <fstream>
#include <stack>
using namespace std;
int main() {
    ifstream in;
    ofstream out;
    in.open("brackets.in");
    out.open("brackets.out");
    string str;
    stack<char> pshe;
    while(!in.eof()){
        in >> str;
        int jojo;
        jojo = str.size();
        for(int i = 0; i < jojo; i++){
              if(str[i] == '(' || str[i] == '[') {
               pshe.push(str[i]);
                }
               else if (pshe.top() == '(' && str[i] == ')') {
                   pshe.pop();
               }
               else if (pshe.top() == '[' && str[i] == ']') {
                   pshe.pop();
               }
               else if (pshe.empty()) {
                   out << "YES" << endl;
                   break;
               }
               else { out << "NO" << endl;
              break;}
           }

        }

    return 0;
}
