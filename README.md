#include<iostream.h>
#include<conio.h>
#include<string.h>

class number
{
char na[30];

public:
number operator +(number n)
{
int i,j,k,l,m,x,c;
number p;
l=strlen(na);
m=strlen(n.na);
if(l>m)
{
k=l-m+1;
for(i=0;i<l;i++)
{
x=n.na[i];
na[i]=0;
na[k++]=x;
}
}

if(m>l)
{
k=m-l+1;
for(i=0;i<m;i++)
{
x=n.na[i];
na[i]=0;
na[k++]=x;
}
}

for(i=0;na[i]!=NULL;i++);
for(c=i;c>=0;c--)
{
p.na[c+1]=na[c]+n.na[c];
	if(p.na[c+1]>9)
	{
	p.na[c+1]=p.na[c+1]%10;
	p.na[c-1]=p.na[c-1]+1;
	}
}
return p;

}

friend void operator <<(ostream&,number);
friend void operator >>(istream&,number&);
};

void operator<<(ostream &pf,number n)
{
int i=0;
for(i=0;n.na[i]!=NULL;i++)
{
pf<<" "<<n.na[i]+48;
}
}

void operator>>(istream &sf,number &n)
{
int i;
cout<<"Enter the string:";
sf>>n.na;
for(i=0;n.na[i]!=NULL;i++)
{
n.na[i]=n.na[i]-48;
}
}


void main()
{
number n1,n2,n3;
clrscr();

cin>>n1;
cin>>n2;
n3=n1+n2;
cout<<n3;
getch();
}
