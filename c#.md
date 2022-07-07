# C# Notları
## Giriş
* Konsol Çıktısı Almak
```c#
Console.WriteLine("Hello World!");
Console.Write("Hello World!");
```
* Konsol çıktısı alırken değişkenler kullanılacaksa şu şekilde kolaylık sağlanabilir:
```c#
Console.WriteLine($"Sonuç: {num1} + {num2 = }" + sonuc);
```
*c'ye basıp 2 kere tab'a basarsan otomatik **WriteLine** Açar*
* Yorum Satırı
```c#
//Bu bir yorum satırıdır
/*Bu
 *bir
 *yorum
 *paragrafıdır
 */
```
* Boşluk Bırakmak
```c#
\b backspace
\n yeni satır
\t tab
```
* Alttaki Çerçöpü Gizlemek
*Kodun sonuna:*
```c#
Console.ReadKey();
```
## Değişkenler
* Değişken Tipleri
```c#
char x = "a";
string y = "Kuti";
bool z = true;
int f = 3;
```
* Değişkenler değer atanmadan da tanımlanabilir (declaration)
```c#
int x;
string y;
bool z;
```
* Sayı depolarken; int, sadece tam sayıları tutar; double, ondalıklı sayıları da tutar.
* *Char* tek karakter tutabilir.
* Değişkenlerin daha sonra değiştirilmesini istemiyorsak *constant* olarak tanımlanabilir. Bunu *const* ile sağlayabilir.
```c#
const double pi = 3.141;
```
* Bir data tipinin başka bir data'ya dönüştürülmesi casting kullanılarak yapılabilir.
```c#
double a = 3,14;
int b = Convert.ToInt32(a);
int c = Convert.ToString(a);
int d = Convert.ToDouble(a);
...
```
* Bir değişkenin data tipinin ne olduğunu bulmak için *GetType()* fonksiyonu kullanılır. Aşağıdaki fonksiyon b değişkeninin tipini çıktı olarak verir.
```c#
Console.WriteLine(b.GetType());
```
* Kullanıcıdan bilgi almak
```c#
String isim = Console.ReadLine();
```
## Matematiksel İşlemler
* Bir değişkeni 1 arttırmanın 3 yolu:
```c#
elma = elma + 1;
elma += 1;
elma++
```
* Bölme işleminden kalanı veren fonksiyon: (elmanın 2'ye bölümünden kalanı verir)
```c#
int kalan = elma % 2;
```
* Math kütüphanesi bir çok matematiksel işlem için kullanılabilir.
* Bir sayının üstünü almak:
```c#
double x = 3;
double a = Math.Pow(x,2);
```
Çıktı olarak 3'ün karesi olan 9'u alırız.
* Bir sayının karekökünü almak:
```c#
double x = 3;
double b = Math.Sqrt(x);
```
* Bir sayının mutlak değerini almak:
```c#
double x = -3;
double c = Math.Abs(x);
```
* Bir sayıyı yuvarlamak: (Sırasıyla önce en yakın tam sayıya, sonra bir üste, son olarak bir alta yuvarlar)
```c#
double x = 3,14:
double d = Math.Round(x);
double e = Math.Ceiling(x);
double f = Math.Floor(x);
```
* 2 sayı arasında hangisinin daha büyük/küçük olduğunu bulmak:
```c#
double x = 4;
double y = 5;
double g = Math.Min(x,y);
double h = Math.Max(x,y);
```
* Random sayı oluşturmak
```c#
Random random = new Random();
int rastgele = random.Next();
```
Eğer sınır belirlenmezse bu fonksiyon integer'ın sınırı kadar yani 2 milyar küsüre kadar değer alabilir. Sınır belirlemek için:
```c#
Random random = new Random();
int rastgele = random.Next(1,7)
```
**Bu bize 1 ile 6 ARASINDA bir sayı verir**
* Ondalıklı sayı oluşturmak istiyorsak:(**0 ile 1 arasında**)
```c#
Random random = new Random();
double num = random.NextDouble();
```
## String Methodları
* String'in tüm harflerini büyütmek için:
```c#
String fullName = "Kutay Şahin";
fullName = fullName.ToUpper();
```
* String'in tüm harflerini küçültmek için:
```c#
String fullName = "Kutay Şahin"
fullName = fullName.ToLower();
```
* Bir String'deki tüm x'leri y'lere çevirmek:
```c#
degistir = degistir.Replace("x","y");
```
* Insert methodu kullanarak bir String'e istenilen karakter eklenebilir.
```c#
String userName = userName.Insert(0, "Mr.");
```
*İsmin önüne "Mr." ön ekinin gelmesini sağlar*

**Property'ler kullanılırken parantez açıp kapatılmaz. Parantez açıp kapatma olayı Methodlarda kullanılır**

* String'in uzunluğunu bulmak:
```c#
fullName.Length;
```
* Bir String'i kullanarak yeni alt String'ler oluşturma: (*İlk değer bölünmenin yapılacağı index'i, 2. değer o konumdan sonraki kaç karakterin dahil edileceğini gösterir. "Kutay Şahin" örneği için ayırmak istersek:*)
```c#
String firstName = fullName.Substring(0,5);
String lastName = fullName.Substring(6,5);
```
## Mantıksal Operatörler
* Ve
```c#
&&
```
* Veya
```c#
||
```
## If, While, For ve Diğer Döngüler
* If ifadesi, karar vermenin en basit formudur. Şart tanımlar.
* Örnek if modeli(*18 yaş denetleme koşulu:*)
```c#
if (yas >= 18){
    Console.WriteLine("18'den büyüksün")
}
else if(yas < 0){
    Console.WriteLine("Sen daha doğmadın")
}
else{
    Console.WriteLine("18'den küçüksün")
}
```
***Bir If ifadesinin okunma sırası yukarıdan aşağı doğru olduğu için eğer tanımlanmış olan bir koşul sağlanırsa o parantezin içerisindeki işlemler yapılır ve If'in kalanı okunmadan program kaldığı yerden devam eder. Koşullar bu unutulmadan belirlenmelidir.***
* Eşitlik koşulunun sağlanıp sağlanamdığı kontrol edilirken eşittir 2 kere kullanılır. Aksi takdirde c# atama yapmaya çalıştığımızı düşünür.
* Switch-case bazı durumlarda if-else'e göre daha verimlidir ve okumayı kolaylaştırır. Birden fazla seçenek olduğunda switch-case kullanmak daha mantıklıdır.
```c#
Console.writeline("Budün günlerden ne?");
String gun = Console.ReadLine();

switch (gun){
    case "pazartesi":
        Console.WriteLine("Bugün pazartesi");
        break;
    case "salı":
        Console.WriteLine("Bugün salı");
        break;
    default:
        Console.WriteLine(gun + " bir gün değildir.")
        break;
    ...
}
```
* Switch-case'lerde default durum kullanılarak koşullar harici bir durum oluşursa ne olacağı tanımlanabilir.
* While kullanımı
```c#
String isim = Console.ReadLine();

while (isim == ""){
    Console.WriteLine("İsminizi giriniz:");
    isim = Console.ReadLine();
}
```
* While döngüleri sınırsız kere tekrar eden, for döngüleri sınırlı kere tekrar eden döngülerdir.
* For kullanırken parantez içinde sırasıyla for *(sayaç indeksi; bitiş şartı; indeks değişimi)* yazılır.
* For kullanımı
```c#
for (int i = 1; i <= 10; i++){
    Console.WriteLine(i);
}
```
* **Nested Loop**, iç içe birden fazla döngünün yer aldığı döngülere verilen addır. Sıralama problemlerinde çokça kullanılır.
* ***User Input HER ZAMAN String'dir. Dolayısıyla işlemlerde kullanmak için Convert.ToInt32() yapılmalıdır.***
* Nested Loop kullanımı:
```c#
Console.Write("Kaç satır olsun?");
int satir = Convert.ToInt32(Console.ReadLine());

Console.Write("Kaç sütun olsun?");
int sutun = Convert.ToInt32(Console.ReadLine());

Console.Write("Hangi sembol kullanılsın?");
String sembol = Console.Readline();

for (int i = 0; i < satir; i++){
    for (int j = 0; j < sutun; j++){
        Console.Write(symbol);
    }
    Console.WriteLine();
}
```
* Do-While döngüsünde Do başa yazılır, ilgili parantez 1 kere çalıştırılır, parantezin sonunda while koşulunun sağlanıp sağlanmadığına göre fonksiyon tekrar edilir.
```c#
do{
    işlemler
    ...
}while(Console.ReadLine().ToUpper() == "Y");
```
## Diziler
* **Dizi**: birden fazla değer içerebilen değişken. ***Boyutu sabittir.***
* ***Her zaman 0. indexten başlanır.*** Dizinin birinci elemanı i=0'dır.
```c#
String[] arabalar = {"BMW", "Mercedes", "Corvette"};

Console.WriteLine(arabalar[0]);
```
* Dizideki değerlerden biri değiştirilecekse index numarasıyla beraber değiştirilir.
```c#
cars[0] = "Tesla";
```
* Bir dizideki elemanları for döngüsü ile yazdırmak
```c#
for (int i = 0; i < cars.Length; i++){
    Console.WriteLine(cars[i]);
}
```
* Boş dizi tanımlamak: (*örnekte 3 boyutunda bir string dizisi tanımlanıyor*)
```c#
String[] cars = new String[3];
```
* Foreach döngüsü: Dizilerle işlem yaparken for döngüsüne göre daha pratiktir. For'a göre daha az esnek.
```c#
String[] cars = {"BMW","Mercedes","Ferrari"};

foreach (String car in cars){
    Console.WriteLine.(car);
}
```
## Methodlar
* Method: Çağrıldığında bir kod bölümünün çalıştırır. Aynı kodu birden fazla kez yazmaya gerek kalmadan çıktı almayı sağlar. Methodu çağırma işlemine "invoke" denir.
```c#
static void sarkiSoyle(){
    Console.WriteLine("İyi kidoğdun")
    Console.WriteLine("Kutay Bey")
}
```
**Bu örnekte sarkiSoyle() methodu her çağrıldığında 2 satırlık çıktıyı alırız.**
* Main methodunda tanımlanmış olan değişkenler tanımlanan methodun içinden erişilemez. Bir method invoke edilecekken argument belirterek methodun içine gönderilecek değişkenler tanımlanır.

* Parametre: Method'un invoke'lanması için gereken şeyler
```c#
{
String isim = Kutay;
int yas = 22;
sarkiSoyle(isim, yas);
}

static void sarkiSoyle(String dgCocugu, int yasi){
    Console.WriteLine("İyi ki doğdun " + isim + yas);
}
```
* Eğer methoddan çıktı alınacaksa methodun sonuna ***return*** yazılmalı ve method tanımlanırken void olarak değil de hangi türde çıktı alınacaksa o türe uygun tanımlanmalı. (**örneğin**)
```c#
static double Carpim(double x, double y){
    double z = x* y;
    return z;
}
```
* ReadLine çıktısı alınan bilgiyi her zaman String olarak depolar. Sayısal değere çevirmek için *Convert.ToDouble()* fonksiyonu kullanılmalıdır. 
```c#
Console.WriteLine("1. sayıyı giriniz:")
x = Convert.ToDouble(Console.ReadLine());
```
* Method Overload: Methodlar aynı ismi paylaşsa dahi farklı parametreler kullanarak farklı işlemler yapabilirler. Bir method ismi farklı parametreler içeren methodlar tanımlamak için kullanılırsa buna *Method Overloading* denir.
* Kaç adet data girişinin gerçekleşeceğinin bilinmediği durumlarda ***params*** keyword'ünden yararlanılır. Bir dizi parametre alabilir. Tek boyutlu bir dizidir.
```c#
static double Sepet(params double[] fiyatlar){
    double toplam = 0;
    foreach(double fiyat in fiyatlar){
        toplam += fiyat;
    }
}
```
## Exception Handling
* Programın çalışması esnasında oluşabilecek hatalarda programın sonlanması yerine hata türüne göre geribildirim verebilmemizi sağlayan fonksiyonlar.
* Ne bunlar?
    *try:* tehlikeli oalbilecek kodu dener
    *catch:* hatalar oluştuğu anda onları yakalar ve ilgili durumla başa çıkar
    *finally:* hata olmasa dahi her zaman çalışır
```c#
try{
    *riskli şeyler*
}
catch (FormatException e){
    Console.WriteLine("Sadece sayı gir!");
}
catch (DivideByZeroException e){
    Console.WriteLine("Sayı 0'a bölünür mü mal?");
}
catch (Exception e){
    Console.WriteLine("Bir şeyler yanlış gitti ama biz de bilmiyoruz");
}
finally{
    Console.WriteLine("İyi günler!")
}
```
## Conditional Operator
* Conditional Operator: Bir şartın true/false olmasına bağlı olarak atama yapılacalsa kullanılır. Şart sağlanırsa x yapılır, sağlanmazsa y yapılır.
```c#
(condition) ? x : y
```
* If ve Conditional Operator'ün karşılaştırmalı kullanımı:
```c#
double temperature = 20;
String message;

if(temperature >= 15){
    message = "Sıcak";
}
else{
    message = "Soğuk";
}
---

message = (temperature >= 15) ? "Sıcak" : "Soğuk";

```
## String Interpolation
* String sabitlerinin içerisine değişkenler atamamızı sağlar. String başlamadan önce konulan $ işareti ile kullanılır. Stringin içerisine değişkenin ekleneceği kısımlarda değişken adı {} parantezlerinin içerisine alınarak yazılır.
```c#
Console.WriteLine($"Merhaba {isim}, bugün {yas} yaşındasın.");
```
* String Interpolation sırasında değişken isminden sonra virgül kullanılarak değişkenden sonra istenilen sayıda boşluk bırakılabilir.
```c#
Console.WriteLine($"Merhaba {isim, 10}");
//isimden önce 10 boşluk bırakılır, isimden sonra boşluk bırakılmak istenirse "-10" yazılarak yapılabilir.
```
## Çok Boyutlu Diziler(Matrisler)
* Yatay ve dikey olarak her yön 0 indexinden başlar, her bir satır virgülle ayrılarak yazılır.
```c#
String[,] parkNo = {{"1","2","3"},
                    {"4","5","6"},
                    {"7","8","9"}
                    };
//Böyle yazılmasına gerek yoktu ancak okuma kolaylığı açısından tab kullanarak bu şekilde yazmak daha faydalı.
//Herhangi bir index'e ulaşmak için:
parkNo[0, 2] = 123;
//3 değişkenini 123 yaptık
```
* Bir multidimensional array'i dizi gibi düzenli şekilde yazdırmak istiyorsak *Nested Loop* kullanırız.
```c#
for(int i = 0; i < parkNo.GetLenght(0); i++){
    for(int j = 0; j < parkNo.GetLenght(1); j++){

        Console.Write(parkNo[i, j] + " ");
    }
    Console.WriteLine();
}
// Burada GetLenght fonksiyonunun içerisindeki 0 satırı, 1 ise sütunu ifade eder
/* Alacağımız çıktı şöyle olur:
    1 2 3
    4 5 6
    7 8 9
*/
```
## Class'lar
* Class'lar birbiriyle bağlantılı bir grup kodu depolamak için kullanılır. Örneğin c#'ın içerisinde yer alan Math class'ı birçok farklı matematiksel işlemi methodlar yardımıyla çözmeyi sağlar. (*Örneğin başka bir c# dosyasında tanımlanan Mesajlar isimli bir Class oluşturup bunu daha sonra farklı bir c# dosyasında çağıralım*)
```c#
//Class'ı oluşturma:
static class Mesajlar{
    public static void Merhaba(){
        Console.WriteLine("Merhaba! Hoş geldin.");
    }
    public static void Bye(){
        Console.WriteLine("Bye, tekrar bekleriz.");
    }
}
//Main programı içinde kullanma:
Mesajlar.Merhaba();
Mesajlar.Bye();
```
## OOP
* Instance: Bir Class'tan türetilen nesnedir. Örneğin:
```c#
Form1 frm = new Form1();
// Burada frm nesnesi Form1 sınıfının instance'ıdır.
```
* Bir Class, objelerin oluşturulmasında blueprint görevi görebilir.
* Objelerin field ve methodları yani karakteristik özellikleri ve aksiyonları olabilir.
```c#
class Insan{
    public String isim;
    public int yas;

    public void Ye(){
        Console.WriteLine(isim + "yemek yiyor")
    }

    public void Uyu(){
        Console.WriteLine(isim + "uyuyor")
    }
}
 // Başka Class'ta kullanacak olursak:
class Program{
    Insan yakisikli = new Insan();
    yakisikli.isim = "Kutay";
    yakisikli.yas = 22;

    yakisikli.Ye();
    yakisikli.Uyu();
}
```
* Field, objenin sahip olduğu özellikler; Method, objenin yapabildiği şeylerdir.
* Class'lar objelerin blueprint'i olarak kullanılan şeylerdir.
## Constructors
* Bir sınıfta yer alan özel bir method. Class adıyla aynı adı taşır. Obje oluşturulurken argümanları alanlara atamak için kullanılabilir.
```c#
class Insan{
    public Insan(String isim, int yas){
        this.isim = isim;
        this.yas = yas;
    }
}

class Program{
    Insan insan1 = new Insan("Kutay", 22);
}
```
* Static modifier: bir class'taki özelliklerin o classtaki özel methodların her biri için değil de class'a ait genel bir özellik olmasını sağlar.
* Static olan özellik Class'a aittir. Objeler onu kendine alamaz.
* Overloaded constructor'lar kullanılarak farklı parametreler içeren benzer constructor'lar oluşturulabilir.
## Inheritance
* Class'ların birbirlerine parent-child ilişkileri sayesinde özellik aktarabilmesini sağlar.
```c#
class Arac{
    public int hiz = 0;

    public void go(){
        Console.WriteLine("Araç hareket ediyor.")
    }
}

class Araba : Arac{
    public int tekerler = 4;
}
class Bisiklet : Arac{
    public int tekerler = 2;
}

Main{
    Araba araba1 = new Araba();
    Console.WriteLine(araba.hiz);
    Console.WriteLine(araba.tekerler)
    Araba.go();
}

// Araba ve bisikler Araç classının child'i olduğu için her ikisinde de "hiz" değişkeni vardır ve her ikisi de go() methodunu kullanabilir.
```
* Bir class'ın başka bir yerde 0'dan bir obje olarak oluşturulmasının istenmediği durumlarda (yukarıdaki örnekte yer alan Arac class'ı gibi) **Abstract Class**'lar kullanılır. Bu özelliği taşıyan class'lar başka bir yerde generatelenemez. Bu programın güvenliğini arttırır.
* Property ve methodlar da Abstract özelliği taşıyabilir.
* **Objelerden dizi oluşturmak:** normalde diziler tanımlanırken "String[]" şeklinde tanımlanmaya başlanırdı. Objelerle bir dizi oluşturulacaksa da bu objenin türü String'in yerini alır.
```c#
Araba[] garaj = new Araba[3];
// Buradaki 3 dizinin boyutunu temsil eder.
Araba araba1 = new Araba("Lamborghini")
garaj[0] = araba1;
```
## Method Overriding
* Parent Class'ta tanımlanıp, daha sonra Child Class'ta tekrar tanımlanan Methodlar; Child Class'ta tekrar tanımlanan özelliği gösterir. Aynı methodun Child Class'ta aynı isimde, farklı özellikleri olan bir Method ile tanımlanması olayına *Method Overriding* denir.
* Override yapılabilmesi için **miras alınan** Method'un virtual, abstract veya halihazırda override yapılmış olması lazım.
* **Abstract method kullanılacaksa class'ın da abstract olması ve method'un body'sinin olmaması lazım.**
* kullanılışı: *public override void ...*
```c#
class Animal{
    public virtual void Speak(){
        Console.WriteLine("Hayvan brr der")
    }
}
class Dog : Animal{
    public override void Speak(){
        Console.WriteLine("Köpek hav hav der")
    }
}
class Cat : Animal{
    public override void Speak(){
        Console.WriteLine("Kedi miyav der")
    }
}
```
* Method Overriding genelde *ToString()* methoduyla ve polymorphism ile birlikte kullanılır.

## ToString() Methodu
* Objects methodundan kalıtılmış bir özelliktir.
* Bir objenin görüntülenmeye uygun olması için onu String gösterimine çevirir.
* ToString() methodu normalde namespace'i ve çalışılan objeyi çıktı olarak verir fakat override yaparak daha güzel bir String çıktısı alınabilir.
```c#
main(){
    Console.WriteLine(Araba.ToString());
}
public override string ToString(){
    return "Bu " + yil + " model bir araba"
}
```
* Polymorphism'de objeler birden fazla tiple tanımlanabilir. 

## Interface
* İlgili class'tan miras alan tüm diğer class'ların uyması gereken birtakım "contract"ler tanımlar.
* Method'lar IMehmet IAhmet gibi başına "I" konularak isimlendirillir.
* Method'lar tanımlanır ancak tanımlandığı yerde implement edilmez. Onu çağıran class'ta implement edilir.
```c#
main{
    Hawk kartal = new Hawk();
    kartal.Hunt();
}
interface IPredator{
    void Hunt();
}
class Hawk : IPredator{
    public void Hunt(){
        Console.WriteLine("Kartal avlanıyor")
    }
}
// Bir class 1den farklı class'tan miras alabilir. örneğin bir balık hem av hem de avcıdır. Bu durumda ilgili class tanımlanırken miras alacağı class'lar virgülle ayrılarak tanımlanır.
class Fish : IPredator, IPrey{
    public void Flee(){
        ...
    }
    public void Hunt(){
        ...
    }
}
```
* **Interface, class'ın sahip olması gereken özellikleri belirler.**
* **Miras alan class, interface'den aldığı özellikleri nasıl kullanacağını belirler.**

## Lists
* Array'ler dinamik olarak boyut değiştiremezken listelerin boyutu tanımlandıktan sonra da değiştirilebilir.
* Kullanılacağı zaman *using System.Collections.Generic;* ile ilgili kütüphane eklenir.
```c#
List<String> hayvanlar = new List<String>();

hayvanlar.Add("köpek");
hayvanlar.Add("kedi");
//bir indexe ulaşmak
Console.WriteLine(hayvanlar[0]); //köpek çıktısı aldık
//bir item'ı çıkarmak
hayvanlar.Remove("köpek");
//bir item'ı özel bir konuma eklemek
hayvanlar.Insert(0, "mamut");
//list boyutunu görmek
hayvanlar.Count;
//bir item'ın index numarasını bulmak
Console.WriteLine(food.IndexOf("kedi"));
//bir item'ın listede olup olmadığını veren bool method
hayvanlar.Contains("mamut");// True/False çıktı verir
//list'i alfabetik sıralamak
hayvanlar.Sort();
//list'i ters sıralamak
hayvanlar.Reverse();
//list'i temizlemek
hayvanlar.Clear();
//list'i array'a çevirmek
String [] hayvanlarArray = hayvanlar.ToArray();
//list'e obje eklemek
List<Hayvan> hayvanlar = new List<Hayvan>();
```
## Getters & Setters
* Encapsulation yardımıyla güvenliği arttıran erişim methodlarıdır.
* Property: Fieldlar ve methodların özelliklerini birlikte kullanmayı sağlarlar. İlgili field'la aynı adı taşırlar. Tek farkı ilk harfinin büyük olmasıdır.
* get accessor: property'nin değerini almayı sağlar.
* set accessor: property'nin değerini değiştirmeyi sağlar.
* value: set accessor'unun atama yapacağı değer
```c#
class Car{
    private int speed;
    public Car(int speed){
        Speed = speed;
    }
    public int Speed{
        get {return speed; }//oku
        set {//yaz
            speed = value;//buraya koşullar vs de yazılabilir
          }
    }
}
// Auto-Implemented propertyler ile pratik bir şekilde get/set ilişkisi oluşturulabilir.
public String Model { get; set; }
```
## Generics
* Generic: Özel bir data tipine ait olmayan
* **Class, Method, Field vs.yi tanımlarken <T> ekleyerek ilgili şeyin farklı data tiplerinde(int, double, string vs.) kullanılabilmesini sağlarsın**
* *<T> yerine bu <> parantezler içine başka bir şey de yazılabilir*
```c#
public static void ElementleriGoster<T>(T[] array){

}
```
## Multithreading
* Thread: bir programın execution path'i. Aynı ortamda birden fazla iş yapıldığında her iş bir iplikteymiş gibi sırayla işlemciye gider.
* Uygulamalarda aynı anda birden fazla thread kullanılabilir.
* **using System.Threading** ile eklenir.
* 10'dan geriye sayan sayaç yapma:
```c#
public static void CountDown(){
    for (int i = 10; i >= 0; i--){
        Console.WriteLine("Timer:" + i)
        Thread.Sleep(1000);
        //1000 ms = 1 s
    }
}
```
* Aynı anda birden fazla sayaç yapılmak isteniyorsa multithreading kullanılır.
```c#
Thread thread1 = new Thread(() => CountDown("Timer 1:"));
Thread thread2 = new Thread(() => CountDown("Timer 2:"));
```