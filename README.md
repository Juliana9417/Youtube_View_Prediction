
#  **Airline Customer Value Analysis Case** 
---
## 📂 **Stage 0 : Problem Statement**
The company aims to understand the factors influencing high view counts on their content. By identifying the features that contribute to a large audience, they can develop more effective content strategies. The goal of this analysis is to maximize the impact of their content in reaching a broader target audience. Ultimately, the company hopes to increase engagement and achieve better business objectives through a more targeted and data-driven approach to content creation. 

<br>

---

## 📂 **Stage 1 : Exploratory Data Analysis**
### Dataset
<p align="center">
  Tabel 1 – Informasi Data <br>
</p>

<p align="center">
  
![data yutub](https://github.com/user-attachments/assets/bbbb17b3-1481-4e5a-b7ba-4b2c7b9e8c34)

</p>

### Descriptive Statistics

<p align="center">
  Tabel 2  – Data Deskriptif Numerikal
</p>

<p align="center">
  
![data numerikal](https://github.com/user-attachments/assets/31152b39-f092-42d2-8b7f-01be94ef41d7)

</p>

<br>

<p align="center">
   Tabel 3  – Data Deskriptive Kategori
</p> 

<p align="center">
  
![data kategori](https://github.com/user-attachments/assets/8b6867fc-f7dd-44e9-99f0-47be50b2607a)

</p>

<br>

### Insight Data Deskriptif : <br>

- Distribusi data pada Fitur views, likes, dislikes, comment_count, desc_len, and len_title terlihat skewed. <br>
- Pada Fitur comment_disabled, rating_disabled, dan video_error_or_removed, terdapat dominasi nilai False yang sangat besar. <br>
<br>

<br>

### Univariate Analisis : 
  
<p align="center">
  
![boxplot](https://github.com/user-attachments/assets/07c08555-b69c-4ff1-908b-5d83b8ef782d)

  Gambar 1 – Boxplot Numerikal 
</p>

<br>
### Insight: <br>

- Fitur views, likes, dislikes, dan comment_count memiliki banyak outliers dengan jarak yang sangat ekstrim. <br>
- Fitur no_tags, dan desc_len juga memiliki outliers namun jaraknya tidak se ekstrim ke empat kolom yang telah disebutkan sebelumnya. <br>
- Fitur len_title tidak memiliki outliers, mungkin ini disebabkan oleh adanya default batas 'jumlah kata' penulisan judul video. <br>
<br>

<p align="center">
  
![displot](https://github.com/user-attachments/assets/db9c6174-d7a1-4c64-8fc9-0c0dae0f647b)

  Gambar 2 – Displot Numerikal 
</p>
<br>
### Insight : 

- Fitur len_title memiliki distribusi skew negatif sedangkan fitur lainya memiliki distribusi skew positif. <br>
- Fitur views, likes, dislikes, dan comment_count berkonsentrasi di sekitar 0 dengan ekor kanan yang panjang, artinya distribusi mencakup nilai ekstrem yang secara signifikan lebih tinggi daripada sisa data. <br>
<br>

### Bivariate Analisis : 

</p>
<p align="center">
  
![bivariate](https://github.com/user-attachments/assets/37e0ef44-ecbe-4adf-831c-3addbd7b46dc)

  Gambar 3 - Bivariate Analisis
</p>

### Insights: <br>

- Di 'category_id', id 24 memiliki jumlah views tertinggi dan id 10, id 1 dan id 28 memiliki total views yang relatif lebih tinggi dari yang lainya. <br>
- Pada fitur 'comments_disabled', 'ratings_disabled', dan 'video_error_or_removed', nilai False memiliki jumlah views yang lebih besar dibanding nilai True (general domain: video akan mendapat views lebih banyak jika kedua variabel tersebut False). Ini mengindikasikan bahwa ketiga fitur tersebut bukan oredictor jumlah views yang baik. <br>
<br>

### Multivariate Analisis : 
<p align="center">
  
![multivariate](https://github.com/user-attachments/assets/da6be4d1-e900-41b4-980c-9a8995455766)

<p>
  Gambar 4 - Multivariate Numerikal
</p>
<br>
### Insight : <br>

- korelasi koefisien  'views'-'likes' sebesar 0,85 yang artinya terdapat hubungan linear yang sangat kuat antara keduanya. Koefisien Korelasi 'views'-'dislikes' sebesar 0,54 dan 'views'-'comment_count' sebesar 0,67 yang menunjukan bahwa dislike dan comment_count juga mempunyai hubungan linear yang signifikan dengan target. Kesimpulanya, fitur likes, dislikes dan comment_count kemungkinan besar menjadi prediktor yang baik untuk target 'views'. <br>
- Terdapat korelasi linier yang juga sangat tinggi satu sama lain pada fitur 'likes', 'dislikes', dan 'comment_view'. <br>
<br>

## 📂 **Stage 2 : Data Pre-Processing**
<br>
1. Duplicate & Missing Value
   
  <p align="center">
    
  ![duplita null](https://github.com/user-attachments/assets/c97095d8-04f8-43b0-88d6-85c4b6c93137)

   </p>
   <p align="center">
     Gambar 5 - Handling duplicate and missing values <br>
   </p>
<br>
<br>
2. Feature Engineering
       
    <p align="center">
    
  ![jam publish](https://github.com/user-attachments/assets/1a791685-6c9d-4a86-980b-2f35e3c081e8)

   </p>
   <p align="center">
     Gambar 6 - Publish Time <br>
   </p>
<br>
### Insight : <br>
- Grafik diatas menunjukkan waktu prime time dalam 24 jam berada di jam 12.00 - 13.00 <br>
<br>

<p align="center">
  
![day publish](https://github.com/user-attachments/assets/be8ccd82-1184-4649-8737-019114e46287)

   </p>
   <p align="center">
     Gambar 7 - Publish Time <br>
   </p>
<br>
### Insight : <br>
- Hasil grafik diatas menunjukkan bahwa dalam satu minggu views terbanyak terdapat pada hari Rabu <br>
<br>

## 📂 **Stage 3 : Modelling**

### **Random Forest**

  <p> 
  <p align="center">
  
  ![hyperparameter tuning rf](https://github.com/user-attachments/assets/e1c19552-bd3a-4ced-a1ce-65a4175b5db4)

   </p>
   <p align="center">
     Gambar 8 - Hyperparameter Tunning Random Forest with RandomSearchCV <br>
   </p>
   <br>
### Insight : <br>
- Dari hasil Tunning menggunakan Random Search telah meningkatkan performa model Random Forest, terutama dalam hal RMSE (test) dan R² (test), yang menunjukkan peningkatan dalam kemampuan model memprediksi data uji dan menjelaskan variasi dalam data uji. <br>
<br>

### **Feature Importance**

  <p> 
  <p align="center">
  
  ![important](https://github.com/user-attachments/assets/0d757870-158d-4ba3-8009-f2594782068a)

   </p>
   <p align="center">
     Gambar 9 - Feature Importances <br>
   </p>
   <br>

---

### **Business Insight and Recomendations:**

### Business Insight:

1. *Optimal Publishing Time*: Analisis menunjukkan bahwa pemilihan waktu yang tepat untuk mempublikasikan konten memiliki dampak signifikan terhadap jumlah views. Data menunjukkan bahwa puncak jumlah views terjadi pada hari Rabu, diikuti oleh Selasa dan Senin. Waktu yang paling efektif untuk mempublikasikan konten adalah antara pukul 12:00 hingga 13:00. Pada jam ini, banyak orang cenderung aktif di platform YouTube pada waktu istirahat ditengah menjalani rutinitas harian mereka. Rabu, sering menjadi puncak karena merupakan pertengahan minggu ketika orang merasa lelah dengan pekerjaan sehari-hari, sedangkan Selasa dan Senin menunjukkan minat tinggi karena orang mencari hiburan setelah akhir pekan.

2. *Peran Engagement*: Interaksi seperti likes, dislikes, dan comments bukan hanya mencerminkan respons terhadap konten, tetapi juga mempengaruhi tingkat eksposur konten kepada orang lain. Konten dengan engagement yang tinggi memiliki peluang lebih besar untuk menarik perhatian dan menjadi viral.

3. *Konsistensi dan Prediktabilitas*: Fitur-fitur yang dipilih untuk dianalisis didasarkan pada konsistensi hubungannya dengan views. Perusahaan dapat memilih fitur-fitur ini untuk dipertimbangkan dalam mengembangkan strategi konten yang lebih efektif dan terarah.

4. *Optimasi Keputusan Berbasis Data*: Dengan memanfaatkan data mengenai waktu publikasi dan interaksi, perusahaan dapat membuat keputusan yang lebih baik dalam merencanakan dan melaksanakan kampanye pemasaran. Hal ini meningkatkan efisiensi dan efektivitas upaya pemasaran konten secara keseluruhan.

### Rekomendasi:

- *Peningkatan Engagement*: Fokus pada meningkatkan engagement melalui interaksi yang lebih aktif dari audiens, seperti meningkatkan panggilan aksi (call-to-action, CTA) dalam konten. CTA dapat menjadi kunci untuk mendorong interaksi dan keterlibatan audiens lebih lanjut dengan video konten. Pembuat konten dapat mengajak audiens untuk melakukan berbagai tindakan seperti subscribe untuk mendukung kanal Anda, like untuk meningkatkan visibilitas video, comment untuk memicu diskusi, share untuk memperluas jangkauan, atau mengklik link di deskripsi video untuk informasi tambahan atau tindakan lebih lanjut. CTA yang tepat tidak hanya meningkatkan interaksi dan engagement, tetapi juga membantu dalam membangun komunitas yang loyal dan meningkatkan keberhasilan konten di YouTube.

- *Manfaatkan Prime Time Waktu Publikasi*: Pilih untuk mempublikasikan konten pada prime time antara pukul 12:00 hingga 13:00, waktu di mana lebih banyak orang menonton konten YouTube. Hari Rabu, Selasa, dan Senin terbukti menjadi hari-hari dengan jumlah views tertinggi, yang menunjukkan minat tinggi dari audiens untuk mengonsumsi konten pada waktu-waktu tersebut. Hal ini dapat meningkatkan visibilitas dan dampak konten Anda secara signifikan.

- *Optimalkan Promosi Konten: *Optimalkan Promosi Konten: Analisis juga menunjukkan bahwa video yang trending pada hari ke 8 setelah publish adalah yang paling banyak mendapatkan penonton, diikuti oleh hari ke-7 dan ke-9. Oleh karena itu, tingkatkan promosi konten selama 9 hari pertama setelah publikasi untuk memaksimalkan jumlah penonton dan memperluas jangkauan konten Anda.

Dengan mempertimbangkan aspek-aspek ini, perusahaan dapat meningkatkan strategi konten untuk lebih efektif mencapai audiens target dan memaksimalkan dampaknya dalam mencapai tujuan bisnis.
