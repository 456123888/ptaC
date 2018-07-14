# ptaC#include<stdio.h>
#include<math.h>
int main ()
{
    int k,p,q,i,g,h;
    scanf("%d",&k);
    if(k>2&&k<=2000000000)
    {
        for(i=2;i<=k;i++)
        {
            for(g=2;g<=sqrt(i);g++)//判断素数时用sqrt(i)别用i/2。不然运行量比较大，可能会超时//
            {
                if(i%g==0)
                    break;
            }
            if(g>sqrt(i))
            {
                p=i;
                q=k-p;
                for(h=2;h<=sqrt(q);h++)
                {
                    if(q%h==0)
                        break;
                }
                if(h>sqrt(q))
                {
                  printf("%d = %d + %d\n",k,p,q);
                  return 0;//直接退出，break太麻烦//
                }
            }
        }
    }
    return 0;
}
