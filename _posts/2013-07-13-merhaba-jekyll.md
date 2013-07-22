---
layout: post
title: Merhaba Jekyll.
date: 2013-07-13 06:24:21 UTC
updated: 2013-07-13 06:24:21 UTC
comments: false
categories: ruby jekyll
---

Uzun zamandır güncellemediğim bloğuma artık hakettiği önemi vermenin zamanı geldi. Becerebilirsen artık daha sık güncelleyeceğim. Blogger üzerinde host ettiğim bloğumu da bu süreçte yenilemek istedim. Mevcut hali ile çok fazla müdehale edemediğim bloğumu daha hacker dostu bir şey ile değiştirmek istediğimde aklıma ilk Jekyll geldi. Bir süredir, Github'ın da sayesinde adını duyuyordum. Ama ne yalan söyleyeyim bu kadar kolay olacağını sanmamıştım. Bu yazıda bloğumu Blogger üzerinden Github Pages üzerine Jekyll kullanarak nasıl aktardığımı anlatmaya çalışcağım.

Öncelikle sisteminizde ruby gems kurulu olduğunu düşünüyorum ve bu kısmı geçiyorum. Ama ruby ve rubygems kurulumu ile ilgili olarak Ubuntu platformu için güzel bir rehber [burada var.](https://help.ubuntu.com/community/RubyOnRails/ "Ruby installation on Ubuntu")

{% highlight bash %}
gem install jekyll
{% endhighlight %}

Öncelikle bir Github reposu açıyoruz. Bu repoyu açarken dikkat edilmesi gereken husus, repo adının kullanıcıadı.github.com olarak açılmasıdır. Benim örneğimde repoyu voransoy.github.com olarak açtım. Bu isim düzenini kullandığınızda Github bunun bir Github Pages reposu olduğunu anlıyor ve 10 dakika içinde bu url ile erişilebilir durumda oluyor sayfanız. Daha sonra bir dizin oluşturup jekyll'ı bu dizine kurdum.

{% highlight bash %}
mkdir voransoy.github.com
jekyll new voransoy.github.com
{% endhighlight %}

Bu adımdan sonra oluşan dizin içine Jekyll standart dizin yapısını açtı. Sonraki adım olarak dizini Github ile ilişkilendiriyorum.

{% highlight bash %}
cd voransoy.github.com
git init
git remote add origin https://github.com/voransoy/voransoy.github.com.git
git add .
git commit -a -m "ilk commit"
git push origin master
{% endhighlight %}

Bu adım sonunda artık Github Pages üzerinden http://voransoy.github.com adresi ile erişilebilen bir siteniz oldu. Tabi default Jekyll içeriği ile. Şu andan itibaren yeni blog yazılarını yazabiliriz. Yazılarımızı "_post_" dizini altında yazmamız gerekiyor. Dosya adı formatı önemli. Tarih ve ardından yazının başlığı şeklinde olmalı. Bu yazı için "2013-07-13-merhaba-jekyll.md" olarak oluşturdum ben. Dosya uzantısı .html, .md, .markdown, .textile olabilir. Jekyll bu uzantılara göre çıktı oluşturmakta. Dosyanın ilk kısmında yazı ile ilgili meta datanın bulunması gerekli. Aşağıda bu yazının meta datasını görebilirsiniz. Meta datayı takiben istediğiniz formatta yazınızı yazabilirsiniz. Ben markdown kullandım.

{% highlight rst %}
---
layout: post
title: Merhaba Jekyll.
date: 2013-07-13 06:24:21 UTC
updated: 2013-07-13 06:24:21 UTC
comments: false
categories: ruby jekyll
---

#Merhaba Jekyll

Uzun zamandır güncellemediğim bloğuma artık hakettiği...
{% endhighlight %}

Yazımızı oluşturduğumuza göre artık Github'a gönderebiliriz.

{% highlight bash %}
git add .
git commit -a -m "ilk post"
git push origin master
{% endhighlight %}

Basitçe ilk yazımızı yazdık ve Github'a yolladık. Github bu yazıyı derleyip bize http://voransoy.github.com üzerinden oromatik olarak sunmaya başlayacak. Peki yazılarımızı biz Github üzerinde değil de farklı bir servis sağlayıcı da barındıracaksak? O zaman bu içeriği bizim derlememiz lazım. Bu da kolay...

{% highlight bash %}
jekyll build
{% endhighlight %}

komutu ile Jekyll bize "_site" dizini içerisinde tüm içeriğin html olarak derlenmiş bir halini oluşturur. Herhangi bir hosting hesabına bu içeriği kopyalayabilir, sitenizi buradan sunabilirsiniz. Şimdilik bu kadar. Bir sonraki yazımda vakit bulursam Blogger'dan Jekyll'a mevcut yazılarımı nasıl göç ettiğimi de yazacağım.

Faydalandığım linkler:
- [Jekyll resmi sitesi](http://jekyllrb.com/ "Jekyll")
- [Markdown yazım kılavuzu](http://daringfireball.net/projects/markdown/syntax "Markdown guide")





