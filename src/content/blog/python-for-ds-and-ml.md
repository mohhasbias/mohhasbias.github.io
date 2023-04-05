---
title: "Python untuk Data Science dan Machine Learning"
description: "Beberapa library python yang berkaitan dengan Data Science dan Machine Learning"
pubDate: "Mar 30 2023"
# heroImage: "/placeholder-hero.jpg"
# draft: true
---

## Python

Beberapa fitur python yang digunakan antara lain:
- [function][function]
- [loops][loops]
- [lambda][lambda]
- [arithmetic][arithmetic]
- [logic][logic]

Selain itu terdapat beberapa libraries pendukung antara lain:
- [numpy][numpy]: untuk manipulasi array.
- [pandas][pandas]: untuk manipulasi tables. semacam padanan dari spreadsheet.
- [matplotlib][matplotlib]: untuk visualisasi data.
- [seaborn][seaborn]: untuk visualisasi data.
- [plotly][plotly] dan [cufflinks][cufflinks]: untuk visualisasi data interaktif.
- [scikit-learn][scikit-learn]: untuk machine learning.

## Numpy

Beberapa fungsi yang disediakan numpy antara lain:
- `np.array()` : untuk membuat array.
- `np.arange()`: untuk membuat array dengan range tertentu.
- `np.linspace()`: untuk membuat array dengan range tertentu dengan jumlah elemen yang ditentukan.
- `np.zeros()`: untuk membuat array dengan elemen 0.
- `np.ones()`: untuk membuat array dengan elemen 1.
- `np.eye()`: untuk membuat array dengan elemen 1 di diagonal dan 0 di luar diagonal.
- `np.random.rand()`: untuk membuat array dengan elemen random.
- `np.random.randn()`: untuk membuat array dengan elemen random dengan distribusi normal.
- `np.reshape()`: untuk mengubah bentuk/dimensi array.
- `[:,:]`: untuk mengakses seluruh elemen array.
- `[a:b]`: untuk mengakses elemen array dari indeks a sampai b eksklusif.
- `[:b]`: untuk mengakses elemen array dari indeks 0 sampai b eksklusif.
- `[a:]`: untuk mengakses elemen array dari indeks a sampai indeks terakhir.
- `np.max()`: untuk melihat nilai maksimum dari array.
- `np.min()`: untuk melihat nilai minimum dari array.
- `np.argmax()`: untuk melihat indeks dari nilai maksimum dari array.

## Pandas

Pandas adalah library yang running di atas numpy. Pandas menyediakan struktur data yang mirip dengan spreadsheet. Pandas menyediakan dua struktur data utama, yaitu:
- Series: struktur data yang mirip dengan array 1 dimensi.
- DataFrame: struktur data yang mirip dengan array 2 dimensi.

Beberapa fungsi yang disediakan pandas antara lain:
- `pd.read_csv()`: untuk membaca file csv.
- `[DataFrame].head()`: untuk melihat 5 baris pertama dari DataFrame.
- `[DataFrame].tail()`: untuk melihat 5 baris terakhir dari DataFrame.
- `[DataFrame].info()`: untuk melihat informasi dari DataFrame.
- `[DataFrame].value_counts()`: untuk melihat jumlah dari setiap nilai dari kolom tertentu.
- `[DataFrame].mean()`: untuk melihat rata-rata dari setiap kolom.
- `[DataFrame].min()`: untuk melihat nilai minimum dari setiap kolom.
- `[DataFrame].max()`: untuk melihat nilai maksimum dari setiap kolom.
- `[DataFrame].sum()`: untuk melihat jumlah dari setiap kolom.
- `[DataFrame].groupby()`: untuk mengelompokkan data berdasarkan kolom tertentu.
- `[BooleanExpression]`: untuk melakukan filter data.
- `[(bool1) & (bool2)]`: untuk melakukan filter data dengan kondisi AND.
- `[(bool1) | (bool2)]`: untuk melakukan filter data dengan kondisi OR.

Pandas juga memungkinkan untuk melakukan query, seperti query pada database. contoh:
```python
# query table salaries, cari data dengan BasePay > 100000 dan Year = 2013
salaries[(salaries['BasePay'] > 100000) & (salaries['Year'] == 2013)]
```

## Matplotlib

Matlabplotlib adalah library untuk visualisasi data yang terinspirasi dari Matlab. Beberapa fungsi yang disediakan matplotlib antara lain:
- `plt.plot()`: untuk membuat plot.
- `plt.show()`: untuk menampilkan plot.
- `plt.figure()`: untuk membuat figure.
- `plt.subplot()`: untuk membuat subplot.
- `plt.title()`: untuk menambahkan judul pada plot.
- `plt.xlabel()`: untuk menambahkan label sumbu x pada plot.
- `plt.ylabel()`: untuk menambahkan label sumbu y pada plot.
- `plt.legend()`: untuk menambahkan legend pada plot.
- `ax.plot()`: untuk membuat plot pada axis.
- `ax.set_title()`: untuk menambahkan judul pada plot pada axis.
- `ax.set_xlabel()`: untuk menambahkan label sumbu x pada plot pada axis.
- `ax.set_ylabel()`: untuk menambahkan label sumbu y pada plot pada axis.
- `ax.set_xlim()`: untuk menambahkan batas sumbu x pada plot pada axis.
- `ax.set_ylim()`: untuk menambahkan batas sumbu y pada plot pada axis.

matplotlib bisa langsung diakses lewat pandas. contoh:
```python
# membuat plot dari kolom TotalPay
salaries['TotalPay'].plot()
```

## Seaborn

Seaborn dibuat di atas matplotlib. Seaborn menyediakan beberapa chart/diagram yang siap digunakan. antara lain:
- Distribution Plot: untuk melihat distribusi data.
- Categoical Plot: untuk melihat distribusi data berdasarkan kategori.
- Matrix Plot: untuk melihat hubungan antar kolom.
- Grid Plot: untuk melihat hubungan antar kolom dengan kategori.
- Regression Plot: untuk melihat hubungan antar kolom dengan garis regresi.

seaborn bisa digunakan untuk mengubah style dari matplotlib. contoh:
```python
# mengubah style matplotlib menjadi darkgrid
sns.set_style('darkgrid')
```
maka semua plot yang dibuat akan menggunakan style darkgrid.

## Plotly and Cufflinks

Plotly dan Cufflinks adalah library untuk visualisasi data yang interaktif. Plotly dan Cufflinks bisa digunakan untuk membuat plot yang bisa di zoom, di scroll, dan bisa di save ke dalam file html.
Plotly juga bisa digunakan melalui pandas. contoh:
```python
# membuat plot dari kolom TotalPay
salaries['TotalPay'].iplot()
```
Cukup dengan mengubah dari `plot()` menjadi `iplot()`, maka plot yang dibuat akan interaktif.

## Scikit-Learn

Scikit-Learn adalah library untuk machine learning. Scikit-Learn menyediakan beberapa algoritma machine learning, antara lain:
- Linear Regression
- Logistic Regression
- K-Nearest Neighbors
- K-Means
- Decision Trees
- Random Forest
- Support Vector Machines
- Natural Language Processing

## Contoh penggunaan

1. Prediksi menggunakan Multinomial Naive Bayes

    ```python
    # import library
    from sklearn.naive_bayes import MultinomialNB
    from sklearn.metrics import classification_report, confusion_matrix

    # tentukan X dan y
    X = df['text']
    y = df['label']
   
    # split data
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3)
   
    # inisialisasi model
    model = MultinomialNB()

    # training model
    model.fit(X_train, y_train)

    # prediksi
    y_pred = model.predict(X_test)

    # evaluasi model
    print(classification_report(y_test, y_pred))
    print(confusion_matrix(y_test, y_pred))
    ```

## Ringkasan

Keterkaitan antara python dan library-library tersebut bisa dilihat pada gambar berikut:

<div><a href='//sketchviz.com/@mohhasbias/84f18cbe1e1701dfeef50e45c0bcded8'><img alt='interdepensi library' src='https://sketchviz.com/@mohhasbias/84f18cbe1e1701dfeef50e45c0bcded8/84af41a5f45fe96626da0255b944880d58ab14af.sketchy.png' style='max-width: 100%;'></a><br/><span style='font-size: 80%;color:#555;'>Hosted on <a href='//sketchviz.com/' style='color:#555;'>Sketchviz</a></span></div>

## Referensi
[Python for Data Science and Machine Learning Bootcamp
](https://www.udemy.com/course/python-for-data-science-and-machine-learning-bootcamp/learn/lecture/5733386#overview)

[function]: https://www.freecodecamp.org/learn/scientific-computing-with-python/python-for-everybody/python-functions
[loops]: https://www.freecodecamp.org/learn/scientific-computing-with-python/python-for-everybody/loops-and-iterations
[lambda]: https://www.freecodecamp.org/news/python-lambda-functions/
[arithmetic]: https://www.freecodecamp.org/learn/scientific-computing-with-python/python-for-everybody/intermediate-expressions
[logic]: https://www.freecodecamp.org/learn/scientific-computing-with-python/python-for-everybody/intermediate-expressions

[numpy]: https://numpy.org/
[pandas]: https://pandas.pydata.org/
[matplotlib]: https://matplotlib.org/
[seaborn]: https://seaborn.pydata.org/
[plotly]: https://plotly.com/python/
[cufflinks]: https://plotly.com/python/cufflinks/
[scikit-learn]: https://scikit-learn.org/stable/
