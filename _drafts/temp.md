
/*
본격적으로 문제를 풀기 전에 주의해야 할 점이 있다. 입출력 방식이 느리면 여러 줄을 입력받거나 출력할 때 시간초과가 날 수 있다는 점이다.

C++을 사용하고 있고 cin/cout을 사용하고자 한다면, cin.tie(NULL)과 sync_with_stdio(false)를 둘 다 적용해 주고, endl 대신 개행문자(\n)를 쓰자. 단, 이렇게 하면 더 이상 scanf/printf/puts/getchar/putchar 등 C의 입출력 방식을 사용하면 안 된다.

https://www.acmicpc.net/problem/15552 (빠른 A+B)
https://www.acmicpc.net/board/view/22716 (추가 설명 및 다른 언어 빠른 입출력 방법)
 */


// 메모리: 1984 KB
// 시간: 192ms
void recur(int depth, string str)
{
	// cout << "===" << str << "\n"; // 이걸 붙이면 재귀의 흐름을 파악하기 쉬움
	if (depth == m)
		cout << str << "\n";
	else
		for (int d = 1; d <= n; d++)
			recur(depth + 1, str + to_string(d) + " ");
}

순열과 조합의 개념조차 헷갈리다니... 수학을 너무 오랫동안 등지고 있었나보다.





int test_internal_free(char *s)
{
	free(s);
}

int main(void)
{
	int i;
	char *s1;
	char *s2;

	s1 = malloc(4);
	for (i = 0; i < 4; i++)
	{
		s1[i] = i + '0';
	}
	s1[i] = '\0';
	printf("s1: %s\n", s1);
		for (i = 0; i < 4; i++)
	s2 = s1;
	test_internal_free(s2);
	printf("s1: %s\n", s1);

	return (0);
}
