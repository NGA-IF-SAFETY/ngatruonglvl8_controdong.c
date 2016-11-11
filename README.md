#**I.CÁC KHÁI NIỆM**      

##*1.Một biến động*    
-  Là các biến được tạo ra lúc chạy chương trình, tùy theo nhu cầu, hoàn toàn không được xác định từ trước    
-  Các biến động đều không có tên     

##*2.Cách tạo biến động và truy cập đến biến động*   

-  Việc tạo ra biến động và xóa nó đi (để thu hồi lại bộ nhớ) được thực hiện nhờ các hàm malloc(), free(), calloc(), relloc() đã có sẵn trong stdlib.h   
-  Việc truy nhập biến động được thực hiện nhờ các biến con trỏ  

#**II.CẤP PHÁT VÀ GIẢI PHÓNG BỘ NHỚ**    

##*1. Trước hết là hàm malloc:*    
 
void * malloc ( size_t size );    

Hàm này dùng để cấp phát bộ nhớ động với kích thước size.   

Ví dụ:   
a=(int)malloc(sizeof(int));     

##*2. Hàm calloc:*   

void * calloc ( size_t num, size_t size );   

ví dụ:int *a = (int *) calloc(10, sizeof( int ));    

Hàm này dùng để cấp phát bộ nhớ động cho một mảng với size_t num là số phần tử của mảng.    

ví dụ: 
`#include <stdio.h>`   
`#include <stdlib.h>`  
 
int main ()    

{  
  int i,n;   
  
  int * pData;   
  
  printf ("Amount of numbers to be entered: ");    
  
  scanf ("%d",&i);   
  
  pData = (int*) calloc (i,sizeof(int));    
  
  if (pData==NULL) exit (1);   
  
  for (n=0;n<i;n++)   
  
  {   
    printf ("Enter number #%d: ",n);    
    
    scanf ("%d",&pData[n]);    
    
  }   
  printf ("You have entered: ");    
  
  for (n=0;n<i; n++)  
  
  printf ("%d ",pData[n]);    
  
  free (pData);   
  
  return 0;   
  
}  

##*3. Hàm realloc:*   

void * realloc ( void * ptr, size_t size );    

Dùng để thay đổi kích thước bộ nhớ đã cấp phát với ptr là địa chỉ của bộ nhớ đã cấp phát và size là kích thước muốn cấp phát lại cho vùng nhớ đó.   

Ví dụ:cấp phát bộ nhớ cho 2 con trỏ a và b

int *a, *b;  
a = (int *)realloc(0, sizeof(int *));   
b = (int *)realloc(0, sizeof(int *));   

##*4. Hàm free:*    


void free ( void * ptr );   

Dùng để giải phóng vùng nhớ đã cấp phát.   

ví dụ:  
int *a = (int*)malloc(512);   
free(a);   
   
#III.BỘ NHỚ HEAP VÀ CƠ CHẾ TẠO BIẾN ÐỘNG:
- Bộ nhớ HEAP: Các biến động do malloc tạo ra được C xếp vào một vùng ô nhớ tự do theo kiểu xếp chồng và được gọi là HEAP ( bộ nhơ cấp phát động)    





