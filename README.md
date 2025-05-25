# Akbank Machine Learning Bootcamp
Akbank Makine Öğrenmesine Giriş Bootcamp

# 🎀

## Report

## 📄 Medical Appointment No-Shows - Proje Raporu

### 1. Proje Tanımı

Bu çalışmada, **bir sağlık randevuları veri seti** kullanılarak, bireylerin randevularına katılıp katılmayacaklarını tahmin
etmeye yönelik bir sınıflandırma modeli geliştirilmiştir. Proje, gözetimli öğrenme yöntemlerini temel almakta ve
hedef değişken olarak "No-show" sütunu kullanılmıştır. Veri seti, 110.527 tıbbi randevuya ait 14 farklı özelliği
içermekte olup, hasta kimliği, randevu kimliği, cinsiyet, randevu tarihi, kayıt tarihi, yaş, mahalle, sosyal yardım
durumu Scholarship), hipertansiyon, diyabet, alkolizm, engellilik Handcap), SMS alıp almadığı ve randevuya
katılıp katılmadığı No-show) gibi değişkenleri barındırmaktadır. Bu projenin amacı, randevuya gelmeme durumunu
tahmin etmektir.

### 2. Veri Seti

Bu çalışmada, Kaggle platformunda bulunan "Medical Appointment No Shows" veri seti kullanılmıştır. 110.
gözlem ve 14 özellik içeren bu veri seti, hastaların randevularına katılıp katılmadıklarını No-show) tahmin etmeye
yönelik bir sınıflandırma modeli geliştirmek için kullanılmıştır.✨

**Kaynak**  Kaggle  Medical Appointment No Shows

**Dosya adı** : KaggleV2.May-2016.csv

**Gözlem sayısı**  110527

**Özellik sayısı**  14

### Önemli Değişkenler:

```
Sütun Adı Açıklama
Gender Hastanın cinsiyeti
Age Yaş
Neighbourhood Hastanın yaşadığı mahalle
Scholarship Sosyal yardım alıp almadığı 0/1
Hipertension Yüksek tansiyon durumu
Diabetes Diyabet durumu
Alcoholism Alkol bağımlılığı
SMS_received Hatırlatma mesajı alıp almadığı
No-show Randevuya gelip gelmedi Target)
```
### 3. Veri Ön İşleme

Eksik veri bulunmadı.
Yaş sütununda negatif değer olmadığı teyit edildi.
Kategorik değişkenler label encoding veya one-hot encoding ile dönüştürüldü.
Tarihsel değişkenler (ScheduledDay, AppointmentDay) kullanıldıktan sonra gün-sayısı farkı üretildi.
Hedef değişken "No-show" sütunu "Yes"  1 v e "No"  0 olarak dönüştürüldü.

### 4. Keşifsel Veri Analizi (EDA)


Yaş dağılımı incelendi.
Sosyal yardım alan bireylerin randevuya gitmeme oranı düşük bulundu.
SMS hatırlatma alanların, almayanlara kıyasla daha yüksek katılım oranına sahip olduğu görüldü.
Mahalle bazlı no-show oranları incelendi.


```
Özellikler ile hedef değişken arasındaki korelasyon incelendi.
```
### 5. Modelleme

Bu projede, hastaların randevularına gelmeme durumunu (
No-show) tahmin etmek amacıyla çeşitli sınıflandırma algoritmaları kullanılmıştır. Model performansını^
değerlendirmek için Accuracy, Precision, Recall, F1-score metrikleri ve Confusion Matrix kullanılmıştır.

### Kullanılan Algoritmalar:

```
Random Forest: Birçok karar ağacının birleşimiyle tahmin yapan güçlü bir topluluk öğrenme modelidir.
Gradient Boosting: Zayıf öğrenicileri ardışık olarak güçlendirerek daha doğru tahminler yapan bir topluluk
öğrenme algoritmasıdır.
Logistic Regression: Girdilere dayalı olasılık hesaplayarak ikili sınıflandırma yapan basit ve doğrusal bir
modeldir.
Decision Tree: Veriyi karar kurallarıyla dallandırarak tahminler yapan ağaç benzeri yorumlanabilir bir modeldir.
KNN KNe arest Neighbors): Yeni bir veri noktasını, en yakın 'k' komşusunun çoğunluk sınıfına göre
sınıflandıran basit bir algoritmadır.
```
### Performans Metrikleri:

```
Accuracy Doğruluk): Modelin tüm tahminlerinin ne kadarının doğru olduğunu gösteren genel bir başarı
oranıdır.
Precision Kesinlik): Modelin pozitif olarak tahmin ettiklerinin ne kadarının gerçekten pozitif olduğunu ölçer.
Recall Duyarlılık): Gerçek pozitif vakaların ne kadarının model tarafından doğru bir şekilde yakalandığını
gösterir.
F1-score: Precision ve Recall'ın dengeli bir ortalaması olup, özellikle dengesiz veri setlerinde daha güvenilir bir
performans ölçütüdür.
Confusion Matrix Karmaşıklık Matrisi): Modelin doğru ve yanlış tahminlerini sınıf bazında detaylandıran bir
tablodur.
```
### Model Karşılaştırma Sonuçları (SMOTE Öncesi)

Dengesiz veri seti üzerinde yapılan ilk modelleme denemelerinde elde edilen F1Score değerleri aşağıdaki tabloda
sunulmuştur:

```
Model Adı F1Score Standart Sapma (+/-)
Logistic Regression 0.0025 0.
Random Forest 0.2631 0.
Gradient Boosting 0.0083 0.
Decision Tree 0.3243 0.
KNN 0.2522 0.
```
**SMOTE öncesi en iyi model:** Decision Tree F1Score: 0.3243

### Model Karşılaştırma Sonuçları (SMOTE Sonrası)

Veri setindeki sınıf dengesizliğini gidermek amacıyla SMOTE Synthetic Minority Over-sampling Technique)
uygulandıktan sonra modeller yeniden eğitilmiş ve değerlendirilmiştir. SMOTE sonrası elde edilen F1Score
değerleri aşağıdaki tabloda gösterilmiştir:

```
Model Adı F1Score Standart Sapma (+/-)
Logistic Regression 0.6825 0.
Random Forest 0.7770 0.
Gradient Boosting 0.7121 0.
Decision Tree 0.7587 0.
KNN 0.7430 0.
```
**SMOTE sonrası en iyi model:** Random Forest F1Score: 0.7770


### 6. Model Karşılaştırması ve Yorumlar

SMOTE sonrası **Random Forest** modeli, **0.7770 F1Score** ile en iyi performansı gösterdi. Bu modelin test seti
performansı: Doğruluk %58.53, Kesinlik %30.63, Duyarlılık %83.29, F1Score %44.78 ve AUCROC %73.06'dır.
Özellikle yüksek Duyarlılık, randevuya gelmeyen hastaların çoğunu doğru tespit ettiğini; düşük Kesinlik ise bazı
yanlış pozitif tahminler olduğunu gösterir. SMS_received, Age ve Scholarship değişkenleri, randevu katılımını tahmin
etmede önemli faktörlerdir.
**En iyi performans gösteren modelin Random Forest) test seti üzerindeki detaylı performans metrikleri
aşağıdaki gibidir:
Doğruluk Accuracy)**  0.
**Kesinlik Precision)**  0.
**Duyarlılık R ecall)**  0.
**F1Score**  0.
**AUCROC**  0.

### 7. Görselleştirme

```
Yaş Grupları vs No-Show: Hastaların yaş grubuna göre randevuya katılım ve katılmama oranlarını gösterir.
Bekleme Kategorileri vs No-Show: Randevu bekleme süresinin randevuya katılım üzerindeki etkisini inceler.
Sağlık Problemi Sayısı vs No-Show: Sağlık sorunları sayısının randevu katılımıyla ilişkisini ortaya koyar.
Hafta İçi/Sonu vs No-Show: Randevunun hafta içi veya hafta sonu olmasının katılım üzerindeki farkını gösterir.
Aylık No-Show Dağılımı: Yılın aylarına göre randevuya katılım ve katılmama eğilimlerini sergiler.
Hafta Günleri vs No-Show: Haftanın gününe göre randevu katılım oranlarının nasıl değiştiğini açıklar.
```

**Karmaşıklık Matrisi Confusion Matrix):** Bir sınıflandırma modelinin tahminlerini T ahmin Edilen Sınıf) gerçek
sonuçlarla Gerçek Sınıf) karşılaştırarak, modelin ne kadar doğru ve ne tür hatalar yaptığını gösteren bir tablodur.
Modelin performansını detaylı olarak anlamamızı sağlar.

### Sınıflandırma Raporu Özeti

```
Metrik Geldi 0 Gelmedi 1
Precision 0.93 0.
Recall 0.52 0.
F1Score 0.67 0.
Support 17642 4464
Accuracy Genel Doğruluk): 0.
Toplam Gözlem Sayısı: 22106
```

**ROC Eğrisi Ne İşe Yarar?**
Bir sınıflandırma modelinin farklı eşik değerlerindeki performansını görselleştirmek için kullanılır. Özellikle ikili
sınıflandırma problemlerinde, modelin pozitif sınıfı ne kadar iyi ayırt edebildiğini gösterir.

### 8. Sonuç ve Öneriler

Modelin "No-show" (randevuya gelmeme) tahmininde en yüksek etkiye sahip olduğu belirlenen özellikler
şunlardır:

```
Özellik Adı Önem Değeri
waiting_days 0.
age 0.
sms_received_1 0.
gender_M 0.
hipertension_1 0.
scholarship_1 0.
handcap_1 0.
alcoholism_1 0.
diabetes_1 0.
handcap_2 0.
```
Bu analizlere göre, **waiting_days (bekleme günleri)** değişkeni, hastaların randevuya katılım davranışını tahmin
etmede açık ara en önemli faktör olarak öne çıkmaktadır. age ve sms_received_1 değişkenleri de önemli katkı
sağlamaktadır.
**Modelin Genel Değerlendirmesi ve Çıkarımlar:**
Model, 'Gelmedi' vakalarını **yüksek duyarlılıkla Recall: %83.29** tespit edebilmektedir. Bu, randevusuna
gelmeyecek kişilerin önemli bir kısmını doğru bir şekilde öngördüğü anlamına gelir. Ancak, **kesinliği Precision:
%30.63** düşüktür. Bu durum, modelin 'Gelmedi' diye tahmin ettiği bazı kişilerin aslında randevuya geldiğini (yanlış
pozitifler) ve dolayısıyla modelin fazla temkinli olduğunu göstermektedir. Bir sağlık kurumu için bu, gereksiz
iletişim SMS, arama vb.) veya kaynak planlaması maliyetlerine yol açabilir.
Modelin genel doğruluğu %59 sınıf dengesizliği nedeniyle yanıltıcı olabilmekle birlikte, özellikle 'Gelmedi'
vakalarını tahmin etme konusundaki düşük kesinlik ve F1Skor değerleri, modelin klinik ortamda tek başına
kullanılmadan önce daha da iyileştirilmesi gerektiğini göstermektedir.


**Sonuç:** Model, 'Gelmedi' riskini yüksek duyarlılıkla tespit edebilmektedir, ancak kesinliği düşüktür. Sağlık
kurumlarında gerçek dünya uygulamaları için yanlış pozitif oranının düşürülmesi ve kesinliğin artırılması
gerekmektedir.



