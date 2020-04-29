## Learning reading git diff Unified Format (unidiff)

Reference: 
- https://en.wikipedia.org/wiki/Diff#Unified_format
- https://www.git-tower.com/learn/git/ebook/en/command-line/advanced-topics/diffs

Following will be explained in Bahasa Indonesia, you can refer to links above to get better tutorial in English

Tulisan ini hanya menjelaskan cara membaca pesan yang digenerate saat run **diff git** dan ditujukan untuk level beginer.

### 1. Mendapatkan file dan masuk ke direktori
```
git clone https://github.com/sumandari/git-diff
cd git-diff
```
### 2. Melakukan perubahan pada file
- buka file mengunakan text editor yang anda sukai
- edit beberapa bagian yang anda inginkan, atau melakukan hal yang sama persis dengan saya
#### Perubahan yang saya lakukan:
- Pada awal paragraf tambahkan:
```
Perhatian, ini adalah paragraf
yang seharusnya ada pada document ini.
Dan berada di awal document.
```

- Hapus line 20 : Eget velit aliquet sagittis id consectetur.

- Edit line 32: kata **Liat** menjadi _Li**h**at_

- Menambahkan line pada akhir document, disini saya pada line 59:
```

Dan ini adalah paragraf
terakhir yang seharusnya ada.
```

### 3. Run command git diff
Jika anda sudah melakukan perubahan, namun belum run **git add**
```
git diff
```
atau lakukan git add terlebih dahulu
```
git add old_document.txt
git diff
```
karena disini saya hanya membahas tentang cara membaca pesan, maka kita akan mengabaikan staged status dari file tersebut.


### 4. Membaca pesan
```
diff --git a/old_document.txt b/old_document.txt
```
- **a/old_document.txt** -> **a**: adalah path asal
- **b/old_document.txt** -> **b**: adalah path tujuan
- disini karena yang dirubah adalah isi file tanpa merubah direktori/path maka baik a atau pun b valuenya sama yaitu old_document.txt

#### Index
```
index 9dc78b3..30f9d11 100644
```
- Baris tersebut merupakan metafile yang menunjukan hash SHA dari file asal dan file yang sudah dirubah.
- Anda bisa melihatnya dengan command berikut, tapi akan panjang.
```
git show 9dc78b3
```
adalah index file asal
```
git show 30f9d11
```
adalah index file yang sudah dirubah
- **100644** adalah an internal file mode identifier. Anda dapat membacanya pada link referensi di atas
