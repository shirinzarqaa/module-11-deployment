
## Reflection on Hello Minikube  
1. Compare the application logs before and after you exposed it as a Service.  
  Setelah layanan diekspos, akan ada perbedaan yang terlihat pada log aplikasi. Hal ini karena layanan yang diekspos mulai menerima permintaan, sehingga log akan mencatat setiap permintaan yang masuk. Sebagai contoh, jika kita membuka layanan hello-node beberapa kali, log akan mencatat setiap aktivitas tersebut.
![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/7f06942c-287d-4c36-b4c8-ea787522780c)


2. Notice that there are two versions of `kubectl get` invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to `kube-system`.
  Perbedaan antara kedua perintah `kubectl get` adalah penggunaan opsi `-n`. Perintah pertama tanpa opsi `-n` akan menampilkan daftar sumber daya di namespace default. Sementara perintah kedua menggunakan opsi `-n kube-system`, yang akan menampilkan daftar sumber daya di namespace kube-system. Opsi `-n` berfungsi untuk menentukan namespace spesifik yang ingin kita lihat. Hal ini penting jika terdapat sumber daya dengan nama yang sama di beberapa namespace berbeda. Dengan menggunakan `-n`, kita dapat memfokuskan perintah get pada namespace yang ditentukan.
    
