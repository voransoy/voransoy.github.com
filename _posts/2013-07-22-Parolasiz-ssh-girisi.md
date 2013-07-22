---
layout: post
title: Parolasız SSH Girişi
date: 2013-07-22 20:08:21 UTC
updated: 2013-07-22 20:08:21 UTC
comments: false
categories: ssh debian ubuntu
---

#Parolasız SSH Girişi

Otomasyon işlemlerinin vazgeçilmezi parolasız SSH girişi işini her seferinde sıfırdan Google ile arayarak yapıyordum. Güzelce not alalım ki tekrar aramayalım.

Öncelikle bir ssh key üretiyoruz. Üretirken passphrase girmiyoruz. Girersek bu kez SSH girişinde bize bu passphrase sorulacak. Biz bunu istemiyoruz. Sorduğunda boş geçiyoruz.

{% highlight bash %}
ssh-keygen -t rsa
{% endhighlight %}

Ardından bu keyi bağlanacağımız sunuculara, yetkilendirilmiş kullanıcı olarak tanıtmamız lazım. Eskiden bunu .ssh/authorized_keys içine yazarak yapıyorduk ama iş kolaylaştı.

{% highlight bash %}
ssh-copy-id -i ~/.ssh/id_rsa.pub root@1.1.1.1
{% endhighlight %}

"1.1.1.1" bizim bağlanacağımız sunucu. Sunucunun root parolasını girince gerekli işlemler otomatik yapılacak. Artık sadece tek komut ile SSH bağlantısı yapabiliriz.

{% highlight bash %}
ssh root@1.1.1.1
{% endhighlight %}

Şeklinde giriş yapmaya çalıştığınızda size şifre sormayacaktır.

Bu arada "Error: Agent admitted failure to sign" şeklinde bir hata alırsanız mevcut SSH keylerinizi agenta eklemeniz gerektiği anlamına gelir. 

{% highlight bash %}
ssh-add
{% endhighlight %}

komutu ile bu hatayı giderebilirsiniz.




