#include <stdio.h>
#include <string.h>
int main() {
	
	int t,n,i,s,v,f;
	scanf("%d",&t);
	while(t--)
	{
		scanf("%d",&n);
		s = f = v = 0;
		for(i=1;i<=n;i++)
		{
		    char a[16];
			scanf("%s",a);
			if(f==0)
			{
			  if(a[strlen(a)-3]=='m'&&a[strlen(a)-2]=='a'&&a[strlen(a)-1]=='n')
			++s;
			else
			++v;
			if(s==(v+2))
			f=1;
			if(v==(s+3))
			f=2;
			}
		}
		if(f==0)
		printf("draw\n");
		else if(f==1)
		printf("superheroes\n");
		else 
		printf("villains\n");
	}
	return 0;
}