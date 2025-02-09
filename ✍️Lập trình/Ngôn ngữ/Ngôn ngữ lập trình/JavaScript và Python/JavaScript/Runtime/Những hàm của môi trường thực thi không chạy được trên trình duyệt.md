---
share: true
created: 2023-10-30T14:29
updated: 2024-08-24T12:40
---
VD, `Deno.readTextFile()` là một hàm của môi trường thực thi. Hàm này sẽ không chạy được trên trình duyệt. Bởi vì trình duyệt thì không biết gì về Deno, Node, v.v. Muốn dùng các hàm do các môi trường thực thi này cung cấp thì phải chạy trên server chứ không chạy trên client được. Cũng vì lý do này mà [[Các hàm được môi trường thực thi cung cấp không hoạt động được ở island]], vì [[Route là code viết cho server. Island là code viết cho client|island là code viết cho client]].

Hệ quả của việc này là bạn [[Nên tách bạch file util cho client và util cho server]], vì nếu không thì sẽ dễ dùng hàm cho server khi viết island. Chỉ dùng không lẫn hàm là không đủ, mà còn phải là không lẫn file. [[Khi import một hàm thì cả file chứa hàm đó sẽ được chạy. Các import của file đó cũng sẽ chạy theo, dù là để import vào một hàm khác mình không import]]. 

Xem thêm:: 
- [[JS vốn được sinh ra để chạy trên trình duyệt và không được dùng để làm việc với lượng code lớn]]. 
- [[Code giống như các nốt nhạc, engine giống như nhạc công, còn runtime giống như nhạc cụ|Môi trường thực thi đối với code cũng giống như nhạc cụ đối với nốt nhạc]]