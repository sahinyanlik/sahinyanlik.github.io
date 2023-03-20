---
layout: post
title: "Google service weaver"
categories: development
---

Service weaver Google'un cloud uygulaması yazma ve deploy etmek hazırladığı yeni frameworktür. [Service Weaver](https://serviceweaver.dev) adresinden inceleyebilirsiniz. 

Uygulamayı normal Go interface'i olarak yazılmış component'lere bölmek yeterli. 

Örneğin Added diye bir interface'iniz var. Bunu weaver.Implements'e ekliyorsunuz ve kullanacağınız zaman weaver.Get ile bu interface'i tekrar alıp bunun metodlarına erişebilirsiniz.

Yani önce bir component'i weaver'a ekliyorsunuz sonra ise weaver'dan bu interface'i çağırıp çalıştırıyorsunuz. Aslında Spring-Context'e biraz benziyor fakat weaver arka tarafta bir çok sunucuda olabilen ve tüm beanleri diğer sunucularda da ayağa kaldıran bir engine olarak düşünülmeli. 

Kullanımı sırasında bu aradaki iletişimi kurmak için sürekli olarak weaver generate . şeklinde kod içerisinde aradaki bağlantıyı kuracak katmanı generate etmeniz gerekmekte.

İlk önce single process execution ile başladığınız projeye sonradan bir TOML dosyası ekleyerek multiprocessor haline getirebiliyorsunuz. Bu açıdan oldukça kolaylık sağlıyor.

Diğer bir güzel özelliği ise Kubernetes gibi teknolojilere çok çabuk şekilde deploy edilebilmesi tek yapmanız gereken

weaver gke deploy weaver.toml

Tabi öncesinde gke ( google kubernetes engine) indirmeniz ve gerekli ayarları yapmanız gerekli. 

## Faydaları

* Type sistemi olacağından dolayı versiyonlama, componentlerin bir biri ile uyumluluğu gibi sorunlar olmayacaktır.
* Bu yapı ile aslında Erlang benzeri altta transparent network olan yani network üzerinden başka bir metodu trigger eden bir yapıyı Go'ya da yapmış oldular.
* gRpc kullanıyor fakat .proto dosyası yok. 
* Rest ile iletişim kuran uygulamalara nazaran kullandığı servisleri gerektiğinde aynı execution engine'e koyması muhtemel. Bu birbiri ile iletişim kuran iki componentin aslında aynı makinede çalıştırılabilmesi demek. Bunu otomatik yapıyor. Böylece network üzerinden iletişime gerek kalmıyor. Bazı durumlarda kesinlikle network hatalarına karşı toleranslı olunmayabilir. Bu gibi durumlarda ise colocation özelliği kullanılarak aynı bazı servislerin aynı sunucuda olması sağlanabilir. Böylece network üzerinden çağrı yapılmamış olur.
 

## Sıkıntıları

* Öncelikle microservis mimarisinin ruhuna tam uymuyor. Burada takımları ayırma gibi bir şey söz konusu değil. Sadece farklı sunucularda servisler halinde uygulamanın çalışmasını sağlıyor.
 

