Kod 3 ayrı bloktan oluşuyor ilk blok gerekli kütüphaneler ve 3 farklı fonksiyona sahip.
Bunlar :
• “train_and_evaluate_regressor” : 
o Regresyon değişkeni train test ve etiket değişkenleriyle birlikte kullanılacak metod 
ismini alıp bir DataFrame’e ekleyen fonkisyondur.
o Bu fonksiyonda regressor modeli fit edilip MAE ve RMSE değeleri hesaplanır
• “train_and_evaluate_classifier” :
o Yukarıdaki fonksiyonla benzer argümanlar alır ancak ilk argüman bir classifier 
olmalıdır
o Argümana göre verilen classifier’ı kullanarak en alttaki tabloda istenen 
Accuracy,precision vb. Değerleri hesaplar
• “train_and_evaluate_all_models” :
o Bu fonksiyon TF-IDF, NGRAM, PCA ve KBEST ve MODELS parametrelerini içerir
o Eğitim test ve etiket setlerini fonksiyona argüman olarak verdikten sonra aynı 
zamanda kullanılacak vectorizer, countvectorizer, pca, kbest ve model değişkenleri 
gerektiği gibi verilir.
o Fonksiyon içerisinde TF-IDF Countvectorizer FS ve PCA kullanılarak model eğitilip test 
seti transform edilir.
o Daha sonra train_and_evaluate_regressor/classifier fonksiyonlarıyla tabloda 
istenilen değerler bir değişkene kaydedilip en son tüm değişkenleri içeren veri return 
edilir
▪ NOT: bu fonksiyon içerisinde kontrol bloklarıyla GaussianNB VE 
MultinominalNB’nin pca değerleri hesaplanmamıştır. Bu fonksiyonlar 
vectorizer’dan gelen negatif verileri kabul etmiyor. Çözüm olarak 0,1 arasına 
normalize edilebilir diye bir sonuç elde ettim ancak doğruluğundan emin 
olamadığım için bu çıktıları üretecek fonksiyonları kaldırdım.
Kodun ikinci bloğunda ise
• Metinlerdeki gereksiz bilgileri temizlenmesi fonksiyonlara gerekli argümanları hazırlanması
ve sonucun elde edileceği dataframeleri oluşturulması burada gerçekleşiyor
• Nltk kütüphanesi yardımıyla stopword’ler PorterStemmer fonksiyonu yardımıyla stemming 
işlemi yapılıyor. Ayrıca “preprocess” isimli fonksiyonda regex kullanarak textlerin gerekmez 
verilerini kaldıracak bir dizi işlem uygulanıyor
• Burada farklı olarak naive bayes yerine Linear Regression kullandım 
• En son Kfold cross validation ile test ve train setleri ve etiketleri ayarlanarak fonksiyonlar 
kullanılıyor ve istenilen tablo için sonuçlar bir listeye aktarılıyor
Kodun son bloğunda ise
• 2. bloktan gelen listedeki veriler kendi gruplarına göre birleştirilip ortalama değeleri alınıp 
yeni bir tabloya aktarılıyor ve çıktı olarak bastırılıyo
