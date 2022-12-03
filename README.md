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
  - [toLocaleLowerCase()](#toLocaleLowerCase)
  - [toLocaleUpperCase()](#toLocaleUpperCase)
  - [toLowerCase()](#toLowerCase)
  - [toUpperCase()](#toUpperCase)
  - [trim()](#trim)
  - [trimStart()](#trim)
  - [trimEnd()](#trim)
  - [toString()](#toString)

* [Number Metotları](#Number-Metotları)
  - [Number()](#Number)
  - [Number.isFinite()](#NumberisFinite)
  - [Number.isInteger()](#NumberisInteger)
  - [Number.isSafeInteger()](#NumberisSafeInteger)
  - [Number.MAX_SAFE_INTEGER](#NumberMAX_SAFFE_INTEGER)
  - [Number.MAX_VALUE](#NumberMAX_VALUE)
  - [Number.MIN_SAFE_INTEGER](#NumberMIN_SAFE_INTEGER)
  - [Number.MIN_VALUE](#NumberMIN_VALUE)
  - [Number.POSITIVE_INFINITY](#NumberPOSITIVE_INFINITY)
  - [Number.NEGATIVE_INFINITY](#NumberNEGATIVE_INFINITY)
  - [parseFloat()](#parseFloat)
  - [parseInt()](#parseInt)
  - [toFixed()](#toFixed)
  - [toLocaleString()](#toLocaleString)
  - [toPrecision()](#toPrecision)
  - [toString()](#toString)

* [Array Metotları](#Array-Metotları)
  - [Array()](#Array)
  - [at()](#at-1)
  - [concat()](#concat-1)
  - [copyWithin()](#copyWithin)
  - [entires()](#entires)
  - [every()](#every)
  - [fill()](#fill)
  - [filter()](#filter)
  - [find()](#find)
  - [findIndex()](#findIndex)
  - [findLast()](#findLast)
  - [findLastIndex()](#findLastIndex)
  - [flat()](#flat)
  - [flatMap()](#flatMap)
  - [forEach()](#forEach)
  - [includes()](#includes)
  - [indexOf()](#indexOf)
  - [Array.isArray()](#ArrayisArray)
  - [join()](#join)
  - [lastIndexOf()](#lastindexof-1)
  - [length()](#length-1)
  - [map()](#map)
  - [Array.of()](#Arrayof)
  - [pop()](#pop)
  - [push()](#push)
  - [reverse()](#reverse)
  - [shift()](#shift)
  - [slice()](#slice)
  - [some()](#some)
  - [sort()](#sort)
  - [splice()](#splice)
  - [toLocaleString()](#tolocalestring-1)
  - [toString()](#tostring-2)
  - [unshift()](#unshift)
---
## String Metotları


### .at()
Bir tam sayı değeri alır ve stringte karşılık gelen değeri döndürür.

Verilen değer bulunamazsa `undefinied` döndürür.

```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.at(5)
//Çıktı: a

pangram.at(-5)
//Çıktı: e
```
---
### .charAt()
0+ değer alır verilen değer string uzunluğundan fazla ise boş string döndürür.

Değer verilmezse varsayılan olarak `0` indeksini döndürür.

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
Ondalık tabanda karakter kodunu döndürür 

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
Bağımsız stringleri birleştirir ve yeni bir string döndürür
```
const string1 = 'Selam '
const string2 = 'Bebek '
const list = [' Naber','?']

let sonuc = string1.concat(string2,":)",...list) 
//Çıktı: Selam Bebek :) Naber?
```

---
### .endswith()
Stringin istenen kelime ya da karakterle bitip bitmediğini kontrol eder `True/False` döndürür.

İkinci parametre olarak index değeri alır istenen bitiş verilen indekse karşılık geliyorsa `True` döndürür
```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.endswith('di.')
//Çıktı: true

pangram.endswith('vendi.', 44)
//Çıktı: true
```
---
### .includes()
Stringin içinde istenen değerin var olup olmadığına bakar `True/False` döndürür.

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

İki parametre alır ilk parametre istenen değer iken ikinci parametre kaçıncı indeksten itibaren bakılması istendiğidir.

İstenen değer bulunamazsa `-1` döndürür

ikinci parametre stringin uzunluğundan fazla ise metot arama yapmadan `-1` döndürür

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

İki parametre alır ilk parametre istenen değer iken ikinci parametre kaçıncı indeksten itibaren geriye bakılması istendiğidir.

İstenen değer bulunamazsa `-1` döndürür

ikinci parametre <0 ise `0` indeksine bakar

Boş `''` değeri verilirse `stringin uzunluğunu` döndürür

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
Stringin uzunluğunu döndürür

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

Karşılaştırmada önce sonra ve eşit olma durumuna göre sayı döndürür

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
İki parametre alır ilk parametre sitringin olmasını istediğimiz uzunluğuyken ikinci parametre stringin sonunun ne ile doldurulacağıdır.

ikinci parametre default değeri `boşluk => " "`'tur

```
const str = 'Pijamalı hasta.'

str.padEnd(20,'abc')
//Çıktı: Pijamalı hasta.abcab
```
---
### .padStart()
İki parametre alır ilk parametre sitringin olmasını istediğimiz uzunluğuyken ikinci parametre stringin başının ne ile doldurulacağıdır.

ikinci parametre default değeri `boşluk => " "`'tur

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
### .repeat()
Stringin belirtilen sayıda kopyasını içeren yeni bir string döndürür yani stringi değiştirmez

0-∞ değer alır
```
const str = "Selam Dünyalı"
str.repeat(3)
Çıktı: Selam DünyalıSelam DünyalıSelam Dünyalı
```
---
### .replace()
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
### .replaceAll()
replace() metodundan farkı bütün eşleşmeleri değiştirmesidir.

Büyük küçük harf duyarlıdır.
```
const str = "Pijamalı hasta yağız şoföre çabucak hasta."

str.replaceAll('hasta','çocuk')
Çıktı: Pijamalı çocuk yağız şoföre çabucak çocuk.
```
---
### .search()
Stringi 0. indexten itibaren tarar

İstenen değer bulunamazsa `-1` döndürür

Regular expression kullanımıza izin verir! Bu indexOf() metodundan farkıdır 
```
const pangram = "Pijamalı hasta yağız şoföre çabucak güvendi."

pangram.search('çabu')
//Çıktı: 28

pangram.search(/has/i)
//Çıktı: 9
```
---
### .slice()
Stringin bir bölümünü çıkarır ve döner.

Asıl dizeyi değiştirmez

İki parametre alır. İlk parametre dahil son parametre dahil değildir

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
### .split()
Stringi verilen değerden parçalara ayırır

Asıl dizeyi değiştirmez

Liste olarak döner

İki parametre alır. İlk parametre stiringin parçalanmasını istediğimiz değerken ikinci parametre limittir
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
### .startsWith()
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
### .substring()
Slice metodundaki gibi stringin bir bölümünü çıkarır ve döner.

Asıl dizeyi değiştirmez

İki parametre alır. İlk parametre dahil son parametre dahil değildir

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
### .toLocaleLowerCase()
Stringi küçük harfe döndürür

İstenirse içine dönüşüm yapılacak dil kodu da girilebilir
```
const str = "YAĞIZ ŞOFÖR"

str.toLocaleLowerCase()
//Çıktı: yağiz şoför

str.toLocaleLowerCase('tr')
//Çıktı: yağız şoför
```
---
### .toLocaleUpperCase()
Stringi büyük harfe döndürür

İstenirse içine dönüşüm yapılacak dil kodu da girilebilir
```
const str = "pijamalı hasta"

str.toLocaleUpperCase()
//Çıktı: PİJAMALI HASTA

str.toLocaleUpperCase('en-US')
//Çıktı: PIJAMALI HASTA
```
---
### .toLowerCase()
String ifadeyi küçük harflere dönüştürür.

```
const str = "YAĞIZ ŞOFÖR"

str.toLowerCase()
//Çıktı: yağiz şoför

```
---
### .toUpperCase()
String ifadeyi büyük harflere dönüştürür.

```
const str = "pijamalı hasta"

str.toLocaleUpperCase()
//Çıktı: PIJAMALI HASTA
```
---
### .trim()
String ifadenin başındaki ve sonundaki boşlukları kaldırır.

```
const str = "   Pijamalı Hasta   "

str.trim()
//Çıktı: Pijamalı Hasta
```
---
### .trimStart()
String ifadenin başındaki boşlukları kaldırır.
```
const str = "   Pijamalı Hasta   "

str.trimStart()
//Çıktı: "Pijamalı Hasta     "
```
---
### .trimEnd()
String ifadenin sonundaki boşlukları kaldırır.

```
const str = "   Pijamalı Hasta   "

str.trimEnd()
//Çıktı: "     Pijamalı Hasta"
```
---
### .toString()
Kendisine tanımlanan değişken değerini string olarak değiştirerek döndürür.

```
const num = 684
const bool = true

str.toString()
//Çıktı: "684"

str.toString()
//Çıktı: "true"
```
## Number Metotları

### Number()
Her hangi bir veri türünü sayıya çevirmek için kullanırız
```
Number("5")
//Çıktı: 5

Number("    5")
//Çıktı: 5

Number(true)
//Çıktı: 1

Number("5a")
//Çıktı: NAN
```
---
### Number.isFinite()
Yapılan sayısal işlemin sonucunun sonlu olup olmadığını kontrol eder

Sonzuz ise `false` döndürür

Sonlu ise `true` döndürür

```
const islem1 = 5
const islem2 = 1/0

Number.isFinite(islem1)
//Çıktı: true

Number.isFinite(islem2)
//Çıktı: false
```
---
### Number.isInteger()
Yapılan sayısal işlemin sonucunun ya da verilen değerin tam sayı olup olmadığını kontrol eder Sonucunda `true / false` döndürür

```
const islem = 5/2

Number.isInteger(islem)
//Çıktı: false

Number.isInteger(5)
//Çıktı: true

Number.isInteger(5.5)
//Çıktı: false
```
---
### Number.isSafeInteger()
Sayısal değerin güvenilir olup olmadığını kontrol eder. `true / false` döndürür

Javascriptte tam sayılar `-2^53 +1 / 2^53 -1` aralığı güvenilir tamsayı olarak ifade edilir. Bu değerlerin üstündeki bir değeri javascript hesaplarken bir veya daha fazla işlem aynı sonuçları verir.

Noktalı sayılar tam sayı olmadığı için `false` döndürür.

```
//

Number.isSafeInteger(9007199254740991)
//Çıktı: true

Number.isSafeInteger(5.1)
//Çıktı: false

9007199254740991 + 1
//Çıktı: true


9007199254740992 + 0 = ...2
9007199254740992 + 1 = ...2
9007199254740992 + 2 = ...4
9007199254740992 + 3 = ...6
```
---
### Number.MAX_SAFE_INTEGER
En büyük güvenilir tam sayıyı temsil eder.

```
Number.MAX_SAFE_INTEGER
//Çıktı: 9007199254740991
```
---
### Number.MAX_VALUE
Javascriptte gösterilebilen en büyük sayısal değeri temsil eder.

Javascript bu değerin üstünü sonsuz olarak ifade eder.

Değer `1.79E+308` yani `1,7976931348623157 × 10^308'dir`.

```
Number.MAX_VALUE
//Çıktı: -9007199254740991
```
---
### Number.MIN_SAFE_INTEGER
En küçük güvenilir tam sayıyı temsil eder

```
Number.MIN_SAFE_INTEGER
//Çıktı: -9007199254740991
```
---
### Number.MIN_VALUE
Javascriptte pozitif sıfıra en yakın sayıyı temsil eder.

Değer `5e-324` yani `2^-1074'dür`.

```
Number.MIN_VALUE
//Çıktı: 5e-324
```
---
### Number.POSITIVE_INFINITY
Pozitif sonsuzluğu temsil eder

```
Number.NEGATIVE_INFINITY
//Çıktı: Infinity
```
---
### Number.NEGATIVE_INFINITY
Negatif sonsuzluğu temsil eder

```
Number.NEGATIVE_INFINITY
//Çıktı: -Infinity
```
---
### .parseFloat()
Verilen değeri ondalıklı sayı haline dönüştürür ve döner.

Artı, eksi, nokta haricinde bir değer görürse durur ve  devamını dahil etmez.

Verilen değerden sayı ayrıştırılamazsa `NaN` döner

```
parseFloat('45asdf')
//Çıktı: 45

parseFloat('99.9asdf')
//Çıktı: 99.9

parseFloat("r3232")
//Çıktı: NaN
```
---
### .parseInt()
Verilen string ya da sayı değerini tam sayıya çevirir

İkinci parametre hangi tabanda çevrileceğini belirtir

İkinci parametre verilmezse 10 tabanında dönüşüm yapar

Verilen değerden sayı ayrıştırılamazsa `NaN` döner

```
parseInt('45asdf')
//Çıktı: 45

parseInt('99.9asdf')
//Çıktı: 99

parseInt(10,2)
//Çıktı: 2
```
---
### .toFixed()
Sayısal değerin noktadan sonra kaç basamaklı olmasını istiyorsak parametre olarak veririz. Parametre verilmezse basamakları tamamen kaldırır.

Sayıları yuvarlama yaparak verir.

Sayısal ifadenin noktadan sonrasının uzunluğundan daha büyük bir sayı verilirse sonunu `0` ile doldurur 

```
const num = 45.547

num.toFixed()
//Çıktı: 46

num.toFixed(2)
//Çıktı: 45.55

num.toFixed(5)
//Çıktı: 45.54700
```
---
### .toLocaleString()
Tarih, saat, sayılar,nesneler,diziler alır ve istenen dilde dizeye dönüştürür.

```
const date = new Date()
date.toLocaleString('tr-TR')

//Çıktı: 25.11.2022 20:44:20

const num = 123456.789
date.toLocaleString('ar-EG')

//Çıktı: ١٢٣٤٥٦٫٧٨٩
```
---
### .toPrecision()
toFixed ile aynı şeyi yapar farkları toPrecision metodunun tam kısmı da dahil etmesidir.

```
const num = 45.567

num.toPrecision(3)
//Çıktı: 45.6
```
---
### .toString()
Sayısal değeri string ifadeye dönüştürür.

```
const num = 45.567

num.toString()
//Çıktı: "45.567"
```

## Array Metotları

### Array()
`0 >=` tek bir sayı verilirse verilen sayı kadar elemanı olan ve elemanları undefinied olan bir dize döndürür.

Verilen elemanlarla yeni bir dize oluşturur.

```
const array = Array(3)
// [undefined, undefined, undefined]

const array = Array(1,2,3)
// [1,2,3]
```

---
### .at()
Dizenin istenen indexteki elemanını döndürür.

Eksi değer verilirse tersten sayar.

```
const array = [1, 3, 2, 7]

array.at(2)
// 2

array.at(-3)
// 3
```
---
### .concat()
2 ya da daha fazla dizeyi birleştirmek için kullanılır.

Orjinal dizeyi değiştirmez. Yeni bir array döndürür.

Syntax => 
`concat ( )`
`concat ( değer0 )`
`concat ( değer0 , değer1 )`
`concat ( değer0 , değer1 , + , + değerN )`

```
const num1 = [1, 2]
const num2 = [3, 4]
const num3 = [5, 6]

const numbers = num1.concat(num2, num3)
// [1,2,3,4,5,6]
```
---
### .copyWithin()
Dizinin bir bölümünü aynı dizideki başka bir konuma kopyalar ve uzunluğunu değiştirmeden geri döndürür.

!Orjinal dizeyi değiştirir

Syntax => {
`copyWithin ( hedef )` 
`copyWithin ( hedef , başlangıç )` 
`copyWithin ( hedef , başlangıç , bitiş )` 
}
```
const array = ['a', 'b', 'c', 'd', 'e']

array.copyWithin(0, 3, 4)
// ['d', 'b', 'c', 'd', 'e']

array.copyWithin(1, 3)
// ['a', 'd', 'e', 'd', 'e']
```
---
### .entries()
Bir dizinin her bir dizin elemanı için anahtar ve değer çiftlerini içeren yeni bir dizi döndürür.

Syntax => {
`entries()` 
}
```
const array = ['a', 'b', 'c', 'd', 'e']
const iterator = array.entries()

iterator.next().value
// [0, "a"]

iterator.next().value
// [1, "b"]
```
---
### .every()
Dizideki tüm öğelerin verilen fonksiyon tarafından uygulanan testi geçip geçemediğini test eder

`true / false` döndürür

Syntax => {
`every((element) => {} )`
}
```
const array = [1,2,3,4,5,6]

array.every((sayi) => sayi < 8)
// true

array.every((sayi) => sayi * 2 < 11 )
// false
```
---
### .fill()
Dizideki öğeleri başlangıç indeksinden bitiş indeksine kadar istenen değerle değiştirir.

!Orjinal diziyi değiştirir.

Başlangıç değeri negatif ise `dizi uzunluğu + başlangıç değeri`
Bitiş değeri negatif ise `dizi uzunluğu + bitiş değeri`

Syntax => {
`fill ( değer )`
`fill ( değer , başlangıç )`
`fill ( değer , başlangıç , bitiş )`
}
```
const array = [1, 2, 3, 4]

array.fill(0, 2, 4)
// [1, 2, 0, 0]

array1.fill(5, 1)
// [1, 5, 5, 5]

array1.fill(0, -3, -1)
// [1,0,0,4]
```
---
### .filter()
Diziyi istenen fonksiyondan tarafından teste tabi tutar ve testi geçenleri döndürür.

Hiçbir değer testi geçemezse boş dize döner.

Syntax => {
`filter( (element)  => {} ) `
}
```
const array = [1, 38, 18, 21, 5]

array.filter((sayi) => sayi > 18)
// [38, 21]
```
---
### .find()
Diziyi istenen fonksiyondan tarafından teste tabi tutar ve testi geçen ilk elemanı döndürür.

Hiçbir değer testi geçemezse `undefinied` döndürür.

Syntax => {
`find( (element)  => {} ) `
}
```
const array = [1, 38, 18, 21, 5]

array.find((sayi) => sayi > 2)
// 38
```
---
### .findIndex()
Diziyi istenen fonksiyondan tarafından teste tabi tutar ve testi geçen ilk elemanın indeksini döndürür.

Hiçbir değer testi geçemezse `-1` döndürür.

Syntax => {
`findIndex( (element)  => {} ) `
}
```
const array = [1, 18, 38, 21, 5]

array.findIndex((sayi) => sayi > 30)
// 2
```
---
### .findLast()
Diziyi istenen fonksiyondan tarafından teste tabi tutar ve testi geçen son elemanın döndürür.

Hiçbir değer testi geçemezse `undefined` döndürür.

Syntax => {
`findLast( (element)  => {} ) `
}
```
const array = [1, 18, 38, 21, 5]

array.findLast((sayi) => sayi > 6)
// 21
```
---
### .findLastIndex()
Diziyi istenen fonksiyondan tarafından teste tabi tutar ve testi geçen son elemanın indeksini döndürür.

Hiçbir değer testi geçemezse `-1` döndürür.

Syntax => {
`findLastIndex( (element)  => {} ) `
}
```
const array = [1, 18, 38, 21, 5]

array.findIndex((sayi) => sayi > 6)
// 3
```
---
### .flat()
İç içe dizileri istenen değer kadar ayrıştırarak dışarı çıkarır.

Syntax => {
`flat()`
`flat(depth)`
}
```
const array = [1, 18, [38, 21], [[5]]]

array.flat()
// [1, 18, 38, 21, [5]]

array.flat(2)
// [1, 18, 38, 21, 5]
```
---
### .flatMap()
Yeni bir array dönderir flat() metoduna 1 verilmesi ile aynıdır.

Her bir elemanı .map() metodu gibi teker teker döner.

Syntax => {
`flatMap( (Mevcut değer)  => {} )`

}
```
const array=['aa bb', '45 65']

.flatMap(el => el.split(' '))
// ["aa", "bb", "45", "65"]
```
---
### .forEach()
Her dizi öğesi için verilen fonksiyonu bir kez yürütür.

Syntax => {
`forEach( (Mevcut değer)  => {} )`

}
```
const array=[1,2,3,4]

.forEach(num => console.log(num))
// 1
// 2
// 3
```
---
### .includes()
Bir dizenin elemanları arasında istenen değerin olup olmadığını kontrol eder.

`true / false` döndürür

Syntax => {
`includes(aranan eleman)`
`includes(aranan eleman, başlangıç indeksi)`

}
```
const array=["selam","kedi","ayı"]

.includes("selam")
// true

.includes("kedi",2)
// false

.includes("ke")
// false
```
---
### .indexOf()
Bir dizenin elemanları arasında istenen değerin hangi indekste olduğunu arar ve döndürür.

Bulamazsa `-1` döndürür

Syntax => {
`indexOf(aranan eleman)`
`indexOf(aranan eleman, başlama indeksi)`

}
```
const array=["selam","kedi","ayı","selam"]

.indexOf("selam")
// 0

.indexOf("kedi",2)
// -1

.indexOf("selam",2)
// 3
```
---
### Array.isArray()
Verilen değerin dizi olup olmadığını kontrol eder.

Syntax => {
`Array.isArray(değer)`
}
```
Array.isArray([1])
// true

Array.isArray(new Array('a', 'b', 'c', 'd'))
// true


Array.isArray(undefined)
// false

Array.isArray(17)
// false
```
---
### .join()
Verilen bir dizinin elemanları arasına verilen değeri koyarak birleştirip stringe dönüştürür.

Default değeri `,`'dür

Syntax => {
`join()`
`join(ayırıcı değer)`
}
```
const array = ['Selam', 'dünyalı', 'nasılsın' '?']

join()
// "Selam,dünyalı,nasılsın,?"

join('')
// "Selamdünyalınasılsın?"
```
---
### .lastIndexOf()
Dizinin son elemanından başlayarak istenen elemanı arar ve indeks numarasını döndürür

Bulamazsa `-1` döndürür

Syntax => {
`lastIndexOf(aranan eleman)`
`lastIndexOf(aranan eleman, başlama indeksi)`
}
```
const array=["selam","kedi","ayı","selam"]

.lastIndexOf("selam")
// 3

.lastIndexOf("Aslan")
// -1

.lastIndexOf("selam",2)
// 0
```
---
### .length()
Dizenin kaç eleman olduğunu döndürür.

Syntax => {
`length()`
}
```
const array=["selam","kedi","ayı","selam"]

.length()
// 4
```
---
### .map()
Dizideki her elemanı teker teker gezer ve verilen işlevden geçirir.

Yeni bir dize oluşturur ve işlevden geçen elemanları içine yerleştirir

Syntax => {
`map( (element)  =>  {} ) `
}
```
const array = [1, 2, 3, 4, 5]

.map( x => x**2)
// [1, 4, 9, 16, 25]
```
---
### Array.of()
Verilen argümanlarla yeni bir dize oluşturur.

Array metodu ile farkı:

Array(7) => 7 elemanlı bir dizi oluşturur

Array.of(7) => Tek elemanlı ve elemanı 7 olan bir dize oluşturur

Syntax => {
`Array.of(eleman)`
`Array.of(eleman1, eleman2,...,elemanN)`
}
```
Array.of(1, 2, 3)
// [1, 2, 3]
```
---
### .pop()
Dizinin son elemanını diziden atar

Diziden atılan elemanı döndürür.

Syntax => {
`pop()`

}
```
const array = ["Elma", "Armut", "Vişne", "Limon", "Kayısı"]

plants.pop()
// Kayısı
```
---
### .push()
Dizenin sonuna verilen eleman/elemanları ekler

Syntax => {
`push(eleman)`
`push(eleman, ..., elemanN)`
}
```
const array = ["Elma", "Armut", "Vişne"]

array.push("Limon", Erik)
// ["Elma", "Armut", "Vişne", "Limon", "Erik"]
```
---
### .reverse()
Dizeyi ters çevirir

Syntax => {
`reverse()`

}
```
const array = ["Bir", "İki", "Üç"]

array.reverse()
// ["Üç", "İki", "Bir"]
```
---
### .shift()
Dizenin ilk elemanını dizeden atar.

Diziden atılan elemanı döndürür.

Syntax => {
`shift()`
}
```
const array = ["Bir", "İki", "Üç"]

array.shift()
// "Bir"
```
---
### .slice()
Dizinin istenen aralıktaki değerlerini döndürür.

Bitiş noktası dahil değildir.

Eksi değer verilirse dizenin sonundan başlar.

Syntax => {
`slice()`
`slice(start)`
`slice(start, end)`
}
```
const array = ["Bir", "İki", "Üç","Dört","Beş","Altı"]

array.slice(3)
// ["Dört", "Beş", "Altı"]

array.slice(2,4)
// ["Üç", "Dört"]

array.slice(2,-1)
// ["Üç", "Dört", "Beş"]
```
---
### .some()
Dizideki en az bir elemanın sağlanan fonksiyon tarafından uygulanan testi geçip geçemediğini kontrol eder.

`true / false` döndürür

Syntax => {
`some( (mevcut değer) => {} )`

}
```
const array = [1, 2, 3, 4, 5]

array.some((element) => element % 2 === 0)
// true
```
---
### .sort()
Dizideki elemanları `alfabetik` olarak sıralar.

Sayısal karşılaştırma için karşılaştırma fonksiyonu yazılmalıdır

Syntax => {

    sort()

    sort( (a,b) => {} )
}
```
const array = [11, 20, 9, 10, 1, 2]

array.sort()
// [1, 10, 11, 2, 20, 9]

array.sort((a,b) => {return a-b})
// [1, 2, 9, 10, 11, 20]
```
---
### .splice()
Dizenin mevcut öğelerini kaldırarak veya değiştirerek ve/veya yerine yeni öğeler ekleyerek dizenin içeriğini değiştirir.

`'SS' => başlangıç değerinden itibaren kaç öğenin silineceğidir.`

Syntax => {

    splice(başlangıç)
    splice(başlangıç, SS)
    splice(başlangıç, SS, eklenecek/ler)
}
```
const array = [1, 2, 3, 4, 5, 6, 7]

array.splice(1)
// [1]

array.splice(1,0,99)
// [1, 99, 2, 3, 4, 5, 6, 7]

array.splice(1,4,99)
// Array [1, 99, 6, 7]
```
---
### .toLocaleString()
Number metotlarında gösterilmiştir.

=> [toLocaleString()](#toLocaleString)
```
const array = [1,2,3]

array.toLocaleString('ar-EG')
// "١,٢,٣"
```
---
### .toString()
String metotlarında gösterilmiştir.

=> [toString()](#toString)
```
const array = [1, 2, 'a', '1a',true]

array.toString()
// "1,2,a,1a,true"
```
---
### .unshift()
Bir dizinin başına bir veya daha fazla öğe ekler ve dizinin yeni uzunluğunu döndürür.

Syntax => {

    unshift(element0)
    
    unshift(element0, … , elementN)
}
```
const array = [1, 2, 3]

array.unshift(4,5,"a")
// 6

Dizinin yeni hali
// array => [4, 5, "a", 1, 2, 3]
```