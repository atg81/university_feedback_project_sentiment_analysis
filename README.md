# Turkish University Sentiment Analysis Model

Bu proje, üniversite geri bildirimlerinin duygu analizini gerçekleştirmek amacıyla geliştirilmiş bir makine öğrenmesi modelini içermektedir.

Model, daha sonra geliştirilen **Üniversite Geri Bildirim Analiz Sistemi** projesinde kullanılmak üzere eğitilmiş ve başarıyla entegre edilmiştir.

---

## Projenin Amacı

Bu çalışmanın amacı, kullanıcıların sisteme gönderdikleri geri bildirimlerin duygu durumunu otomatik olarak analiz edebilecek bir makine öğrenmesi modeli geliştirmektir.

Model sayesinde kullanıcı yorumları;

- 😊 Olumlu (Positive)
- 😟 Olumsuz (Negative)

olarak otomatik sınıflandırılmaktadır.

---

## Kullanılan Teknolojiler

- Python
- Pandas
- NumPy
- Scikit-learn
- Joblib
- Jupyter Notebook

---

## Veri Ön İşleme

Model eğitilmeden önce metinler çeşitli ön işleme adımlarından geçirilmiştir.

Uygulanan işlemler:

- Küçük harfe dönüştürme
- URL temizleme
- @mention temizleme
- Emoji kaldırma
- Noktalama işaretlerinin kaldırılması
- Sayıların kaldırılması
- Gereksiz boşlukların temizlenmesi

Bu işlemler sayesinde modelin daha doğru öğrenmesi hedeflenmiştir.

---

## Özellik Çıkarımı

Metinler sayısal verilere dönüştürülmeden makine öğrenmesi algoritmaları tarafından işlenemeyeceği için TF-IDF (Term Frequency - Inverse Document Frequency) yöntemi kullanılmıştır.

TF-IDF ile her yorum sayısal özellik vektörlerine dönüştürülerek model eğitimine hazır hale getirilmiştir.

---

## Karşılaştırılan Modeller

Bu çalışma kapsamında farklı makine öğrenmesi algoritmaları karşılaştırılmıştır.

- Logistic Regression
- Linear Support Vector Machine (Linear SVM)
- Multinomial Naive Bayes

Performans karşılaştırmaları sonucunda en başarılı model seçilmiştir.

---

## Model Performansı

| Model | Accuracy |
|--------|----------|
| Linear SVM | **90.06%** |
| Logistic Regression | 88.11% |
| Multinomial Naive Bayes | 83.39% |

Yapılan değerlendirmeler sonucunda yaklaşık **%90 doğruluk oranı** ile en başarılı sonucu veren **Linear SVM** modeli tercih edilmiştir.

---

## Modelin Kaydedilmesi

Eğitim tamamlandıktan sonra model tekrar eğitilmesine gerek kalmaması amacıyla Joblib kullanılarak kaydedilmiştir.

Üretilen dosyalar:

- sentiment_model.pkl
- tfidf_vectorizer.pkl

Bu dosyalar daha sonra FastAPI tabanlı projeye entegre edilmiştir.

---

## Test Süreci

Eğitilen model;

- Gerçek kullanıcı yorumları
- Örnek üniversite geri bildirimleri
- Pozitif ve negatif senaryolar

üzerinde test edilmiştir.

Modelin tahminleri Confusion Matrix ve Accuracy, Precision, Recall ve F1-Score metrikleri ile değerlendirilmiştir.

---

## Proje ile İlişkisi

Bu repo yalnızca makine öğrenmesi modelinin geliştirilme sürecini içermektedir.

Modelin kullanıldığı tam uygulama aşağıdaki projede bulunmaktadır:

👉 https://github.com/atg81/university_feed_back_project

---

## Lisans

Bu proje eğitim ve akademik amaçlarla geliştirilmiştir.