# SM Kod Yazım Standartları

## Genel

- Her dil için ilgili firmanın (C# için Microsoft, React için Meta vb.) hazırladığı standartlar, bu dokümanda belirtilen standartlardan farklılık gösteriyorsa önceliği vardır.
- Standartlar, proje başlangıcında ilk konuşulan konular arasında olmalıdır. Her proje için bu doküman veya benzer dokümanlar kullanılarak, proje çalışanları ve paydaşları ile paylaşılmak üzere proje kod yazım standartları dokümantasyonu oluşturulması önerilir.
- Proje süresince standartlarda revizyon/değişiklik yapılmışsa, bu durum proje kod yazım standartları dokümantasyonunda hem değişiklik/ekleme tarihi hem de uygulanmaya başlanma tarihi ile birlikte belirtilmelidir.
- Proje kod yazım standartları dokümantasyonuna göre uygun linter kuralları hazırlanmalıdır. (Bkz: [Lint (software)](https://en.wikipedia.org/wiki/Lint_(software)))
- Bu doküman, her yıl Ocak ayında ilgili dil/dillerin uzmanları tarafından gözden geçirilmeli, gerekirse revize edilmelidir.
- Gerekirse farklı diller için farklı dokümanlar halinde düzenlenmiş olabilir. Bu durumda "Genel" başlığı altındaki maddelerin ayrı bir dokümanda olacak şekilde düzenlenmesi ve diğer dokümanlar içerisinde referans linki olarak mutlaka bulunması sağlanmalıdır.
- Yapı, fonksiyon, değişken vs. isimlendirmelerinde sadece doğru bir İngilizce kullanımına özen gösterilmelidir (Ör: "UsersGetById(id)" yerine "GetUserById(id)").
- Yapı, değişken ve fonksiyon isimlendirmelerinde amacı net bir şekilde ifade eden isimler kullanmaya dikkat edilmelidir.

## JavaScript

- [AirBnb JavaScript Stil Rehberi](https://github.com/airbnb/javascript)
  - Türkçesi: [AirBnb JavaScript Stil Rehberi (Türkçe)](https://github.com/eraycetinay/javascript)

### Kod Formatı

- Tutarlı bir kod formatlama aracı kullanın (ör. Prettier)
- Tutarlı satır başı işlemleri için tab kullanın (bir tab kaç boşluk, karar verilecek)
- Operatörlerden önce ve sonra birer adet boşluk kullanın
- Virgüllerden sonra bir adet boşluk kullanın

### İsimlendirme Kuralları

- Değişken ve fonksiyon isimleri için camelCase kullanın
- Sınıflar ve constructor isimleri için PascalCase kullanın
- Private property'ler ve metodların ismini "_" (alt tire) karakteri ile başlatın
- Koordinat veya index belirtilmiyorsa değişken isimlendirmelerinde x,y,z,i gibi bir anlam ifade etmeyen ifadelerden kaçının
- Yapı, değişken ve fonksiyon isimlendirmelerinde amacı net bir şekilde ifade eden isimler kullanmaya dikkat edin

### ES6+ Özellikleri

- Uygun yerlerde arrow function, destructing ve template literal kullanımına ağırlık verin
- Değişken tanımlamalarında "var" yerine "const" veya "let" kullanın
- Modül organizasyonu için import/export ifadelerinin kullanımına ağırlık verin

### Error Handling

- Senkron işlemlerde "try-catch" yapısını kullanın
- Asenkron işlemlerde Promise ve "catch()" kullanın

### DOM Manipülasyonu

- DOM sorgularını tekrar tekrar yapmak yerine cache'leyerek kullanın
- Event yapısının doğru ve efektif kullanımına dikkat edin

### Asenkron Programlama

- Asenkron kod okunabilirliği için `async/await` kullanın
- Promiseleri `then` ve `catch` ile ele alın

### Linting

- Kod kalitesi için ESLint veya benzer bir araç kullanın
- Linter'ları yaygın hataları yakalamak için yapılandırın

## C#

- [Microsoft isimlendirme kuralları](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/identifier-names)
- [Microsoft kod yazım kuralları](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)

### Kod Organizasyonu ve Yapısı

- Namespace'leri etkili bir şekilde kullanın
- Kodu mantıklı klasörlere organize edin
- Sınıfları ve metotları odaklı ve küçük tutun

### İsimlendirme Kuralları

- Sınıflar ve metotlar için PascalCase isimlendirme kuralına uyun
- Parametreler ve yerel değişkenler için camelCase kullanın
- Interface isimlerini "I" harfi ile başlatın
- Yapı, değişken ve fonksiyon isimlendirmelerinde amacı net bir şekilde ifade eden isimler kullanmaya dikkat edin

### Boşluklar ve Biçimlendirme

- Operatörlerden önce ve sonra birer boşluk ekleyin
- Virgülden sonra boşluk ekleyin
- Satır başı için tab (sekme) kullanın
- bir tab 4 space olacak şekiklde IDE'nizi ayarlayın

### Yorumlar ve Belgelendirme

- Sınıflar, metotlar ve özellikler için Visual Studio’da otomatik olarak tamamlanan XML belgelendirme yorumları kullanın
- Kendini açıklayan kod yazımına dikkat edin, yorum ihtiyacını minimumda tutun

### Exception Handling

- Sadece spesifik hataları yakalayın, "catch(Exception ex)" gibi genel hata yakalama işlemlerinden mümkün mertebe uzak durun
- Doğru log kullanımına dikkat edin. Log mesaj şablonu kullanımında string literal yerine parametreli mesaj kullanın

### Coding Practices

- Eğer tip açıksa "var" ile değişken tanımlayın
- Public field'lar yerine property'leri tercih edin
- Aşırı "#region" kullanımından kaçınmaya çalışın
- Mümkün oldukça primary constructor kullanın,
- Yeni collection initialize edilirken mümkün oldukça "[]" kullanın (dotnet 7+) ya da Array.Empty<T>() ( dotnet 7 öncesi )

### Asenkron Programlama

- Eğer bir metodun hem Async hem Sync versiyonu varsa, mümkün olduğunca Async versiyonunu tercih etmeye çalışın
- Asenkron işlemler için async ve await keyword'lerini kullanın
- Task-based Asynchronous Pattern (TAP) kullanımına özen gösterin (Ref: [Task-based Asynchronous Pattern (TAP)](https://learn.microsoft.com/en-us/dotnet/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap))

### Unit Testing

- Kritik tüm kodlar için unit test yazın. Bunu kod yazımının bir parçası haline getirin
- Testler için proje genelinde tutarlı isimlendirmeler kullanın
