#include <bits/stdc++.h>
using namespace std;

const long long mod = 1000000007;

long long result;
long long arr[300000];
long long square[300000] = {1, 2}; // square[i] = 2^i

long long calculate(int i){
  if(square[i]) return square[i];
  if(i%2){
    return square[i] = (calculate(i/2) * calculate(i/2) % mod) * 2 % mod;
  }
  return square[i] = calculate(i/2) * calculate(i/2) % mod;
  
}

int main() 
{
  int N;
  cin >> N;
  for(int i = 0; i < N; i++) cin >> arr[i];
  sort(arr, arr+N);

  for(int i=N-1; i>0; i--){
    result += (arr[i] * (calculate(i)-1) % mod);
    result %= mod;
  }
  
  for(int i=0; i<N-1; i++){
    result -= (arr[i] * (calculate(N-i-1)-1) % mod);
    while(result<0) result+=mod;
  }

  cout << result;
  return 0;
}
