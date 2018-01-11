#include "stdafx.h" 
#include <iostream> 
#include <vector> 
#include <cmath> 
#include <algorithm> 
#include <string> 
#include <fstream> 
#include <sstream> 
#include <cstdlib> 
#include <time.h> 


void sort_mat1(int* mat, int n) 
{ 
for (int i = n - 1; i >= 0; i--) 
{ 
for (int j = 0; j<i; j++) 
{ 
if (mat[j] > mat[j + 1]) 
{ 
int tmp = mat[j]; 
mat[j] = mat[j + 1]; 
mat[j + 1] = tmp; 
} 
} 
} 
} 
void sort_mat2(int** mat, int n) 
{ 
for (int i = 0; i < n; i++) 
{ 
for (int j = n - 1; j >= 0; j--) 
{ 
for (int k = 0; k<j; k++) 
{ 
if (mat[k][i] > mat[k+1][i]) 
{ 
int tmp = mat[k][i]; 
mat[k][i] = mat[k+1][i]; 
mat[k+1][i] = tmp; 
} 
} 
} 
} 
} 

int main() 
{ 
int ** mat; 
int n; 
std::cout « "VEDITE N = "; 
std::cin » n; 
mat = new int*[n]; 
srand(time(NULL)); 
for (int i = 0; i < n; i++) 
{ 
mat[i] = new int[n]; 
} 
for (int i = 0; i < n; i++) 
for (int j = 0; j < n; j++) 
{ 
mat[i][j]= rand() ; 

} 
for (int i = 0; i < n; i++) 
{ 
for (int j = 0; j < n; j++) 
{ 
std::cout « mat[i][j] «" "; 
} 
std::cout « std::endl; 
} 
std::cout « std::endl; 
for (int i = 0; i < n; i++) 
{ 
sort_mat1(mat[i],n); 
} 
for (int i = 0; i < n; i++) 
{ 
for (int j = 0; j < n; j++) 
{ 
std::cout « mat[i][j] « " "; 
} 
std::cout « std::endl; 
} 
std::cout « std::endl; 
sort_mat2(mat, n); 
for (int i = 0; i < n; i++) 
{ 
for (int j = 0; j < n; j++) 
{ 
std::cout « mat[i][j] « " "; 
} 
std::cout « std::endl; 
} 
std::cout « std::endl; 
system("pause"); 
return 0; 
}
