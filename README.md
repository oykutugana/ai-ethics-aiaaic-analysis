# Yapay Zekâ Kendi Etiğini Yargılayabilir mi?
### AIAAIC İhlalleri Üzerinden Anatomi, Model Karşılaştırması ve Sınıflandırma (2021–2026)

## Özet
AIAAIC veri tabanından (2021–2026) derlenmiş 1001 gerçek AI etik ihlali üzerine üç katmanlı analiz:
1. **p1-Anatomi** — ihlallerin yapısı, trendi, teknoloji/sektör kırılımı
2. **p2-Model Karşılaştırması** — 4 büyük dil modelinin (GPT-5.5, Gemini, Claude, DeepSeek) 200 vakayı etik açıdan değerlendirmesi
3. **p3-Sınıflandırıcı** — başlıktan etik konuyu tahmin eden çok-etiketli ML modeli (Macro-F1 = 0.62)

## Dosyalar
- `Team6_Ethics_final.ipynb` — tüm analiz kodu
- `Team6_Ethics_final_report.pdf` 
- `visuals/` — 13 görsel (p1,p2,p3)
- `README.md`
--------------------------------------------------
- `AIAAIC_Incidents.xlsx` - raw veri (3457 vaka)
- `aiaaic_cleaned_03.csv` — temizlenmiş analiz havuzu (1001 vaka)
- `model_karsilastirma_dolu.xlsx` — 200 vaka × 4 model yargı tablosu
- `etik_konu_siniflandirici.joblib` — eğitilmiş sınıflandırıcı (TF-IDF + OvR Logistic Regression)
- `prompts/` - karşılaştırma için modellerde kullanılan promptlar
- `cevaplar/` - modellerin promptlara verdiği cevaplar (her model için 200 cevap)

## Temel Bulgular
- Transparency en baskın endişe; Generative AI en sık kaynak teknoloji.
- 4 model de ihlalleri tanıyor; fark "kim daha etik" değil, belirsizliği işleme tarzında
  (Gemini/DeepSeek katı, GPT-5.5/Claude gri bölge).
- Sınıflandırıcı somut ihlalleri (Privacy 0.73, Mis/disinfo 0.71) iyi tanıyor;
  soyut kavramda (Accountability 0.49) zorlanıyor. Başarı örnek sayısından bağımsız (kor.=0.01).

## Yöntem Notları
- Kodlama: 0 = etik değil, 0.5 = duruma bağlı, 1 = etik
- Sınıflandırıcı çok-etiketli (AIAAIC etiketleri alfabetik sıralı olduğu için tek-label'a indirgenmedi)

## Limitasyonlar
Beyan edilmiş yargı ölçülmüştür,fiili davranış değil ; tek sürüm/tek seferlik test;
ihlal arşivi olduğu için maruziyet yanlılığı; etiketler AIAAIC editör yargısıdır.
