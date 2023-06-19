# Capstone_Project_Modul_3 - TELCO CUSTOMER CHURN
---
# Business Problem Understanding

1. Latar Belakang:

Dalam industri telekomunikasi, fenomena churn pelanggan (churn rate) merupakan masalah yang umum terjadi. Churn pelanggan merujuk pada pelanggan yang memutuskan untuk berhenti menggunakan layanan sebuah perusahaan telekomunikasi dan beralih ke pesaing atau bahkan tidak menggunakan layanan telekomunikasi sama sekali. Tingkat churn yang tinggi dapat memiliki dampak negatif pada bisnis perusahaan, seperti pendapatan yang menurun, penurunan pangsa pasar, dan biaya akuisisi pelanggan yang meningkat. Dengan kondisi tersebut perusahaan ingin mengembangkan model prediksi churn customer untuk membantu mengidentifikasi customer yang berpotensi churn di masa depan. Dengan memiliki model prediksi yang akurat, perusahaan dapat mengambil tindakan pencegahan yang tepat untuk mempertahankan customer yang bernilai dan mengurangi tingkat churn dengan memahami faktor-faktor yang mempengaruhi churn dan mengembangkan strategi retensi yang efektif. Selain mempertahankan customer yang terprediksi akan churn juga diharapkan dari model dapat membedakan untuk target yang sebetulnya tidak perlu dilakukan penanganan karena aktualnya tidak ada indikasi untuk berhenti berlangganan sehingga meminimalkan juga biaya operasional yang keluar tanpa arti. Oleh karenanya akan dicari model dan metriks terbaik untuk mengatasi trade-off dari permaslahan yang terjadi.

2. Tujuan:

Tujuan utama dari analisis ini adalah untuk mengembangkan model prediksi churn customer yang dapat mengklasifikasikan customer sebagai churn atau tidak churn berdasarkan fitur-fitur yang ada. Model ini akan membantu perusahaan mengidentifikasi customer dengan risiko churn tinggi sehingga dapat dilakukan intervensi atau strategi retensi yang sesuai dan juga memaksimalkan prediksi yang tidak memiliki indikasi churn sehingga biaya operasional untuk penanganan dapat tersalurkan secara akurat untuk customer yang aktualnya memang churn.


3. Problem Statement:
- Bagaimana membangun model machine learning yang dapat mengklasifikasikan churn customer perusahaan telco sehingga bisa digunakan oleh perusahaan untuk mengoptimalkan strategi retensi dengan biaya operasional yang minimum?



4. Manfaat Bisnis:
- Dengan memiliki model prediksi churn yang akurat, perusahaan dapat mengidentifikasi customer dengan risiko churn tinggi dan mengambil tindakan pencegahan yang tepat untuk mempertahankan mereka.
- Mengurangi churn customer secara efektif dapat meningkatkan pendapatan perusahaan dan mengurangi biaya akuisisi customer baru. 
- Model prediksi churn yang baik juga dapat membantu perusahaan mengoptimalkan alokasi sumber daya dan strategi retensi, dengan fokus pada customer yang memiliki dampak bisnis yang signifikan.
- Melalui penggunaan model prediksi churn, perusahaan dapat mengembangkan strategi pemasaran yang lebih personal, meningkatkan kepuasan customer, dan memperkuat hubungan jangka panjang dengan customer.

5. Evaluation Metrics:

Metrics evaluasi yang digunakan pada pemodelan kali ini akan dilihat dari konteks kasus nya terlebih dahulu. Dalam kasus Telco Customer Churn, nilai 1 direpresentasikan untuk pelanggan yang churn dan nilai 0 direpresentasikan untuk customer yang tidak churn. Untuk false positive dan false negative yang ada pada kasus ini dapat dijelaskan sebagai berikut:

- False Positive:

    False positive terjadi ketika model memprediksi bahwa pelanggan churn (nilai prediksi 1), padahal sebenarnya pelanggan tersebut churn (nilai aktual 1). Dalam kasus ini, model secara keliru mengklasifikasikan pelanggan sebagai tidak churn ketika sebenarnya mereka akan berhenti berlangganan. Dampaknya adalah perusahaan mungkin mengalokasikan sumber daya yang tidak perlu untuk mempertahankan pelanggan yang sebenarnya akan churn, yang dapat mengakibatkan biaya yang tinggi.

- False Negative:

    False negative terjadi ketika model memprediksi bahwa pelanggan akan tidak churn (nilai prediksi 0), tetapi sebenarnya pelanggan tersebut tidak churn (nilai aktual 0). Dalam kasus ini, model gagal mengidentifikasi dengan tepat pelanggan yang sebenarnya tidak akan berhenti berlangganan. Dampaknya adalah, perusahaan dapat kehilangan pelanggan yang berharga karena tidak mengambil tindakan yang diperlukan untuk mempertahankan mereka, yang dapat mengakibatkan kerugian finansia.

Pada kasus ini, model diharapkan dapat memprediksi customer yang terindikasi churn dengan baik sehingga perlu diminimalkan untuk terjadi false negative dimana perusahaan akan abai membuat customer churn tanpa ada perlakuan retensi, untuk permasalahan ini metrics recall lebih sesuai sebagai acuan tolak ukur model. Disisi lain, perusahaan juga perlu memperhatikan dari sisi biaya dimana apabila false positive tinggi maka perusahaan berpotensi mengalokasikan biaya retensi kepada target yang salah sehingga memakan biaya tinggi yang tidak tepat sasaran. Untuk permasalahan tersebut, metrics F2 lebih sesuai untuk memprioritaskan recall namun tetap memperhatikan presisi model. Dari beberapa pertimbangan permasalahan yang telah dijelaskan, metrics F2 dan Recall akan dikaji dan dievaluasi mana yang dapat membuat objective tercapai namun lebih menguntukan bagi perusahaan.

---
Kesimpulan

Dalam projek kali ini telah dikembangkan model prediksi churn customer yang dapat mengklasifikasikan customer sebagai churn atau tidak churn berdasarkan fitur-fitur yang ada. Model ini membantu perusahaan mengidentifikasi customer dengan risiko churn tinggi sehingga dapat dilakukan intervensi atau strategi retensi yang sesuai dan juga memaksimalkan prediksi yang tidak memiliki indikasi churn sehingga biaya operasional untuk penanganan dapat tersalurkan secara akurat untuk customer yang aktualnya memang churn. Algoritma model terbaik yang didapat setelah dilakukan beberapa proses untuk memprediksi dataset adalah Catboost dengan teknik resampling Random Over Sampling. Evaluasi metrics yang digunakan untuk mengevaluasi kinerja model adalah F2 dimana perusahaan fokus dalam meminimalkan kejadian customer churn yang pergi tanpa perlakuan retensi namun tetap mempertimbangkan presisi model dimana kerugian bisa terjadi apabila customer yang tidak terindikasi churn tapi mendapatkan perlakuan retensi dimana biaya akan keluar sia-sia. Hasil score F2 dari model prediksi adalah 76%, dimana ini model bisa terbilang cukup baik dalam membantu perusahaan mengklasifikasikan customer churn dan tidak. Namun begitu, sebaik apapun model prediksi ini tidak bisa dijadikan sebagai satu-satunya alat tunggal dalam pengambilan keputusan bisnis, penting untuk menggabungkan pengetahuan bisnis, pengalaman, dan pertimbangan manusia untuk memahami dan menginterpretasikan hasil model dengan benar, serta mengambil keputusan yang berimbang dan sesuai dengan konteks bisnis yang lebih baik.



