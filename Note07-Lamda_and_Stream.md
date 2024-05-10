# NOTE 07: LAMDAS AND STREAMS
Funtional Interface, lambdas, stream xuất hiện ở Java 8 và được ưa dùng nhất.

## Item 42: Ưu tiên sử dụng lamdas thay cho anonymous class
function object
funtion type
trong quá khứ Function Object là những instance của interface hoặc abtract class mà chỉ có duy nhất một hàm static.

sau này chúng được gọi là các funtional interface và Java cho phép tạo các instance của chúng bằng các lamda expression hay ngắn gọn hơn là lambda

## Item 43: Ưu tiên sử dụng method referrence hơn lamda
Ưu điểm của lambda so với anonymous class là chúng ngắn gọn hơn. Java còn cung cấp một function objec thậm chí còn ngắn gọn hơn, đó là method reference (phương thức tham chiếu).  


## Item 45: Sử dụng Stream một cách thận trọng


## Item 47: Sử dụng Collection to Stream như là một kiểu trả về
Trước Java 8, khi trả về một tập hợp, ta dễ dàng quyết định kiểu trả về nào mà ta muốn, ví dụ: List, Set, Array... 

Sau Java 8, khi stream được thêm vào làm phức tạp hơn quyết định chọn kiểu tra về một tập hợp



## Item 48: Cẩn thận khi sử dụng stream song song
Java là một ngôn ngữ hỗ trợ lập trình song song rất tốt, ví dụ như Thread, thư viện concurrent trong Java 5, 

Trong Java 8, Stream khi xuất hiện cũng được hỗ trợ lập trình song song với hàm parallel,

Với sự hỗ trợ nhiều của Java đôi khi khiến các lập trình viên chủ quan và không tìm hiểu kỹ, vì vậy có thể mắc phải một số lỗi. Ví dụ

```java
// Stream-based program to generate the first 20 Mersenne primes
public static void main(String[] args) {
 primes().map(p -> TWO.pow(p.intValueExact()).subtract(ONE))
 .filter(mersenne -> mersenne.isProbablePrime(50))
 .limit(20)
 .forEach(System.out::println);
}
static Stream<BigInteger> primes() {
 return Stream.iterate(TWO, BigInteger::nextProbablePrime);
}
```
Hàm tìm số nguyên tố này sẽ mất khoảng 5 giây để hoàn thành, và bây giờ bạn muốn tăng nó bằng hàm parallel. 
