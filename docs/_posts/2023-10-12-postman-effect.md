---
layout: post
title: "Postman Effect"
categories: development, philosophy
---

Bir kaç gündür yazmak istediğim fakat bir türlü zaman bulamadığım bir konu var. 

Biliyorsunuz postman son dönemde bir değişiklik yaparak uygulamaya login olmayan kişilerin collection'larını görmesini engelledi. Böylece hiç bir collection'a erişemedim. Tabi yedekler ve kendi aldığı yedeklerden dolayı bir şekilde dosyayı bulabildim ve collection'ları dışarıya alabildim. Aslında yavaş da olsa oldukça kullanışlı bir uygulama olduğundan dolayı firma içerisinde bir api paylaşım aracına dönmüştü. Örneğin bir görevi tamamladıktan sonra diğer birime bunun postman örneğini gönderiyor ve sonrasında test etmesini isteyebiliyorduk. Şu anda bunlar da ortadan kalkmış oldu. Henüz tam bu konudan bilgili olmayan insanlar yine de paylaşacaktır. 

Bir diğer problem ise güvenlik. Şu anda benim yanlışlık ile yüklediğim bazı collectionlar bulunmakta. Çünkü login olduktan sonra mecbur bunları kullanmak zorunda kalıyorsunuz. Diğer türlü hiçbir requestiniz olmuyor. Bu da çok zor bir durum.

Peki postman haricinde bunu yapan yokmu. Elbette yine aynı daldan örnek verecek olursak, insomnia'da bu verilerin sunucuda yedeklenmesi için login mekanizması yaptı. Yani iş en sonunda hep kullanıcı topla, bekle, çok feature üret ve bir şekilde para vermelerini sağlaya dönüyor. 

İlk andan itibaren paralı olan uygulamalar da var. Örneğin intellij ideleri buna dahil. Ücretini veriyorsunuz ve bu özelliğe sahip oluyorsunuz. Fakat yapabildiği postman collectionlarını almak. Örneğin ben intellij çıktısı bir dosyayı başka bir yere gönderdiğimde o kişinin de intellij'ye sahip olması gerekiyor. Bu da imkansız.

Postman bende hırsız imajı uyandırıyor. Elbette para almalarında bir beis yok. Fakat bu şekilde insanları kendilerine ücretsiz olarak bağlayıp bir pazar oluşturup ani bir hareketler para vermeyenlerin ellerindekileri alıp hırçın bir yol izlemeleri benim open source'a olan güvenimi artırdı. Artık kullandığım uygulamaların open source olmasına daha fazla özen göstereceğim. Ücretinden dolayı değil böyle bir tuzağa düşmeyecek oluşumdan dolayı.

Firma içerisinde kullanmak için bu toollardan birini kullanıp bir sunucu uygulaması ile aralarında bu requestleri anlık olarak paylaşmalarını sağlayacak bir sistem yapmak istiyorum. Bakalım zamanım ve kaynağım olacak mı bunun için.
