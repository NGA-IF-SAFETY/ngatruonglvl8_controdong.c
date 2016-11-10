#**I.CÁC KHÁI NIỆM**      

##*1.Một biến động*    
-  Là các biến được tạo ra lúc chạy chương trình, tùy theo nhu cầu, hoàn toàn không được xác định từ trước    
-  Các biến động đều không có tên     

##*2.Cách tạo biến động và truy cập đến biến động*   

-  Việc tạo ra biến động và xóa nó đi (để thu hồi lại bộ nhớ) được thực hiện nhờ các hàm malloc(), free(), calloc(), relloc() đã có sẵn trong stdlib.h   
-  Việc truy hồi biến động được thực hiện nhờ các biến con trỏ  

#**II.CẤP PHÁT VÀ GIẢI PHÓNG BỘ NHỚ**    

##*1. Trước hết là hàm malloc:*    
 
void * malloc ( size_t size );    

Hàm này dùng để cấp phát bộ nhớ động với kích thước size.   

Ví dụ:   
a=(int)malloc(sizeof(int));     

##*2. Hàm calloc:*   

void * calloc ( size_t num, size_t size );    

Hàm này dùng để cấp phát bộ nhớ động cho một mảng với size_t num là số phần tử của mảng.    

##*3. Hàm realloc:*   

void * realloc ( void * ptr, size_t size );    

Dùng để thay đổi kích thước bộ nhớ đã cấp phát với ptr là địa chỉ của bộ nhớ đã cấp phát và size là kích thước muốn cấp phát lại cho vùng nhớ đó.

##*4. Hàm free:*    


void free ( void * ptr );   

Dùng để giải phóng vùng nhớ đã cấp phát.   
