# Javascript Methot Rehberi
Bu rehber hatırlatma amacı taşımaktadır. 
---
## İçindekiler
- String Metotları
    - at()
    - charAt()
    - charCodeAt()
    - concat()

---

### .at()
Bir tam sayı değeri alır ve stringte karşılık gelen değeri dönderir

Verilen değer bulunamazsa `undefinied` dönderir

```
const pangram = Pijamalı hasta yağız şoföre çabucak güvendi.

pangram.at(5)
//Çıktı: a

pangram.at(-5)
//Çıktı: e
```


---
### .charAt()
0+ değer alır verilen değer string uzunluğundan fazla ise boş string dönderir

"`
const pangram = Pijamalı hasta yağız şoföre çabucak güvendi.
`"
---
### .charCodeAt()

"`
const pangram = Pijamalı hasta yağız şoföre çabucak güvendi.
`"

---
### .concat()

"`
const pangram = Pijamalı hasta yağız şoföre çabucak güvendi.
`"