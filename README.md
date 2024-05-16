
## Reflection on Hello Minikube  

**1. Compare the application logs before and after you exposed it as a Service.**
  Setelah layanan diekspos, akan ada perbedaan yang terlihat pada log aplikasi. Hal ini karena layanan yang diekspos mulai menerima permintaan, sehingga log akan mencatat setiap permintaan yang masuk. Sebagai contoh, jika kita membuka layanan hello-node beberapa kali, log akan mencatat setiap aktivitas tersebut.
![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/7f06942c-287d-4c36-b4c8-ea787522780c)


**2. Notice that there are two versions of `kubectl get` invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to `kube-system`.**
  Perbedaan antara kedua perintah `kubectl get` adalah penggunaan opsi `-n`. Perintah pertama tanpa opsi `-n` akan menampilkan daftar sumber daya di namespace default. Sementara perintah kedua menggunakan opsi `-n kube-system`, yang akan menampilkan daftar sumber daya di namespace kube-system. Opsi `-n` berfungsi untuk menentukan namespace spesifik yang ingin kita lihat. Hal ini penting jika terdapat sumber daya dengan nama yang sama di beberapa namespace berbeda. Dengan menggunakan `-n`, kita dapat memfokuskan perintah get pada namespace yang ditentukan.

## Reflection on Rolling Update & Kubernetes Manifest File

**1. What is the difference between Rolling  Update and Recreate Deployment Strategy?**

**2. Try deploying the Spring Petclinic REST using Recreate deployment strategy and document your  attempt.**

- recreate pada springboot-petclinic-rest yang telah di scaled
  
  ![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/cb66133d-e1db-4cae-a777-754aeb776fe5)

- Memanfaatkan replikaset yang akan menggantikan pod yang dihapus dengan templatenya dan diubah ke versi 3.2.1
  
  ![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/b66b8fe4-a628-4724-ae79-119ffa33486c)

- Mengecheck keberhasilan perubahan
  
  ![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/547e839e-a170-4f5a-a381-49beefa6c218)
  ![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/f4ed8976-8be9-444e-acd9-14975235b3ab)

- delete pod
  
  ![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/973173a7-f952-448c-b178-1e76cc9f8621)
- Buat pod baru untuk mengganti pod sebelumnya dan output dari program pada saat di run
  ![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/d8862d68-9a0f-42ee-a4d7-99be67d0253c)
  ![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/74db9411-9257-4b52-a4ab-29970ca3057a)



**3. Prepare different manifest files for executing Recreate deployment strategy.**

```yaml
  selector:
      matchLabels:
      app: spring-petclinic-rest
   strategy:
      type: Recreate
```

![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/1edc8a3b-fcb5-4872-9073-aceda57aa3a4)
![image](https://github.com/shirinzarqaa/module-11-deployment/assets/110030938/9d26c3e4-6404-4e07-9b2c-b6921c29f34f)


**4. What do you think are the benefits of using Kubernetes manifest files?**




    
