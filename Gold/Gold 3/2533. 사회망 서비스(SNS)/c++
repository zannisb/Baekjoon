#include <bits/stdc++.h>
using namespace std;

vector<int> v[1000001];
int dp[1000001][2];
bool visited[1000001];


void dfs(int cur){
  if(visited[cur]) return;
      
  visited[cur] = 1;
  
  dp[cur][0] = 0;
  dp[cur][1] = 1;
  
  for(auto next : v[cur]){
    if(visited[next]) continue;
    dfs(next);
    dp[cur][0] += dp[next][1];
    dp[cur][1] += min(dp[next][0],dp[next][1]);
  }
}

int main() 
{
  int N;
  cin >> N;
  
  for(int i = 0; i < N-1; i++){
    int tmp1,tmp2;
    cin >> tmp1 >> tmp2;
    v[tmp1].push_back(tmp2);
    v[tmp2].push_back(tmp1);
  }
  
/*  for(int i = 1; i <= N; i++){
    cout << i << " : ";
    for(int j = 0; j < v[i].size(); j++) cout << v[i][j] << " ";
    cout << "\n";
  }*/
  
  dfs(1);
  cout << min(dp[1][0],dp[1][1]);

  return 0;
}
