# N-and-M
# c
한 줄에 하나씩 문제의 조건을 만족하는 수열을 출력한다. 중복되는 수열은 출력하면 안되며, 각 수열은 공백으로 구분해서 출력해야 한다.수열은 사전 순 출력하며 자연수 N과 M이 주어졌을 때, 아래 조건을 만족하는 길이가 M인 수열을 모두 구하는 프로그램을 작성해보자!

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int n,m;
int answer[100];
int relate[100]={0};
void dfs(int end){
	int i;
	if(end==m){
		for(i=0;i<m;i++){
		  printf("%d ",answer[i]);}
		printf("\n");}
	else{
		for(i=1;i<=n;i++){
			if(relate[i]==0){
				answer[end]=i;
				relate[i]=1;
				dfs(end+1);
				relate[i]=0;}}}
}


void main(){
	scanf("%d %d",&n,&m);
	dfs(0);
}
