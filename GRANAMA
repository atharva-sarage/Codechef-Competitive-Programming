#include<string.h>
#include<stdio.h>

int main()
{
	int i,c[27],d[27],t,u,v;
	char a[10010],b[1010];
	scanf("%d",&t);
	while(t--)
	{
		
		scanf("%s",a);
		scanf("%s",b);
		for(i=0;i<26;i++)
			c[i]=0;
		for(i=0;i<26;i++)
			d[i]=0;
		for(i=0;i<strlen(a);i++)
			c[a[i]-'a']++;
		for(i=0;i<strlen(b);i++)
			d[b[i]-'a']++;
		
		int flag=1,flag1=1;
		for(i=0;i<26;i++)
		{
			if((c[i]==0 && d[i]!=0)  || (c[i]!=0 && d[i]==0))
			{
				flag1=0;
			}
			if(c[i]!=d[i])
			{
				
				flag=0;
				
			}
		}
		if(flag!=flag1)
			printf("NO\n");
		else
			printf("YES\n");
	}
	return 0;
}