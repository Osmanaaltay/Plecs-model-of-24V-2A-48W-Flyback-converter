# Plecs model of 24V 2A 48W Flyback converter
non-ideal-circuit-model
# Flyback (DCM) Tasarım Tezgâhı

Sabit frekanslı, tepe akım modunda çalışan **DCM flyback dönüştürücüler** için tek dosyalık, tarayıcı tabanlı bir tasarım ve doğrulama aracı. Kurulum gerektirmez; `flyback_tasarim_araci.html` dosyasını tarayıcıda açmanız yeterlidir.

## Özellikler

- **Özet ve kontroller:** Hata/uyarı listesi ve her kalem için çözüm önerisi
- **Dalga şekilleri:** Vin ve yük kaydırıcılarıyla canlı akım/gerilim, DCM ↔ CCM geçişi
- **Adım adım hesap:** Makale denklemlerinin sizin girdilerinizle çözümü
- **Trafo ve snubber:** Sarım önerisi, Np/Ns, Lpri, RCD snubber tasarımı
- **Kayıp ve verim:** Kayıp dağılımı, iteratif verim hesabı
- **Tarama grafikleri:** DCM emniyet payının yük ve hat gerilimi boyunca değişimi
- JSON kaydet/yükle, PDF olarak yazdırma, koyu/açık tema

## Kullanım

1. `Vin,min/max`, `Vout`, `Iout` ve `fsw` değerlerini girin.
2. `Dmax`, `η` ve `x` gibi tasarım varsayımlarını seçin.
3. Özet sekmesindeki kırmızı **HATA**'ları giderin, sarı **UYARI**'ları değerlendirin.
4. Gerçek parça değerlerini (Np/Ns, Lpri, Rs, Rsn) girin; kontroller yenilenir.

## Kaynaklar

Hesaplar Texas Instruments'ın SLUP127, SSZTCV6 ve SSZTCW6 uygulama notlarına dayanır. Bu notlardaki bazı tutarsızlıklar ve bunların araçta nasıl ele alındığı, araç içindeki **Kullanım & Makale Notları** sekmesinde açıklanmıştır.

## Sınırlamalar

Araç; EMI, izolasyon/güvenlik standartları, kontrol döngüsü kompanzasyonu ve ısıl analizi kapsamaz. Sonuçlar ön tasarım içindir; prototip ölçümü ve simülasyonun yerini tutmaz.
