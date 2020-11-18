# Tutree-Internship
Write a program in C++ to print the following pattern
 1 2 3 4 5 6 7
 2 3 4 5 6 7
  3 4 5 6 7
   4 5 6 7
    5 6 7
     6 7
      7
     6 7
    5 6 7
   4 5 6 7
  3 4 5 6 7
 2 3 4 5 6 7
1 2 3 4 5 6 7


Ans :
#include <iostream>
using namespace std;

int main() {
	// your code goes here
	int n,space=0;
	cin>>n;
	for(int i=1;i<=n;i++)
	{
	    for(int k=1;k<=space;k++) cout<<" ";
	    for(int j=i;j<=n;j++)
	    cout<<j<<" ";
	    space++;
	    cout<<endl;
	}
	space=space-2;
	for(int i=n-1;i>=1;i--)
	{
	    for(int k=1;k<=space;k++) cout<<" ";
	    for(int j=i;j<=n;j++) cout<<j<<" ";
	    space--;
	    cout<<endl;
	}
	return 0;
	
}


Question 2:-
Find all substrings of a given string that contains all characters of other string.
 Example
string str1 = ‘XYYZXZYZXXYZ’;
string str2 = ‘XYZ’;
 
substring ‘YZX’ present at index 2
substring ‘XZY’ present at index 4
substring ‘YZX’ present at index 6
substring ‘XYZ’ present at index 9

Ans :

#include <iostream>
#include<string.h>
using namespace std;

int main() {
	// your code goes here
    string s1,s2; // considering the 2 strings consist of uppercase alphabets 
    cin>>s1>>s2;
    string::iterator it;
    char freq[27]={'0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0'};
    for(it=s2.begin();it!=s2.end();it++)
    freq[*it-65]++;
    
    string s3=s2.substr(0,s1.length());
    char compareWith[27]={'0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0','0'};
    
    for(it=s1.begin();it!=s1.begin()+s2.length();it++) compareWith[*it-65]++;
    int index=0;
   
    if(strcmp(compareWith,freq)==0) cout<<s1.substr(index+1,s2.length())<<endl;
    for(it=s1.begin()+s2.length();it!=s1.end();it++,index++)
    {
        
        compareWith[s1[index]-65]--;
        compareWith[*it-65]++;
        
        
        if(strcmp(compareWith,freq)==0) cout<<s1.substr(index+1,s2.length())<<endl;
        
    }
    
    
    
	return 0;
}
