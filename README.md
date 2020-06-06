# <h1 align=center> DCGAN ile Keras Kullanarak Sentetik Görüntü Oluşturulması</h1>

---
<h3 align=center>(Deep Convolutional Generative Adversarial

---
### Üretici Çekişmeli Ağlar (GAN)

2014 yılından bu yana heyecan verici yapay zeka konularından olan değişimsel otokodlayıcılar (Variatinoal autoencoders - VAEs).  ve üretici çekişmeli ağlar (Generative adverserial networks - GANs) ile görüntülerdeki saklı uzayının örneklenmesiyle var olan görseli değiştirme ya da yenisini üretmek mümkün hale geliyor. Ian Goodfellow ile derin öğrenme dünyasını sarsan GAN yaklaşımı istatistiksel anlamda gerçeğinden ayırt edilemeyen sentetik verilerin üretilmesinin önünü açıyor. Çalışma yapısında başlangıçta kötü bir taklitçi gibi düşünülebilir. Taklit yeteneği giderek gelişir ve gerçeğinden ayırt edilemeyen fakat aynısı olmayan yeni çıktılar üretilmektedir. 

[GAN için temel kaynak](https://arxiv.org/pdf/1406.2661.pdf)

Bu çalışma dosyasında DCGAN yani evrişimli bir GAN tipini ele alarak konunun mantığını uygulamalı olarak göstermeye çalışıyorum. Aşağıdaki şekil temel bir GAN yapısını ifade ediyor.

![GAN](https://i.hizliresim.com/00TSUo.png)

[Şekil kaynağı](https://www.tensorflow.org/tutorials/generative/images/gan1.png)

---

DCGAN ise Evrişim ve Ters Evrişimden oluşan iki ağdan oluşuyor. Üretici ve Ayırcı ağlarının evrişimli olmasından dolayı adına *Derin Evrişimli Üretici Çekişmeli Ağlar* deniyor.

[DCGAN için temel kaynak](https://arxiv.org/pdf/1511.06434.pdf)

![DCGAN](https://i.hizliresim.com/XnsRnK.jpg)

[Şekil kaynağı](https://arxiv.org/pdf/1511.06434.pdf)

---

[*Yeni ve farklı GAN yaklaşımları vardır. Yaklaşık 200 GAN yaklaşımını listeyen bu repoyu inceleyebilirsiniz.*](https://github.com/hindupuravinash/the-gan-zoo) 

---

Denklemde D ayırt edici (ayırıcı), G ise üretici olarak tanımlanmakta ve aralarındaki çekişme ifade ediliyor. Aslında bu temel bir *oyun teorisi* yaklaşımıdır.

Burada ters evrişim işlemi yaparak ve rastgele gürültüden başlayan bir görseller yapısı elde ediyoruz. Giderek bu üreticiyi gerçek görsellere benzer üretimler yapmasını aşağıdaki denklem yoluyla sağlıyoruz. 

![GAN Denklemi](https://i.hizliresim.com/IknKWJ.png)

Bu denklem aşağıdaki görseldeki yapıyı temsil ediyor:

![GAN Anlama](https://i.hizliresim.com/mYldwo.gif)

Kaynak: [Play with Generative Adversarial Networks (GANs) in your browser!](https://poloclub.github.io/ganlab/)

