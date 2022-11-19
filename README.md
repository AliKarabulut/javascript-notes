# Javascript Methot Rehberi
### Bu rehber hatırlatma amacı taşımaktadır! 
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
  - [localeCompare()](#localeCompare)
  - [match()](#match)
  - [matchAll()](#matchAll)
  - [normalize()](#normalize)
  - [padEnd()](#padEnd)
  - [padStart()](#PadStart)
  - [String.raw()](#Stringraw)
  - [repeat()](#repeat)
  - [replace()](#replace)
  - [replaceAll()](#replaceAll)
  - [search()](#search)
  - [slice()](#slice)
  - [split()](#split)
  - [startsWith()](#startsWith)
  - [substring()](#substring)
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

Regular expression kullanımıza izin vermez bunun için search() metodunu kullanmalısınız

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

let dizi = ["a","A","b","c","Ç","ç","B","d","D"]
let data = dizis.sort((a,b) =>{
    return a.localeCompare(b);
})

//Çıktı data: ['a', 'A', 'b', 'B', 'c', 'ç', 'Ç', 'd', 'D']
```
---
### .match()
Verilen regex için ifadeyi tarar ve eşleşmelerin çıktısını verir

```
const str = "Pijamalı hasta yağız şoföre çabucak Güvendi."
const regex = /[A-Z]/g;

pangram.match(regex)
//Çıktı: ["P","G"]
```
---
### .matchAll()
Verilen regex için ifadeyi tarar indeksleri ve gruplarıyla birlikte eşleşmelerin çıktısını verir

```
const str = 'Pijamalı hasta yağız şoföre çabucak hastalomanya güvendi.'
const regex = /ha[a-z]*/g

const matches = [...str.matchAll(regexp)]
//Çıktı: 
['hasta', index: 9, input: 'Pijam...', groups: undefined]
['hastalomanya', index: 36, input: 'Pijam...', groups: undefined]
```
---
### .normalize()
Her ne kadar ekranda görünen string ifadeler tıpa tıp aynı olsa da bazen birden çok kod noktası ya da  kod noktası sırası aynı karakteri verebilir. Peki burada şair ne anlatmak istiyor? `\u00F1 ve \u006E\u0303` = `ñ` çıktısını verir bizler için bu değer aynı olsa da makineler için değil malesef.

Biz Latin alfabeciler için ne alaka desekte aksanlı karakter kullanılan diller için bir sorundur ve hangi değerin verileceği klavyeden klavyeye değişebilir. Örneğin:

let s1 = 'sabiá'
let s2 = 'sabiá'

s1 == s2 yi sorguladığımızda karşımıza çıkacak olan koca bir false'dir. Bu iki değerin uzunlukları bile birbirinden Farklıdır :)

Ve eğer ki string ifadelerin aynı olup olmadığına bakıp aynı olanları çıkardığımız bir durumda, ya da websitemizdeki isimlerin bir listesini almak istediğimizde aynı değerlerin birden çok kez yazılmış olduğunu görebiliriz.

```
let s1 = 'sabiá
let s2 = 'sabiá

s1 === s2
//Çıktı: false

s1.length === s2.length
//Çıktı: false

const nors1 = s1.normalize('NFC')
const nors2 = s2.normalize('NFC')

nors1 === nors2
//Çıktı: true

nors1.length === nors2.length
//Çıktı: true
```
---
### .padEnd()
İki argüman alır ilk argüman sitringin olmasını istediğimiz uzunluğuyken ikinci argüman stringin sonunun ne ile doldurulacağıdır.

ikinci argüman default değeri `boşluk => " "`'tur

```
const str = 'Pijamalı hasta.'

str.padEnd(20,'abc')
//Çıktı: Pijamalı hasta.abcab
```
---
### .padStart()
İki argüman alır ilk argüman sitringin olmasını istediğimiz uzunluğuyken ikinci argüman stringin başının ne ile doldurulacağıdır.

ikinci argüman default değeri `boşluk => " "`'tur

```
const str = 'Pijamalı hasta.'

str.padStart(20,'*')
//Çıktı: *****Pijamalı hasta.
```
---
### String.raw()
Yazılım dillerinde kaçış karakterleri bulunur bunlar string ifade çıktı alınırken eğer ki bunlara sahipse istenen sonuç alınamaz. Bu durumdan kaçınmak için kullanılır

Tırnak işareti değil `BackTick` kullanılır

```
const dosyaYolu = "C:\Development\profile\aboutme.html"
//Çıktı: C:Developmentprofileaboutme.html

const dosyaYolu = String.raw`C:\Development\profile\aboutme.html`
//Çıktı: C:\Development\profile\aboutme.html
```
---
### repeat()
Stringin belirtilen sayıda kopyasını içeren yeni bir string dönderir yani stringi değiştirmez

0-∞ değer alır
```
const str = "Selam Dünyalı"
str.repeat(3)
Çıktı: Selam DünyalıSelam DünyalıSelam Dünyalı
```
---
### replace()
String ifadede bir kelime ya da kelimeleri değiştirmek istediğimizde kullanırız.

Büyük küçük harf duyarlıdır.

Birden çok kelimeyi değiştirecekseniz regular expression kullanmalısınız
```
const str = "Pijamalı hasta yağız şoföre çabucak hasta."

str.replace('hasta','çocuk')
Çıktı: Pijamalı çocuk yağız şoföre çabucak hasta.

const re = /hasta/gi
const str = 'Pijamalı hasta yağız şoföre çabucak hasta.'

str.replace(re, 'çocuk'))

//Çıktı: Pijamalı çocuk yağız şoföre çabucak çocuk.
```
---
### replaceAll()
replace() metodundan farkı bütün eşleşmeleri değiştirmesidir.

Büyük küçük harf duyarlıdır.
```
const str = "Pijamalı hasta yağız şoföre çabucak hasta."

str.replaceAll('hasta','çocuk')
Çıktı: Pijamalı çocuk yağız şoföre çabucak çocuk.
```
---
### search()
Stringi 0. indexten itibaren tarar

İstenen değer bulunamazsa `-1` dönderir

Regular expression kullanımıza izin verir! Bu indexOf() metodundan farkıdır 
```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.search('çabu')
//Çıktı: 28

pangram.search(/has/i)
//Çıktı: 9
```
---
### slice()
Stringin bir bölümünü çıkarır ve döner.

Asıl dizeyi değiştirmez

İki argüman alır. İlk argüman dahil son argüman dahil değildir

Eksi değer alabilir bu durumda stringin sonundan itibaren hesaplar
```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.slice(28)
//Çıktı: çabucak güvendi.

pangram.slice(9,14)
//Çıktı: hasta

pangram.slice(-16)
//Çıktı: çabucak güvendi

pangram.slice(-8)
//Çıktı: güvendi.
```
---
### split()
Stringi verilen değerden parçalara ayırır

Asıl dizeyi değiştirmez

Liste olarak döner

İki argüman alır. İlk argüman stiringin parçalanmasını istediğimiz değerken ikinci argüman limittir
```
const str = "Pijamalı hasta yağız şoföre hasta çabucak güvendi."

str.split(' ',3)
//Çıktı: ['Pijamalı', 'hasta', 'yağız']

str.split('hasta')
//Çıktı: ["Pijamalı ", " yağız şoföre ", " çabucak güvendi."]

str.split('hasta',2)
//Çıktı: ["Pijamalı ", " yağız şoföre "]
```
---
### startsWith()
Stringin verilen değer ile başlayıp başlamadığını kontrol eder

True ya da False döner

İki değer alır ilk değer kontrol edilmesini istediğimiz değerken ikinci değer başlangıç indeksidir
```
const str = "Pijamalı hasta yağız şoföre çabucak güvendi."

str.startsWith('Pija')
//Çıktı: true

str.split('hasta')
//Çıktı: false

str.split('hasta',9)
//Çıktı: true
```
---
### substring()
Slice metodundaki gibi stringin bir bölümünü çıkarır ve döner.

Asıl dizeyi değiştirmez

İki argüman alır. İlk argüman dahil son argüman dahil değildir

Slice'dan farkı negatif değer alamamasıdır. Negatif değer verilirse stringin tamamını döner
```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.substring(28)
//Çıktı: çabucak güvendi.

pangram.substring(9,14)
//Çıktı: hasta

pangram.substring(-16)
//Çıktı: Pijamalı hasta yağız şoföre çabucak güvendi.
```