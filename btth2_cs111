//kieu nguoi E dung ham min
//kieu nguoi W dung ham min thu i(i la so nguoi kieu W cho toi hien tai)
#include <iostream>
using namespace std;

int b[100];
void khoitao(int n)
{
     for(int i=0;i<n;i++)
     b[i]=0;
}
void min(int a[],int count,int n)// tim min thu count trong day a
{
     int min=9000000;
     int vt=0;
     for(int i=0;i<n;i++){
          if(a[i] < min && b[i]==0){
             min = a[i];
             vt=i;
           }
           else continue;
     }
      b[vt]=count;
     
}
 
void thuattoan(int a[],int k,int M)
{
     for(int count=1;count<=k;count++)
     {
             min(a,count,M);
     }
}
int Min_thuk(int a[], int k,int n){
    thuattoan(a,k,n);
     int vt=1;
     for(int i=0;i<n;i++)
     if(b[i]==k) vt=i;
    return vt;
}
int Min_x(int a[],int *temp,int M){//xet min ma khi doi chieu voi mang b phan tu tai do khac -1
    int min,m,i=0;
    while(temp[i]==-1){
        i++;
    }
    m=999999999;
    for(int j=i;j<M;j++){
        if(a[j]<m and temp[j]>0) {
            min=j;
            m=a[j];
        }
    }
    return min;
}
int main()
{
    int N,M,K;
    cout<<"nhap n,m,k ";
    cin>>N>>M>>K;
    char c[N];//tính cách người thứ i
    int r[M];//lượng nước còn lại sau khi đc n người uống ở mỗi chai
    for(int i=0;i<N;i++){//nhập tính cách
        cin>>c[i];
    }
    for(int i=0;i<M;i++){//nhập lượng nước còn lại
        cin>>r[i];
    }
 
    int result[N];//output
    int temp[M];//tinh
    for(int i=0;i<M;i++){
        temp[i]=3;
    }
    int count=0;
    for(int i=0;i<N;i++){
        if(c[i]=='E')
            result[i]=Min_x(r,temp,M);
        
        if(c[i]=='W'){
            count=count+1;
            if(temp[i]==0 ) count++;
            result[i]=Min_thuk(r,count,M);
            khoitao(M);
            
        }  ; 
        int t=temp[result[i]];
        if(t==3) {
            temp[result[i]]=K-1;
            }
        else if (t>0) temp[result[i]]=t-1;
        
        
    }
    for(int i=0;i<N;i++){
        cout<<result[i]+1<<"\n";
    }
    
    return 0;
}




