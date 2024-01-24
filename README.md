# EN: Code Block 1

The code consists of 3 separate blocks. The first block contains the necessary libraries and three different functions.

## `train_and_evaluate_regressor`

- It is a function that takes the name of the method along with the regression variable, train, test, and label variables, and adds it to a DataFrame.
- In this function, the regressor model is fitted, and MAE and RMSE values are calculated.

## `train_and_evaluate_classifier`

- It takes similar arguments to the previous function but the first argument must be a classifier.
- Using the provided classifier, it calculates desired values such as Accuracy, Precision, etc.

## `train_and_evaluate_all_models`

- This function includes TF-IDF, NGRAM, PCA, KBEST, and MODELS parameters.
- After providing training, testing, and label sets as arguments to the function, vectorizer, countvectorizer, pca, kbest, and model variables are also given as needed.
- Inside the function, the model is trained and the test set is transformed using TF-IDF, Countvectorizer, FS, and PCA.
- Then, values desired in the table are saved to a variable using the `train_and_evaluate_regressor/classifier` functions, and finally, all variables are returned as data.

**NOTE:** In this function, control blocks for GaussianNB and MultinominalNB's PCA values have not been calculated. These functions do not accept negative values from the vectorizer. As a solution, I obtained results that can be normalized to the range 0.1, but I removed the functions that would produce these outputs because I couldn't be sure of their accuracy.

# Code Block 2

In this block, the functions for cleaning unnecessary information in texts are prepared with the necessary arguments, and dataframes where the results will be obtained are created.

Using the Nltk library, stop words are removed, and stemming is performed using the PorterStemmer function. Additionally, in the "preprocess" function, a series of operations are applied to remove unnecessary data from texts using regex.

Differently, Linear Regression is used instead of Naive Bayes.

Finally, using Kfold cross-validation, test and train sets, and labels are adjusted, functions are applied, and results for the desired table are stored in a list.

# Code Block 3

In this block, data from the list obtained from Block 2 is combined according to their groups, average values are calculated, and a new table is transferred, then printed as output.



# TR: Kod Blok 1

Kod 3 ayrı bloktan oluşuyor. İlk blok, gerekli kütüphaneleri içerir ve 3 farklı fonksiyona sahiptir.

## `train_and_evaluate_regressor`

- Regresyon değişkeni, train, test ve etiket değişkenleriyle birlikte kullanılacak metod ismini alıp bir DataFrame'e ekleyen fonksiyondur.
- Bu fonksiyonda regressor modeli fit edilir ve MAE ile RMSE değerleri hesaplanır.

## `train_and_evaluate_classifier`

- Yukarıdaki fonksiyonla benzer argümanlar alır, ancak ilk argüman bir classifier olmalıdır.
- Argümana göre verilen classifier'ı kullanarak istenen Accuracy, Precision vb. değerleri hesaplar.

## `train_and_evaluate_all_models`

- Bu fonksiyon, TF-IDF, NGRAM, PCA ve KBEST ve MODELS parametrelerini içerir.
- Eğitim, test ve etiket setlerini fonksiyona argüman olarak verdikten sonra aynı zamanda kullanılacak vectorizer, countvectorizer, pca, kbest ve model değişkenleri gerektiği gibi verilir.
- Fonksiyon içerisinde TF-IDF, Countvectorizer, FS ve PCA kullanılarak model eğitilip test seti transform edilir.
- Daha sonra `train_and_evaluate_regressor/classifier` fonksiyonlarıyla istenilen değerler bir değişkene kaydedilir ve en son tüm değişkenleri içeren veri return edilir.

**NOT:** Bu fonksiyon içerisinde kontrol bloklarıyla GaussianNB VE MultinominalNB'nin PCA değerleri hesaplanmamıştır. Bu fonksiyonlar vectorizer'dan gelen negatif verileri kabul etmiyor. Çözüm olarak 0,1 arasına normalize edilebilir diye bir sonuç elde ettim, ancak doğruluğundan emin olamadığım için bu çıktıları üretecek fonksiyonları kaldırdım.

# Kod Blok 2

Metinlerdeki gereksiz bilgilerin temizlenmesi fonksiyonlarına gerekli argümanların hazırlanması ve sonucun elde edileceği dataframelerin oluşturulması bu blokta gerçekleşiyor.

Nltk kütüphanesi yardımıyla stopword'ler ve PorterStemmer fonksiyonu kullanılarak stemming işlemi yapılıyor. Ayrıca "preprocess" isimli fonksiyonda regex kullanılarak textlerin gereksiz verilerini kaldıracak bir dizi işlem uygulanıyor.

Farklı olarak, Naive Bayes yerine Linear Regression kullanılmıştır.

En son, Kfold cross validation ile test ve train setleri ve etiketleri ayarlanarak fonksiyonlar kullanılıyor ve istenilen tablo için sonuçlar bir listeye aktarılıyor.

# Kod Blok 3

Bu blokta, 2. bloktan gelen listedeki veriler kendi gruplarına göre birleştirilip ortalama değerleri alınıp yeni bir tabloya aktarılıyor ve çıktı olarak bastırılıyor.
