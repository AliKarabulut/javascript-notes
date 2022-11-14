# Javascript Methot Rehberi
Bu rehber hatırlatma amacı taşımaktadır. 
---
## İçindekiler
- String Metotları
    - at()
    - charAt()
    - charCodeAt()
    - concat()

* [String Metotları](#String-Metotları)
  - [at()](#at())
  - [charAt()](#charAt())
  - [charCodeAt()](#charCodeAt())
  - [concat()](#concat())
  - [endswith()](#endswith())

---
## String Metotları
---

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