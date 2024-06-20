# praktica
#include <iostream> 
#include <vector> 

void Approximation(const std::vector<float>& x, const std::vector<float>& y) 
{ 
    int n = x.size(); 
    float sumX = 0, sumY = 0, sumXY = 0, sumXSquare = 0; 
 
    for (int i = 0; i < n; ++i) 
    { 
        sumX += x[i]; 
        sumY += y[i]; 
        sumXY += x[i] * y[i]; 
        sumXSquare += x[i] * x[i]; 
    } 
 
    float a = (n * sumXY - sumX * sumY) / (n * sumXSquare - sumX * sumX); 
    float b = (sumY - a * sumX) / n; 
 
    std::cout << " Approximation : y = " << a << "x + " << b << std::endl; 
} 
 
int main() 
{ 
    std::vector<float> x = {0, 1, 2, 3, 4}; 
    std::vector<float> y = {9, 7, 3, 8, 6}; 
 
    Approximation(x, y); 
 
    return 0; 
}
