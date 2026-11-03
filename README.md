# Katta tub sonlarni generatsiya qilish algoritmlarining qiyosiy benchmarki

**AL-9624115197 “Katta tub sonlarni generatsiya qilish algoritmlarini ishlab chiqish” loyihasi uchun tajriba dasturi.**

Ushbu loyiha axborot xavfsizligi va kriptografiyada muhim o'rin tutuvchi katta o'lchamdagi (256, 512, 1024, 2048 bitli) tub sonlarni generatsiya qilish algoritmlarining ishlash tezligi va samaradorligini o'zaro taqqoslaydi. 

Dastur Jupyter Notebook muhitida yozilgan bo'lib, turli ehtimoliy va deterministik tublik testlari asosida yozilgan algoritmlarning vaqt sarfi hamda hisoblash murakkabligini tahlil qiladi.

## 🚀 Asosiy algoritmlar

Loyihada quyidagi generatsiya usullari va tublik testlari qiyoslangan:
* **G1 (Sodda usul):** Tasodifiy toq k-bitli son va Miller-Rabin (MR) testi.
* **G2 (Bo'lish usuli):** Kichik tublarga bo'lib ko'rish va MR testi.
* **G3 (GCD filtr):** EKUB (GCD) yordamida tezkor filtr va MR testi.
* **G4 (Inkremental elak):** Kichik tublar bilan inkremental elash va MR/Baillie-PSW testlari.
* **G5 (Isbotlanadigan usul):** Pocklington teoremasi yordamida qat'iy isbotlanadigan tub son generatsiyasi.

## 📊 O'tkazilgan tajribalar (Benchmark)

Notebook avtomatik ravishda quyidagi tajribalarni bajaradi va natijalarni jadvallar (CSV/Excel) hamda grafiklar shaklida saqlaydi:

1. **T1 (To'g'rilik tekshiruvi):** Miller-Rabin va Baillie-PSW testlarining ishonchliligini qiyin holatlar (Karmaykl sonlari, psevdotublar) misolida tekshirish.
2. **T2 (Asosiy benchmark):** Qaysi generatsiya usuli bitta tub son topish uchun eng kam vaqt (mediana) va `powmod` amalini bajarishini o'lchash.
3. **T3 (Optimallashtirish):** Kichik tublar elak chegarasining (B) eng optimal qiymatini aniqlash.
4. **T4 (Nazariya va tajriba):** Tekshirilgan nomzodlar sonini Mertens formulasidagi matematik bashoratlar bilan taqqoslash.
5. **T5 (Taqsimot):** Inkremental usulda tub sonlarning tanlanish taqsimoti tekis yoki tekis emasligini tahlil qilish.
6. **T6 (Tashqi kutubxonalar):** Natijalarni OpenSSL, gmpy2 kabi mashhur kutubxonalar tezligi bilan qiyoslash.

## 🛠 Texnologiyalar
* Python 3.x
* Kutubxonalar: `gmpy2` (tezkor arifmetika uchun), `numpy`, `pandas`, `matplotlib`.

*Eslatma: Benchmarkda natijalar qayta takrorlanuvchan bo'lishi uchun `random.Random(seed)` ishlatilgan. Haqiqiy kriptografik amaliyotda OS entropiya manbaiga asoslangan `secrets` modulidan foydalanish zarur.*
