#include <iostream>
//#include "stdio.h"
//#include "string.h"

using namespace std;

// Create a strcmp1, similar to strcmp in C that
// returns -1 for a less than b, 0 for equal, and
// 1 for a greater than b
// Hello Phi
// hello

//notes : pass by ptr not string because string cannot be '\0'
//use const when have data/parameters that do not change
//passing by reference unnecessary due to const parameters
//in C++, ptr[i] refers to element in array, if ptr=ptr+1, ptr points to next ELEMENT in array


int strcmp1(const char * pt1,const  char * pt2)
{
  
  int check;
  if (pt1 == '\0' && pt2 != '\0' )
  {
    return -1;
  
  }
  if (pt1 != '\0' && pt2 == '\0' )
  {
    return 1;
 
  }
  if (pt1 == '\0' && pt1 == '\0')
  {
    return 0;
  
  }
  
  
  
  for (int i=0; pt1[i] != '\0' || pt2[i] != '\0' ; i++)
  {
    // aba vs aaa
    if (pt1[i] < pt2[i])
    {
      check = -1;
      break;
    }
  
    else if ( pt1[i] > pt2[i])
    {
      check = 1; 
      break;
    }
    
    else {
    check = 0;
    }
    
  }
    
    return check;

}





int main() {
  cout << "1 " << strcmp1("a", "b") << endl;
  cout << "2 " << strcmp1("b11", "a1231") << endl;
  cout << "3 " << strcmp1("aaa", "aabb") << endl;
  cout << "4 " << strcmp1("a123", "a123") << endl;
  cout << "5 " << strcmp1("a12345", "a123") << endl;
  cout << "6 " << strcmp1("a", 0) << endl;
  cout << "7 " << strcmp1(0, "aa1234") << endl;
  cout << "8 " << strcmp1(0, 0) << endl;
  return 0;
}

// Answer:  -1, 1, -1, 0, 1, 1, -1, 0
