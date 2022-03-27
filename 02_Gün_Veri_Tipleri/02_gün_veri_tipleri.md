<div align="center">
  <h1> 30 Günde JavaScript: Veri Tipleri</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

  <sub>Author:
  <a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
  <small> January, 2020</small>
  </sub>
</div>
</div>

[<< 1. Gün](../readMe.md) | [3. Gün >>](../03_Day_Booleans_operators_date/03_booleans_operators_date.md)

![Otuz Günde JavaScript](../images/banners/day_1_2.png)

- [📔 2. Gün](#-2.-gün)
	- [Data Types](#data-types)
		- [Primitive Data Types ](#primitive-data-types)
		- [Non-Primitive Data Types](#non-primitive-data-types)
	- [Numbers](#numbers)
		- [Declaring Number Data Types](#declaring-number-data-types)
		- [Math Object](#math-object)
			- [Random Number Generator](#random-number-generator)
	- [Strings](#strings)
		- [String Concatenation](#string-concatenation)
			- [Concatenating Using Addition Operator](#concatenating-using-addition-operator)
			- [Long Literal Strings](#long-literal-strings)
			- [Escape Sequences in Strings](#escape-sequences-in-strings)
			- [Template Literals (Template Strings)](#template-literals-template-strings)
		- [String Methods](#string-methods)
	- [Checking Data Types and Casting](#checking-data-types-and-casting)
		- [Checking Data Types](#checking-data-types)
		- [Changing Data Type (Casting)](#changing-data-type-casting)
			- [String to Int](#string-to-int)
			- [String to Float](#string-to-float)
			- [Float to Int](#float-to-int)
	- [💻 Day 2: Exercises](#-day-2-exercises)
		- [Exercise: Level 1](#exercise-level-1)
		- [Exercise: Level 2](#exercise-level-2)
		- [Exercises: Level 3](#exercises-level-3)

# 📔 Day 2

## Data Types 
_Tr = Veri Türleri_

Bir önceki bölümde, veri türlerinden biraz bahsettik. Veri veya değerlerin veri türleri vardır. Veri türleri, verilerin özelliklerini tanımlar. Veri tipleri 2'ye ayrılır:

1. İlkel veri türleri
2. İlkel olmayan veri türleri(Nesne Referansları)

### Primitive Data Types
_Tr = İlkel Veri Türleri_

JavaScript'teki ilkel veri türleri şunları içerir:

 1. Numbers - Integers, floats 
 2. Strings - Tek tırnak, çift tırnak veya ters tırnak alıntısı altındaki tüm veriler
 3. Booleans - true yada false değerleri
 4. Null - boş değer veya değer yok
 5. Undefined - tanımlanmamış

JavaScript'teki ilkel olmayan veri türleri şunları içerir:

1. Object 'ler
2. Function 'lar
3. Array 'ler

Şimdi ilkel ve ilkel olmayan veri türlerinin tam olarak ne anlama geldiğini görelim.
*Primitive* (ilkel) veri türleri değişmez (değiştirilemez) veri türleridir. İlkel bir veri türü oluşturulduktan sonra onu değiştiremeyiz.

**Örnek:**

```js
let word = 'JavaScript'
```

*word* değişkeninde saklanan dizeyi değiştirmeye çalışırsak, JavaScript bir hata oluşturmalıdır. Tek bir alıntı altında herhangi bir veri türü, çift ​​tırnak, veya backtick alıntı bir dize veri türüdür.

```js
word[0] = 'Y'
```

Bu ifade, *word* değişkeninde saklanan dizeyi değiştirmez. İlkel veri türleri değerlerine göre karşılaştırılır. Farklı veri değerlerini karşılaştıralım. Aşağıdaki örneğe bakın:

```js
let numOne = 3
let numTwo = 3

console.log(numOne == numTwo)      // doğru

let js = 'JavaScript'
let py = 'Python'

console.log(js == py)             //yanlış

let lightOn = true
let lightOff = false

console.log(lightOn == lightOff) // yanlış
```

### Non-Primitive Data Types
_Tr = İlkel Olmayan Veri Türleri_

*Non-primitive* (İlkel Olmayan) veri türleri değiştirilebilir. İlkel olmayan veri türlerinin değerini, oluşturulduktan sonra değiştirebiliriz.
Hadi bunu örnek bir dizi oluşturarak görelim. Dizi, köşeli parantez içindeki veri değerlerinin bir listesidir. Diziler aynı veya farklı veri türlerini içerebilir. Dizinlere "Array" diyoruz. JavaScript'te Array'lerdeki elemanlar sayısı sıfırdan başlar. Yani, bir dizinin ilk elemanı 0. eleman, ikinci elemanı 1. eleman, üçüncü elemanı ise 2. elemandır. Saymaya 0'dan başlarız.
```js
let nums = [1, 2, 3]
nums[0] = 10

console.log(nums)  // [10, 2, 3]
```

Gördüğünüz gibi, ilkel olmayan bir veri türü olan bir array değişkendir. İlkel olmayan veri türleri değere göre karşılaştırılamaz. İlkel olmayan iki veri türü aynı özelliklere ve değerlere sahip olsa bile, kesinlikle eşit değildirler. 

```js
let nums = [1, 2, 3]
let numbers = [1, 2, 3]

console.log(nums == numbers)  // false 

let userOne = {
name:'Asabeneh',
role:'teaching',
country:'Finland'
}

let userTwo = {
name:'Asabeneh',
role:'teaching',
country:'Finland'
}

console.log(userOne == userTwo) // false
```

Temel kural, ilkel olmayan veri türlerini karşılaştırmıyoruz. Dizileri, işlevleri veya nesneleri karşılaştırmayın.
İlkel olmayan değerler, değer yerine referansla karşılaştırıldıkları için referans türleri olarak adlandırılır. İki nesne, yalnızca aynı temel nesneye atıfta bulunuyorlarsa eşittir.

```js
let nums = [1, 2, 3]
let numbers = nums

console.log(nums == numbers)  // true

let userOne = {
name:'Asabeneh',
role:'teaching',
country:'Finland'
}

let userTwo = userOne

console.log(userOne == userTwo)  // true
```

İlkel veri türleri ile ilkel olmayan veri türleri arasındaki farkı anlamakta zorlanıyor olabilirsiniz. Sakin olun ve bir sonraki bölüme geçin ve bir süre sonra geri gelip tekrar çalışın. Şimdi sayı türüne göre veri türlerine başlayalım.

## Numbers
_Tr = Sayılar_

Sayılar, tüm aritmetik işlemleri yapabilen tam sayılar ve ondalık değerlerdir.
Sayılarla ilgili bazı örnekler görelim.

### Declaring Number Data Types
_Tr = Sayı Veri Türleri_

```js
let age = 35
const gravity = 9.81  // değişmeyen ve sabit olan değerler için const kullanırız. Örneğin yer çekimi  m/s2
let mass = 72         // kütlemiz farklı ortamlarda değişiklik göstereceği için let ile yazarız.
const PI = 3.14       // pi sayısı sabittir. O yüzden const ile yazarız.

// örnekler
const boilingPoint = 100 // Suyun Normal Koşullar'da kaynama derecesi sabittir.
const bodyTemp = 37      // Ortalama insan vücut sıcaklığı. 

console.log(age, gravity, mass, PI, boilingPoint, bodyTemp)
```

### Math Object
_Tr = Matematiksel İfadeler_

JavaScript'te Math Object, sayılarla çalışmak için birçok yöntem sağlar.

```js
const PI = Math.PI

console.log(PI)                            // 3.141592653589793

// En yakın sayıya yuvarlama
// 0,5'in üzerindeyse bir üst sayıya altındaysa bi alt sayıya

console.log(Math.round(PI))                // 3 - en yakın sayıya yuvarlamak için

console.log(Math.round(9.81))              // 10 - en yakın sayıya yuvarlamak için

console.log(Math.floor(PI))                // 3 - aşağı yuvarlama

console.log(Math.ceil(PI))                 // 4 - yukarı yuvarlama

console.log(Math.min(-5, 3, 20, 4, 5, 10)) // -5 - en düşük değeri alma

console.log(Math.max(-5, 3, 20, 4, 5, 10)) // 20 -  en yüksek değeri alma

const randNum = Math.random() // 0 ile 0,999999 arasında rastgele sayı oluşturur
console.log(randNum)

// 0 ile 10 arasında rastgele bir sayı oluşturalım.

const num = Math.floor(Math.random () * 11) // 0 ile 10 arasında rastgele sayı oluşturur
console.log(num)

//Mutlak değer
console.log(Math.abs(-10))      // 10

//Kare kök
console.log(Math.sqrt(100))     // 10

console.log(Math.sqrt(2))       // 1.4142135623730951

// Üstünü Alma
console.log(Math.pow(3, 2))     // 9

console.log(Math.E)             // 2.718

// Logaritma
// E tabanı x, Math.log(x) ile doğal logaritmayı döndürür
console.log(Math.log(2))        // 0.6931471805599453
console.log(Math.log(10))       // 2.302585092994046

// Sırasıyla 2 ve 10'un doğal logaritmasını döndürür
console.log(Math.LN2)           // 0.6931471805599453
console.log(Math.LN10)          // 2.302585092994046

// Trigonometri
Math.sin(0)
Math.sin(60)

Math.cos(0)
Math.cos(60)
```

#### Random Number Generator
_Tr = Rastgele Sayı Üretimi_

JavaScript Math Object, 0 ile 0,999999999 arasında bir sayı üreten bir random() yöntemi sayı üretecine sahiptir...

```js
let randomNum = Math.random() // 0 ila 0,999 üretir...
```

Şimdi 0 ile 10 arasında rastgele bir sayı üretmek için random() yöntemini nasıl kullanabileceğimizi görelim:

```js
let randomNum = Math.random()         // 0 ila 0,999 üretir...
let numBtnZeroAndTen = randomNum * 11

console.log(numBtnZeroAndTen)         // bu verir: en az 0 ve en fazla 10,99

let randomNumRoundToFloor = Math.floor(numBtnZeroAndTen)
console.log(randomNumRoundToFloor)    //bu 0 ile 10 arasında verir
```

## Strings

Dizeler, **_single_** , **_double_**, **_back-tick_** alıntının altındaki metinlerdir. Bir dize bildirmek için bir değişken adına, atama operatörüne, tek tırnak, çift tırnak veya ters tırnaklı alıntı altındaki bir değere ihtiyacımız var.
Bazı dize örnekleri görelim:

```js
let space = ' '           // boş alan dizisi
let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'
let language = 'JavaScript'
let job = 'teacher'
let quote = "2020'de 'Görmek İnanmaktır' sözü doğru değildir."
let quotWithBackTick = `2020'de 'Görmek İnanmaktır' sözü doğru değildir.`
```

### String Concatenation
_Tr = String birleştirme_

İki veya daha fazla diziyi birbirine bağlamaya birleştirme denir.
Önceki Dize bölümünde belirtilen dizeleri kullanarak:
```js
let fullName = firstName + space + lastName; // birleştirme, iki dizeyi bir araya getirme.
console.log(fullName);
```

```sh
Asabeneh Yetayeh
```

Dizeleri farklı şekillerde birleştirebiliriz.

#### Concatenating Using Addition Operator
_Tr = Toplama Operatörünü Kullanarak Birleştirme_
Ekleme operatörünü kullanarak birleştirme eski bir yoldur.Bu birleştirme yöntemi sıkıcı ve hataya açıktır. Bu şekilde nasıl birleştirileceğini bilmek iyidir, ancak ES6 şablon dizelerini kullanmanızı şiddetle tavsiye ederim (daha sonra açıklanacaktır).
```js
// Farklı veri türlerinin farklı değişkenlerini bildirme
let space = ' '
let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'
let language = 'JavaScript'
let job = 'teacher'
let age = 250


let fullName =firstName + space + lastName //ekleme operetörü ile eklemek
let personInfoOne = fullName + '. I am ' + age + '. I live in ' + country; // ES5 dize ekleme

console.log(personInfoOne)
```

```sh
Asabeneh Yetayeh. I am 250. I live in Finland
```

#### Long Literal Strings
_Tr = Uzun Değişmez Dizeler_

Bir dize, tek bir karakter veya paragraf veya bir sayfa olabilir. Dize uzunluğu çok büyükse bir satıra sığmaz. Dizenin bir sonraki satırda devam edeceğini belirtmek için her satırın sonunda ters eğik çizgi karakterini (\\) kullanabiliriz.
**Örnek:**

```js
const paragraph = "My name is Asabeneh Yetayeh. I live in Finland, Helsinki.\
I am a teacher and I love teaching. I teach HTML, CSS, JavaScript, React, Redux, \
Node.js, Python, Data Analysis and D3.js for anyone who is interested to learn. \
In the end of 2019, I was thinking to expand my teaching and to reach \
to global audience and I started a Python challenge from November 20 - December 19.\
It was one of the most rewarding and inspiring experience.\
Now, we are in 2020. I am enjoying preparing the 30DaysOfJavaScript challenge and \
I hope you are enjoying too."

console.log(paragraph)
```

#### Escape Sequences in Strings

In JavaScript and other programming languages \ followed by some characters is an escape sequence. Let's see the most common escape characters:

- \n: Alt satıra geçer.
- \t: Boşluk bırakır
- \\\\: Ters eğik çizgi
- \\': Tek Tırnak (')
- \\": Çift Tırnak (")
  
```js
console.log('I hope everyone is enjoying the 30 Days Of JavaScript challenge.\nDo you ?') // line break
console.log('Days\tTopics\tExercises')
console.log('Day 1\t3\t5')
console.log('Day 2\t3\t5')
console.log('Day 3\t3\t5')
console.log('Day 4\t3\t5')
console.log('This is a backslash  symbol (\\)') // To write a backslash
console.log('In every programming language it starts with \"Hello, World!\"')
console.log("In every programming language it starts with \'Hello, World!\'")
console.log('The saying \'Seeing is Believing\' isn\'t correct in 2020')
```

Konsol Çıktısı:

```sh
I hope everyone is enjoying the 30 Days Of JavaScript challenge.
Do you ?
Days  Topics  Exercises
Day 1 3 5
Day 2 3 5
Day 3 3 5
Day 4 3 5
This is a backslash  symbol (\)
In every programming language it starts with "Hello, World!"
In every programming language it starts with 'Hello, World!'
The saying 'Seeing is Believing' isn't correct in 2020
```

#### Template Literals (Template Strings)
_Tr = Şablon Değişmezleri (Şablon Dizeleri)_

Bir şablon dizeleri oluşturmak için iki geri tik kullanırız. Verileri bir şablon dizesinin içine ifadeler olarak enjekte edebiliriz. Verileri enjekte etmek için, ifadeyi bir $ işareti ile başlayan bir küme parantezinin({}) içine alırız. Aşağıdaki sözdizimine bakın.

```js
//Syntax
`String literal text`
`String literal text ${expression}`
```

**Örnek: 1**

```js
console.log(`The sum of 2 and 3 is 5`)              // verileri statik olarak yazma
let a = 2
let b = 3
console.log(`The sum of ${a} and ${b} is ${a + b}`) // verileri dinamik olarak enjekte etme
```

**Örnek:2**

```js
let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'
let language = 'JavaScript'
let job = 'teacher'
let age = 250
let fullName = firstName + ' ' + lastName

let personInfoTwo = `I am ${fullName}. I am ${age}. I live in ${country}.` //ES6 - Dize enterpolasyon yöntemi
let personInfoThree = `I am ${fullName}. I live in ${city}, ${country}. I am a ${job}. I teach ${language}.`
console.log(personInfoTwo)
console.log(personInfoThree)
```

```sh
I am Asabeneh Yetayeh. I am 250. I live in Finland.
I am Asabeneh Yetayeh. I live in Helsinki, Finland. I am a teacher. I teach JavaScript.
```

Bir dize şablonu veya dize enterpolasyon yöntemi kullanarak, bir değer olabilecek ifadeler veya bazı işlemler (karşılaştırma, aritmetik işlemler, üçlü işlem) ekleyebiliriz.

```js
let a = 2
let b = 3
console.log(`${a} is greater than ${b}: ${a > b}`)
```

```sh
2 is greater than 3: false
```

### String Methods
_Tr = Dize Yöntemleri_

JavaScript'teki her şey bir nesnedir. Bir dize, ilkel bir veri türüdür, bu, oluşturulduktan sonra onu değiştiremeyeceğimiz anlamına gelir. string nesnesinin birçok string metodu vardır. Dizelerle çalışmamıza yardımcı olabilecek farklı dize yöntemleri vardır.

1. *length*: dize *length* yöntemi, boş alan içeren bir dizedeki karakter sayısını döndürür.
**Example:**

```js
let js = 'JavaScript'
console.log(js.length)         // 10
let firstName = 'Asabeneh'
console.log(firstName.length)  // 8
```

2. *Accessing characters in a string*: We can access each character in a string using its index. In programming, counting starts from 0. The first index of the string is zero, and the last index is the length of the string minus one.

  ![Accessing sting by index](../images/string_indexes.png)
  
Let us access different characters in 'JavaScript' string.

```js
let string = 'JavaScript'
let firstLetter = string[0]

console.log(firstLetter)           // J

let secondLetter = string[1]       // a
let thirdLetter = string[2]
let lastLetter = string[9]

console.log(lastLetter)            // t

let lastIndex = string.length - 1

console.log(lastIndex)  // 9
console.log(string[lastIndex])    // t
```

3. *toUpperCase()*: this method changes the string to uppercase letters.

```js
let string = 'JavaScript'

console.log(string.toUpperCase())     // JAVASCRIPT

let firstName = 'Asabeneh'

console.log(firstName.toUpperCase())  // ASABENEH

let country = 'Finland'

console.log(country.toUpperCase())    // FINLAND
```

4. *toLowerCase()*: this method changes the string to lowercase letters.

```js
let string = 'JavasCript'

console.log(string.toLowerCase())     // javascript

let firstName = 'Asabeneh'

console.log(firstName.toLowerCase())  // asabeneh

let country = 'Finland'

console.log(country.toLowerCase())   // finland
```

5. *substr()*: It takes two arguments, the starting index and number of characters to slice.

```js
let string = 'JavaScript'
console.log(string.substr(4,6))    // Script

let country = 'Finland'
console.log(country.substr(3, 4))   // land
```

6. *substring()*: It takes two arguments, the starting index and the stopping index but it doesn't include the character at the stopping index.

```js
let string = 'JavaScript'

console.log(string.substring(0,4))     // Java
console.log(string.substring(4,10))    // Script
console.log(string.substring(4))       // Script

let country = 'Finland'

console.log(country.substring(0, 3))   // Fin
console.log(country.substring(3, 7))   // land
console.log(country.substring(3))      // land
```

7. *split()*: The split method splits a string at a specified place.

```js
let string = '30 Days Of JavaScript'

console.log(string.split())     // Changes to an array -> ["30 Days Of JavaScript"]
console.log(string.split(' '))  // Split to an array at space -> ["30", "Days", "Of", "JavaScript"]

let firstName = 'Asabeneh'

console.log(firstName.split())    // Change to an array - > ["Asabeneh"]
console.log(firstName.split(''))  // Split to an array at each letter ->  ["A", "s", "a", "b", "e", "n", "e", "h"]

let countries = 'Finland, Sweden, Norway, Denmark, and Iceland'

console.log(countries.split(','))  // split to any array at comma -> ["Finland", " Sweden", " Norway", " Denmark", " and Iceland"]
console.log(countries.split(', ')) //  ["Finland", "Sweden", "Norway", "Denmark", "and Iceland"]
```

8. *trim()*: Removes trailing space in the beginning or the end of a string.

```js
let string = '   30 Days Of JavaScript   '

console.log(string)
console.log(string.trim(' '))

let firstName = ' Asabeneh '

console.log(firstName)
console.log(firstName.trim())  // still removes spaces at the beginning and the end of the string
```

```sh
   30 Days Of JavasCript   
30 Days Of JavasCript
  Asabeneh 
Asabeneh
```

9. *includes()*: It takes a substring argument and it checks if substring argument exists in the string. *includes()* returns a boolean. If a substring exist in a string, it returns true, otherwise it returns false.

```js
let string = '30 Days Of JavaScript'

console.log(string.includes('Days'))     // true
console.log(string.includes('days'))     // false - it is case sensitive!
console.log(string.includes('Script'))   // true
console.log(string.includes('script'))   // false
console.log(string.includes('java'))     // false
console.log(string.includes('Java'))     // true

let country = 'Finland'

console.log(country.includes('fin'))     // false
console.log(country.includes('Fin'))     // true
console.log(country.includes('land'))    // true
console.log(country.includes('Land'))    // false
```

10. *replace()*: takes as a parameter the old substring and a new substring.

```js
string.replace(oldsubstring, newsubstring)
```

```js
let string = '30 Days Of JavaScript'
console.log(string.replace('JavaScript', 'Python')) // 30 Days Of Python

let country = 'Finland'
console.log(country.replace('Fin', 'Noman'))       // Nomanland
```

11. *charAt()*: Takes index and it returns the value at that index

```js
string.charAt(index)
```

```js
let string = '30 Days Of JavaScript'
console.log(string.charAt(0))        // 3

let lastIndex = string.length - 1
console.log(string.charAt(lastIndex)) // t
```

12. *charCodeAt()*: Takes index and it returns char code (ASCII number) of the value at that index

```js
string.charCodeAt(index)
```

```js
let string = '30 Days Of JavaScript'
console.log(string.charCodeAt(3))        // D ASCII number is 68

let lastIndex = string.length - 1
console.log(string.charCodeAt(lastIndex)) // t ASCII is 116

```

13.  *indexOf()*: Takes a substring and if the substring exists in a string it returns the first position of the substring if does not exist it returns -1

```js
string.indexOf(substring)
```

```js
let string = '30 Days Of JavaScript'

console.log(string.indexOf('D'))          // 3
console.log(string.indexOf('Days'))       // 3
console.log(string.indexOf('days'))       // -1
console.log(string.indexOf('a'))          // 4
console.log(string.indexOf('JavaScript')) // 11
console.log(string.indexOf('Script'))     //15
console.log(string.indexOf('script'))     // -1
```

14.  *lastIndexOf()*: Takes a substring and if the substring exists in a string it returns the last position of the substring if it does not exist it returns -1


```js
//syntax
string.lastIndexOf(substring)
```

```js
let string = 'I love JavaScript. If you do not love JavaScript what else can you love.'

console.log(string.lastIndexOf('love'))       // 67
console.log(string.lastIndexOf('you'))        // 63
console.log(string.lastIndexOf('JavaScript')) // 38
```

15. *concat()*: it takes many substrings and joins them.

```js
string.concat(substring, substring, substring)
```

```js
let string = '30'
console.log(string.concat("Days", "Of", "JavaScript")) // 30DaysOfJavaScript

let country = 'Fin'
console.log(country.concat("land")) // Finland
```

16. *startsWith*: it takes a substring as an argument and it checks if the string starts with that specified substring. It returns a boolean(true or false).

```js
//syntax
string.startsWith(substring)
```

```js
let string = 'Love is the best to in this world'

console.log(string.startsWith('Love'))   // true
console.log(string.startsWith('love'))   // false
console.log(string.startsWith('world'))  // false

let country = 'Finland'

console.log(country.startsWith('Fin'))   // true
console.log(country.startsWith('fin'))   // false
console.log(country.startsWith('land'))  //  false
```

17. *endsWith*: it takes a substring as an argument and it checks if the string ends with that specified substring. It returns a boolean(true or false).

```js
string.endsWith(substring)
```

```js
let string = 'Love is the most powerful feeling in the world'

console.log(string.endsWith('world'))         // true
console.log(string.endsWith('love'))          // false
console.log(string.endsWith('in the world')) // true

let country = 'Finland'

console.log(country.endsWith('land'))         // true
console.log(country.endsWith('fin'))          // false
console.log(country.endsWith('Fin'))          //  false
```

18. *search*: it takes a substring as an argument and it returns the index of the first match. The search value can be a string or  a regular expression pattern.

```js
string.search(substring)
```

```js
let string = 'I love JavaScript. If you do not love JavaScript what else can you love.'
console.log(string.search('love'))          // 2
console.log(string.search(/javascript/gi))  // 7
```

19. *match*: it takes a substring or regular expression pattern as an argument and it returns an array if there is match if not it returns null. Let us see how a regular expression pattern looks like. It starts with / sign and ends with / sign.

```js
let string = 'love'
let patternOne = /love/     // with out any flag
let patternTwo = /love/gi   // g-means to search in the whole text, i - case insensitive
```

Match syntax

```js
// syntax
string.match(substring)
```

```js
let string = 'I love JavaScript. If you do not love JavaScript what else can you love.'
console.log(string.match('love'))
```

```sh
["love", index: 2, input: "I love JavaScript. If you do not love JavaScript what else can you love.", groups: undefined]
```

```js
let pattern = /love/gi
console.log(string.match(pattern))   // ["love", "love", "love"]
```

Let us extract numbers from text using a regular expression. This is not the regular expression section, do not panic! We will cover regular expressions later on.

```js
let txt = 'In 2019, I ran 30 Days of Python. Now, in 2020 I am super exited to start this challenge'
let regEx = /\d+/

// d with escape character means d not a normal d instead acts a digit
// + means one or more digit numbers,
// if there is g after that it means global, search everywhere.

console.log(txt.match(regEx))  // ["2", "0", "1", "9", "3", "0", "2", "0", "2", "0"]
console.log(txt.match(/\d+/g)) // ["2019", "30", "2020"]
```

20. *repeat()*: it takes a number as argument and it returns the repeated version of the string.

```js
string.repeat(n)
```

```js
let string = 'love'
console.log(string.repeat(10)) // lovelovelovelovelovelovelovelovelovelove
```

## Checking Data Types and Casting

### Checking Data Types

To check the data type of a certain variable we use the _typeof_ method.

**Example:**

```js
// Different javascript data types
// Let's declare different data types

let firstName = 'Asabeneh'      // string
let lastName = 'Yetayeh'        // string
let country = 'Finland'         // string
let city = 'Helsinki'           // string
let age = 250                   // number, it is not my real age, do not worry about it
let job                         // undefined, because a value was not assigned

console.log(typeof 'Asabeneh')  // string
console.log(typeof firstName)   // string
console.log(typeof 10)          // number
console.log(typeof 3.14)        // number
console.log(typeof true)        // boolean
console.log(typeof false)       // boolean
console.log(typeof NaN)         // number
console.log(typeof job)         // undefined
console.log(typeof undefined)   // undefined
console.log(typeof null)        // object
```

### Changing Data Type (Casting)

- Casting: Converting one data type to another data type. We use _parseInt()_, _parseFloat()_, _Number()_, _+ sign_, _str()_
  When we do arithmetic operations string numbers should be first converted to integer or float if not it returns an error.

#### String to Int

We can convert string number to a number. Any number inside a quote is a string number. An example of a string number: '10', '5', etc.
We can convert string to number using the following methods:

- parseInt()
- Number()
- Plus sign(+)

```js
let num = '10'
let numInt = parseInt(num)
console.log(numInt) // 10
```

```js
let num = '10'
let numInt = Number(num)

console.log(numInt) // 10
```

```js
let num = '10'
let numInt = +num

console.log(numInt) // 10
```

#### String to Float

We can convert string float number to a float number. Any float number inside a quote is a string float number. An example of a string float number: '9.81', '3.14', '1.44', etc.
We can convert string float to number using the following methods:

- parseFloat()
- Number()
- Plus sign(+)

```js
let num = '9.81'
let numFloat = parseFloat(num)

console.log(numFloat) // 9.81
```

```js
let num = '9.81'
let numFloat = Number(num)

console.log(numFloat) // 9.81
```

```js
let num = '9.81'
let numFloat = +num

console.log(numFloat) // 9.81
```

#### Float to Int

We can convert float numbers to integers.
We use the following method to convert float to int:

- parseInt()
  
```js
let num = 9.81
let numInt = parseInt(num)

console.log(numInt) // 9
```

🌕  You are awesome. You have just completed day 2 challenges and you are two steps ahead on your way to greatness. Now do some exercises for your brain and for your muscle.  

## 💻 Day 2: Exercises

### Exercise: Level 1

1. Declare a variable named challenge and assign it to an initial value **'30 Days Of JavaScript'**.
2. Print the string on the browser console using __console.log()__
3. Print the __length__ of the string on the browser console using _console.log()_
4. Change all the string characters to capital letters using __toUpperCase()__ method
5. Change all the string characters to lowercase letters using __toLowerCase()__ method
6. Cut (slice) out the first word of the string using __substr()__ or __substring()__ method
7. Slice out the phrase *Days Of JavaScript* from *30 Days Of JavaScript*.
8. Check if the string contains a word __Script__ using __includes()__ method
9. Split the __string__ into an __array__ using __split()__ method
10. Split the string 30 Days Of JavaScript at the space using __split()__ method
11. 'Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon' __split__ the string at the comma and change it to an array.
12. Change 30 Days Of JavaScript to 30 Days Of Python using __replace()__ method.
13. What is character at index 15 in '30 Days Of JavaScript' string? Use __charAt()__ method.
14. What is the character code of J in '30 Days Of JavaScript' string using __charCodeAt()__
15. Use __indexOf__ to determine the position of the first occurrence of __a__ in 30 Days Of JavaScript
16. Use __lastIndexOf__ to determine the position of the last occurrence of __a__ in 30 Days Of JavaScript.
17. Use __indexOf__ to find the position of the first occurrence of the word __because__ in the following sentence:__'You cannot end a sentence with because because because is a conjunction'__
18. Use __lastIndexOf__ to find the position of the last occurrence of the word __because__ in the following sentence:__'You cannot end a sentence with because because because is a conjunction'__
19. Use __search__ to find the position of the first occurrence of the word __because__ in the following sentence:__'You cannot end a sentence with because because because is a conjunction'__
20. Use __trim()__ to remove any trailing whitespace at the beginning and the end of a string.E.g ' 30 Days Of JavaScript '.
21. Use __startsWith()__ method with the string *30 Days Of JavaScript* and make the result true
22. Use __endsWith()__ method with the string *30 Days Of JavaScript* and make the result true
23. Use __match()__ method to find all the __a__’s in 30 Days Of JavaScript
24. Use __concat()__ and merge '30 Days of' and 'JavaScript' to a single string, '30 Days Of JavaScript'
25. Use __repeat()__ method to print 30 Days Of JavaScript 2 times

### Exercise: Level 2

1. Using console.log() print out the following statement:

    ```sh
    The quote 'There is no exercise better for the heart than reaching down and lifting people up.' by John Holmes teaches us to help one another.
    ```

2. Using console.log() print out the following quote by Mother Teresa:

    ```sh
    "Love is not patronizing and charity isn't about pity, it is about love. Charity and love are the same -- with charity you give love, so don't just give money but reach out your hand instead."
    ```

3. Check if typeof '10' is exactly equal to 10. If not make it exactly equal.
4. Check if parseFloat('9.8') is equal to 10 if not make it exactly equal with 10.
5. Check if 'on' is found in both python and jargon
6. _I hope this course is not full of jargon_. Check if _jargon_ is in the sentence.
7. Generate a random number between 0 and 100 inclusively.
8. Generate a random number between 50 and 100 inclusively.
9. Generate a random number between 0 and 255 inclusively.
10. Access the 'JavaScript' string characters using a random number.
11. Use console.log() and escape characters to print the following pattern.

    ```js
    1 1 1 1 1
    2 1 2 4 8
    3 1 3 9 27
    4 1 4 16 64
    5 1 5 25 125
    ```

12.  Use __substr__ to slice out the phrase __because because because__ from the following sentence:__'You cannot end a sentence with because because because is a conjunction'__

### Exercises: Level 3

1. 'Love is the best thing in this world. Some found their love and some are still looking for their love.' Count the number of word __love__ in this sentence.
2. Use __match()__ to count the number of all __because__ in the following sentence:__'You cannot end a sentence with because because because is a conjunction'__
3. Clean the following text and find the most frequent word (hint, use replace and regular expressions).

    ```js
        const sentence = '%I $am@% a %tea@cher%, &and& I lo%#ve %te@a@ching%;. The@re $is no@th@ing; &as& mo@re rewarding as educa@ting &and& @emp%o@weri@ng peo@ple. ;I found tea@ching m%o@re interesting tha@n any ot#her %jo@bs. %Do@es thi%s mo@tiv#ate yo@u to be a tea@cher!? %Th#is 30#Days&OfJavaScript &is al@so $the $resu@lt of &love& of tea&ching'
    ```

4. Calculate the total annual income of the person by extracting the numbers from the following text. 'He earns 5000 euro from salary per month, 10000 euro annual bonus, 15000 euro online courses per month.'

🎉 CONGRATULATIONS ! 🎉

[<< Day 1](../readMe.md) | [Day 3 >>](../03_Day_Booleans_operators_date/03_booleans_operators_date.md)
