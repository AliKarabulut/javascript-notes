# Javascript Methot Rehberi
Bu rehber hatırlatma amacı taşımaktadır. 
---
## İçindekiler
* [String Metotları](#String-Metotları)
  - [at()](#at)
  - [charAt()](#charAt)
  - [charCodeAt()](#charCodeAt)
  - [concat()](#concat)
  - [endswith()](#endswith)
  - [includes()](#includes)
  - [indexOf()](#indexOf)
  - [lastIndexOf()](#lastIndexOf)
  - [length](#length)
---
## String Metotları


### .at()
Bir tam sayı değeri alır ve stringte karşılık gelen değeri dönderir.

Verilen değer bulunamazsa `undefinied` dönderir.

```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.at(5)
//Çıktı: a

pangram.at(-5)
//Çıktı: e
```
---
### .charAt()
0+ değer alır verilen değer string uzunluğundan fazla ise boş string dönderir.

Değer verilmezse varsayılan olarak `0` indeksini dönderir.

```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.charat(5)
//Çıktı: a

pangram.charAt()
//Çıktı: P

pangram.charat(-5)
//Çıktı: " "
```
---
### .charCodeAt()
Ondalık tabanda karakter kodunu dönderir 

`Alt + karakter kodu` ile değeri kullanarak çıktısını alabilirsiniz.
```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.charCodeAt(8)
//Çıktı: 107

pangram.charCodeAt(-8)
//Çıktı: NAN
```

---
### .concat()
Bağımsız stringleri birleştirir ve yeni bir string dönderir
```
const string1 = 'Selam '
const string2 = 'Bebek '
const list = [' Naber','?']

let sonuc = string1.concat(string2,":)",...list) 
//Çıktı: Selam Bebek :) Naber?
```

---
### .endswith()
Stringin istenen kelime ya da karakterle bitip bitmediğini kontrol eder `True/False` dönderir.

İkinci argüman olarak index değeri alır istenen bitiş verilen indekse karşılık geliyorsa `True` dönderir
```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.endswith('di.')
//Çıktı: true

pangram.endswith('vendi.', 44)
//Çıktı: true
```
---
### .includes()
Stringin içinde istenen değerin var olup olmadığına bakar `True/False` dönderir.

Büyük-küçük harf duyarlıdır 

```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.includes('ndi.')
//Çıktı: true

pangram.includes('Güvendi.')
//Çıktı: false
```
---
### .indexOf()
Stringi 0. indexten itibaren tarar

İki argüman alır ilk argüman istenen değer iken ikinci argüman kaçıncı indeksten itibaren bakılması istendiğidir.

İstenen değer bulunamazsa `-1` dönderir

ikinci argüman stringin uzunluğundan fazla ise metot arama yapmadan `-1` dönderir

```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi. Pijamalı"

pangram.indexOf('asta')
//Çıktı: 10

pangram.indexOf('Hasta')
//Çıktı: -1

pangram.indexOf('Pija',20)
//Çıktı: 45
```
---
### .lastIndexOf()
Stringi sondan tarayarak istenen değeri arar

İki argüman alır ilk argüman istenen değer iken ikinci argüman kaçıncı indeksten itibaren geriye bakılması istendiğidir.

İstenen değer bulunamazsa `-1` dönderir

ikinci argüman <0 ise `0` indeksine bakar

Boş `''` değeri verilirse `stringin uzunluğunu` dönderir

```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi. Pijamalı"

pangram.lastIndexOf('Pija')
//Çıktı: 45

pangram.lastIndexOf('Pija',5)
//Çıktı: 0

pangram.lastIndexOf('')
//Çıktı: 53
```
---
### .length
Stringin uzunluğunu dönderir

Boş string için uzunluk `0`'dır

```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."
const empty = ""

pangram.length
//Çıktı: 44

empty.length
//Çıktı: 0
```
---
### .localeCompare()
Javascript ASCII karakterleri dışındaki karakterleri sıralamaz ve sona atar. Bunun önüne geçmek için kullanılır

Karşılaştırmada önce sonra ve eşit olma durumuna göre sayı dönderir

Küçük harfler büyüklerden önce gelir

```
const string1 = 'a'
const string2 = 'A'
const string3 = 'ç'


string1.localeCompare(string2)
//Çıktı: -1

string3.localeCompare(string2)
//Çıktı: 1

`Dizi sıralamasına örnek`
```
let dizi = ["a","A","b","c","Ç","ç","B","d","D"]
let data = dizis.sort((a,b) =>{
    return a.localeCompare(b);
})
//Çıktı data: ['a', 'A', 'b', 'B', 'c', 'ç', 'Ç', 'd', 'D']
```
```
---