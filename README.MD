# 24 W Flyback DC-DC Dönüştürücü (DCM, Tepe Akım Modu)

100 kHz'de çalışan, süreksiz iletim modlu (DCM) 24 V / 48 W çıkışlı flyback dönüştürücü tasarımı. Tasarım hesapları ve PLECS simülasyonu bu repoda yer alır.

## Özellikler

| Parametre | Değer |
|---|---|
| Çıkış gerilimi | 24 V |
| Çıkış gücü | 48 W (Iout = 2 A) |
| Anahtarlama frekansı | 100 kHz |
| Giriş gerilimi | *Vin,min – Vin,max (doldurun)* |
| Çalışma modu | DCM |
| Kontrol | Tepe akım modu (SR flip-flop + akım karşılaştırıcı) |
| Nüve | Samwha ETD29 (hava boşluklu) |
| Snubber | RCD |

## Tasarım Özeti

- **Primer endüktans ve tepe akım (Lp, Ipk):** DCM güç dengesinden hesaplandı.
- **Nüve seçimi:** Samwha kataloğundan; AL değeri ve Bpk, Bsat'a karşı doğrulandı. Bu güç seviyesinde hava boşluksuz nüve, gereken düşük μe değerini sağlayamadığı için hava boşluklu nüve seçildi.
- **Sarım:** Np/Ns, Lp ve Ipk değerlerine göre hesaplandı *(sarım sayılarını ekleyin)*.
- **Snubber:** Sızıntı endüktansından kaynaklanan Vds tepesini sınırlamak için RCD clamp.

## Kontrol

Tepe akım modunda çalışır: SR flip-flop clock ile set edilir, akım karşılaştırıcısı ile reset edilir. PID çıkışı tepe akım referansını belirler. Soft-start, anti-windup ve darbe atlama (pulse skipping) içerir.

## Simülasyon

Simülasyon **PLECS** ile yapıldı (`simulasyon/` klasörü). Trafo, Saturable Core ve Air Gap bloklarıyla modellendi (Ae, le, μr, Bsat parametreleri nüve kataloğundan).

## Durum

Tasarım ve simülasyon aşamasında; prototip üretilmedi.
fakat aşağıda verilen başlıca komponentler ile üretilebilir.
Çekirdek için ETD29 çekirdeği 0.5mm Gap ile
UC3844AN kontrolcüsü
ve Vds gerilim 600V dan ve Akım taşıma kapasitesi 2A den büyük herhangi bir Mosfet ile oluşturulabilir.
