---
layout: post
title: "Google service weaver"
categories: development
---

Service weaver Google'un cloud uygulaması yazma ve deploy etmek hazırladığı yeni frameworktür. [Service Weaver](https://serviceweaver.dev) adresinden inceleyebilirsiniz. 

Uygulamayı normal Go interface'i olarak yazılmış component'lere bölmek yeterli. 

Örneğin Added diye bir interface'iniz var. Bunu weaver.Implements'e ekliyorsunuz ve kullanacağınız zaman weaver.Get ile bu interface'i tekrar alıp bunun metodlarına erişebilirsiniz.

Yani önce bir component'i weaver'a ekliyorsunuz sonra ise weaver'dan bu interface'i çağırıp çalıştırıyorsunuz. Aslında Spring-Context'e biraz benziyor fakat weaver arka tarafta bir çok sunucuda olabilen ve tüm beanleri diğer sunucularda da ayağa kaldıran bir engine olarak düşünülmeli. 

## Faydaları

* Type sistemi olacağından dolayı versiyonlama, componentlerin bir biri ile uyumluluğu gibi sorunlar olmayacaktır.
* Bu yapı ile aslında Erlang benzeri altta transparent network olan yani network üzerinden başka bir metodu trigger eden bir yapıyı Go'ya da yapmış oldular.
* gRpc kullanıyor fakat .proto dosyası yok. 

## Sıkıntıları

* Öncelikle microservis mimarisinin ruhuna tam uymuyor. Burada takımları ayırma gibi bir şey söz konusu değil. Sadece farklı sunucularda servisler halinde uygulamanın çalışmasını sağlıyor.
 

