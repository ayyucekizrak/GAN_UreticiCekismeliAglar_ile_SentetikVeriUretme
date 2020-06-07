# <h1 align=center> DCGAN ile Keras Kullanarak Sentetik Görüntü Oluşturulması</h1>

---
<h3 align=center>(Deep Convolutional Generative Adversarial)
<h3 align=center> :shoe::shirt::sandal::dress::necktie::high_heel::womans_clothes::jeans::womans_hat::handbag: </h3>

---
:dizzy_face: **Google Colab Not Defterinde Aç**  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ayyucekizrak/GAN_UreticiCekismeliAglar_ile_SentetikVeriUretme/blob/master/DCGAN_ile_Keras_Kullanarak_Sentetik_Goruntu_%20Olusturulmasi.ipynb) 

<img align="right" src="https://github.com/ayyucekizrak/GAN_UreticiCekismeliAglar_ile_SentetikVeriUretme/blob/master/DCGAN/dcgan.gif" width="300" height="300"> Sentetik veri üretmek yapay zeka konusundaki çalışmalar listesinde ilk sıralarda yerini alıyor. Bir veriye benzer veri üretmenin yanında görsel, işitsel ve yazılı sanat eserleri de üretebiliyor. Gerçeğinden ayırt edemeyeceğiniz insan yüzleri de üretebiliyorsunuz. Bir sanatçının stilini de taklit edebiliyorsunuz. Medikal alanda size gerekli olacak verinin mevcutlardan faydalanarak çoğaltılmasını da sağlamak amacıyla kullanılabiliyor. Tüm bunlar örüntülerin başarılı şekilde çıkarılmasıyla mümkün oluyor. 

---

Derin üretici ağlar GAN'lardan ibaret değil! Boltzmann makinesi yaklaşımları (Boltzmann Machines), Derin inanç ağları (Deep Belif Networks), Evrişimsel Boltzmann yaklaşımları (Convolutional Boltzmann Machines), Yönlü (Directed Generative Nets) ve Değişimsel Otokodlayıcılar (Variational Autoencoders) gibi farklı yaklaşımlar GAN'lar dan önce ve hala kullanılıyor. İlginizi çekerse bu anahtar kelimeleri de araştırabilirsiniz.[*](https://www.deeplearningbook.org/contents/generative_models.html)

*  [*Yeni ve farklı GAN yaklaşımları da var. Yaklaşık 200 GAN yaklaşımını listeyen bu repoyu inceleyebilirsiniz.*](https://github.com/hindupuravinash/the-gan-zoo) 

### Üretici Çekişmeli Ağlar (GAN) 

2014 yılından bu yana heyecan verici yapay zeka konularından olan değişimsel otokodlayıcılar (Variatinoal autoencoders - VAEs).  ve üretici çekişmeli ağlar (Generative adverserial networks - GANs) ile görüntülerdeki saklı uzayının örneklenmesiyle var olan görseli değiştirme ya da yenisini üretmek mümkün hale geliyor. Ian Goodfellow ile derin öğrenme dünyasını sarsan GAN yaklaşımı istatistiksel anlamda gerçeğinden ayırt edilemeyen sentetik verilerin üretilmesinin önünü açıyor. Çalışma yapısında başlangıçta kötü bir taklitçi gibi düşünülebilir. Taklit yeteneği giderek gelişir ve gerçeğinden ayırt edilemeyen fakat aynısı olmayan yeni çıktılar üretilmektedir. 

:apple:[GAN için temel kaynak](https://arxiv.org/pdf/1406.2661.pdf)

Bu çalışma dosyasında DCGAN yani evrişimli bir GAN tipini ele alarak konunun mantığını uygulamalı olarak göstermeye çalışıyorum. Aşağıdaki şekil temel bir GAN yapısını ifade ediyor.

![GAN](https://i.hizliresim.com/00TSUo.png)

<img src="https://camo.githubusercontent.com/..." data-canonical-src="https://i.hizliresim.com/00TSUo.png" width="800" height="400" />

[Şekil kaynağı](https://www.tensorflow.org/tutorials/generative/images/gan1.png)

---

DCGAN ise Evrişim ve Ters Evrişimden oluşan iki ağdan oluşuyor. Üretici ve Ayırcı ağlarının evrişimli olmasından dolayı adına *Derin Evrişimli Üretici Çekişmeli Ağlar* deniyor.

:apple:[DCGAN için temel kaynak](https://arxiv.org/pdf/1511.06434.pdf)

![DCGAN](https://i.hizliresim.com/XnsRnK.jpg)

[Şekil kaynağı](https://arxiv.org/pdf/1511.06434.pdf)

---

Denklemde D ayırt edici (ayırıcı), G ise üretici olarak tanımlanmakta ve aralarındaki çekişme ifade ediliyor. Aslında bu temel bir *oyun teorisi* yaklaşımıdır.

Burada ters evrişim işlemi yaparak ve rastgele gürültüden başlayan bir görseller yapısı elde ediyoruz. Giderek bu üreticiyi gerçek görsellere benzer üretimler yapmasını aşağıdaki denklem yoluyla sağlıyoruz. 

![GAN Denklemi](https://i.hizliresim.com/IknKWJ.png)

Bu denklem aşağıdaki görseldeki yapıyı temsil ediyor:

![GAN Anlama](https://i.hizliresim.com/mYldwo.gif)

:apple:[Play with Generative Adversarial Networks (GANs) in your browser!](https://poloclub.github.io/ganlab/)


