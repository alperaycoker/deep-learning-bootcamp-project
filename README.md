# Akbank Derin Öğrenme Bootcamp Projesi: Görüntü Sınıflandırma

Bu proje, Akbank Derin Öğrenme Bootcamp'i kapsamında, Keras ve Transfer Learning kullanılarak "Intel Image Classification" veri setindeki doğal sahnelerin sınıflandırılması amacıyla geliştirilmiştir.

## Projenin Amacı

Projenin temel amacı, evrişimli sinir ağları (CNN) kullanarak verilen bir görüntünün 'orman', 'deniz', 'dağ', 'sokak', 'bina' veya 'buzul' sınıflarından hangisine ait olduğunu yüksek bir başarı oranıyla tahmin etmektir. Projede başarı metriği olarak, sınıflar arası dengesizliğe daha dayanıklı olan **ağırlıklı F1-Skoru** hedeflenmiştir.

## Veri Seti

Projede, Kaggle üzerinde bulunan "Intel Image Classification" veri seti kullanılmıştır. Bu veri seti, 6 farklı sınıfa ait yaklaşık 14.000 eğitim ve 3.000 test görüntüsü içermektedir.

## Kullanılan Teknolojiler
- Python
- TensorFlow / Keras
- Scikit-learn
- Numpy
- Pandas
- Matplotlib / Seaborn
- Jupyter Notebook (Kaggle)

## Model Geliştirme Süreci ve Deneyler

En iyi modele ulaşmak için izlenen adımlar şunlardır:

1.  **Baseline Model:** İlk olarak sıfırdan özel bir CNN modeli kurulmuş ve **0.85 F1-skoru** ile bir temel performans belirlenmiştir.
2.  **Hiperparametre Optimizasyonu:** Bu skoru artırmak için epoch sayısını artırma, dropout oranını değiştirme ve modeli derinleştirme gibi deneyler yapılmıştır. Ancak bu deneylerin, aşırı öğrenmeye (overfitting) yol açarak skoru düşürdüğü gözlemlenmiştir.
3.  **En Başarılı Yaklaşım: Transfer Learning:** Manuel optimizasyonun sınırları görüldüğünde, VGG16 mimarisi kullanılarak Transfer Learning tekniğine geçilmiştir. Bu yöntem, projedeki en yüksek başarıyı sağlamıştır.

## Sonuçlar

Transfer Learning ile eğitilen final modeli, test verisi üzerinde **%89 doğruluk** ve **0.89 ağırlıklı F1-skoruna** ulaşmıştır. Bu, projenin ana hedefine başarıyla ulaşıldığını göstermektedir.

Aşağıda modelin detaylı sınıflandırma raporu yer almaktadır:

```
Final Model - Sınıflandırma Raporu:

              precision    recall  f1-score   support

   buildings       0.91      0.89      0.90       437
      forest       0.99      0.97      0.98       474
     glacier       0.80      0.86      0.83       553
    mountain       0.83      0.78      0.81       525
         sea       0.91      0.91      0.91       510
      street       0.90      0.92      0.91       501

    accuracy                           0.89      3000
   macro avg       0.89      0.89      0.89      3000
weighted avg       0.89      0.89      0.89      3000

```

**Hata Matrisi (Confusion Matrix):**


<img width="649" height="547" alt="image" src="https://github.com/user-attachments/assets/a77e6dee-42a0-4761-a9f7-94f25dbd2148" />



## Kaggle Notebook

Projenin tüm kodları, analizleri ve teknik detayları için aşağıdaki Kaggle Notebook linkini ziyaret edebilirsiniz:

**https://www.kaggle.com/code/alperayc/akbankbootcamp-alperaycoker*
