# Planifyr — dəyişiklik və sınaq hesabatı

Mənbə: “Mobil UX Yeniləməsi” söhbətinə əlavə edilmiş `smart_daily_planner.html`. Mövcud tətbiqin strukturu, tapşırıq modeli və təkrarlanma mexanizmi üzərində işlənib; yeni layihə yaradılmayıb.

## Dəyişikliklər

- Mobil kartlarda tam başlıq, açıqlama, saat, prioritet və təkrarlanma göstərilir. Kartın mətninə toxunmaq redaktəni açır.
- Alt naviqasiyada bir əlavəetmə düyməsi var. Mobil təqvimdə daha aydın gün və tamamlanma sayları, desktopda tapşırıq önbaxışları göstərilir.
- Vahid rənglər, ölçülər, açıq/tünd görünüş, təhlükəsiz ekran kənarları və azaldılmış animasiya seçiminə dəstək əlavə edilib.
- Ayın 31-dən növbəti aya keçid və ay sərhədində həftə hesablanması düzəldilib. Şaquli sürüşdürmə təqvimi təsadüfən dəyişmir.
- Gecikmiş birdəfəlik tapşırıqlar bu günə keçirilir; təkrarlanan tapşırıqların başlanğıc tarixləri dəyişdirilmir.
- Axtarış bütün tarixlərdəki tapşırıq adlarını və qeydləri əhatə edir. Nəticə kartında tapşırığın başlanğıc tarixi göstərilir; tamamlanma həmin tarixə tətbiq olunur. Ayrı təkrarı tamamlamaq üçün təqvimdən müvafiq günü açın.
- Statistika bütün saxlanmış tamamlanmaları, son 7 gün üzrə tamamlanma nisbətini və bu günün aktiv tapşırıqlarını göstərir.
- Silinən tapşırığı 15 saniyə ərzində geri qaytarmaq olur. JSON ehtiyat nüsxə və bərpa imkanları əlavə edilib.
- Dialoglarda fokus idarəsi, Tab dövrəsi, Escape ilə bağlama, klaviatura ilə təqvim günlərinin açılması, forma etiketləri və bildirişlərin ekran oxuyucularına elan edilməsi təmin edilib.
- Boş siyahı, nəticəsiz axtarış, boş ad, korlanmış yaddaş və yaddaş dolması üçün ayrıca vəziyyətlər əlavə edilib.
- Stillər və ikonlar HTML daxilindədir. Xarici şrift və skript yüklənməsi tələb olunmur.

## Məlumatların saxlanması

`smart_planner_tasks` və `theme` açarları qorunub. Mövcud identifikatorlar, əlavə sahələr, `completions` tarixçəsi və köhnə `completed` sahəsi saxlanılır. Oxuna bilməyən məlumat avtomatik silinmir və ya nümunə məlumatla əvəz edilmir. Yeni, boş yaddaşda süni tapşırıqlar yaradılmır.

Brauzer yaddaşı istifadə olunan ünvana bağlıdır. Köhnə məlumatları görmək üçün yenilənmiş HTML-ni eyni brauzerdə, əvvəlki ünvan və ya fayl yolunda istifadə edin. Başqa ünvana/brauzerə keçərkən ehtiyat nüsxəni endirib bərpa edin. Mövcud brauzerinizdəki şəxsi məlumatlar bu iş zamanı oxunmayıb; uyğunluq ayrıca sınaq profili və köhnə formatlı nümunələrlə yoxlanılıb.

Bərpa zamanı təsdiq tələb olunur. Əvəzləmədən əvvəlki yaddaş `smart_planner_tasks_before_import` açarında saxlanılır.

## Sınaqlar

Ayrıca Chrome sınaq profilində, xarici şəbəkə sorğuları bloklanmış vəziyyətdə yoxlanılıb:

- Əlavəetmə, boşluqlardan ibarət adın rədd edilməsi, redaktə, tamamlanma, yenidən yükləmə, silmə və geri qaytarma.
- Gündəlik/həftəlik təkrar, başlanğıc tarixindən əvvəl göstərilməmə, köhnə məlumat formatı və əlavə sahələrin qorunması.
- Gecikmiş tapşırıqların köçürülməsi, yanvarın 31-dən fevrala keçid və fevral–mart sərhədində 7 günlük həftə.
- Gündəlik təqvim və gün panelində tamamlanmanın dərhal yenilənməsi.
- Gələcək tarixlər üzrə axtarış, nəticəsiz vəziyyət və süzgəclərin sıfırlanması.
- Tarixi tamamlanmaların statistikaya daxil edilməsi.
- 320, 390, 768, 1024 və 1440 piksel enində əsas üç görünüşdə üfüqi daşmanın olmaması.
- Uzun mətn, HTML-ə bənzər başlıq və xüsusi işarəli identifikatorların təhlükəsiz göstərilməsi.
- Dialog fokusu, arxa məzmunun deaktivləşdirilməsi, Tab dövrəsi və Escape.
- JSON endirmə və bərpa, bərpadan əvvəlki nüsxənin saxlanması.
- Korlanmış JSON, bloklanmış yaddaş və yazma limiti xətaları; uğursuz yazmada əvvəlki məlumatın qorunması.
- Açıq/tünd görünüşdə dashboard, təqvim, statistika və əlavəetmə paneli üçün axe-core 4.10.3 WCAG A/AA avtomatik yoxlamaları: aşkarlanmış pozuntu yoxdur.
- Sınaqlar ərzində JavaScript icra xətası aşkarlanmayıb.

Mobil/desktop, təqvim, dialog və tünd görünüş ekran görüntüləri vizual yoxlanılıb. Fiziki iPhone/Android, Safari və ekran oxuyucusu ilə əl ilə sınaq aparılmayıb; avtomatik əlçatanlıq yoxlaması tam uyğunluq sertifikatı deyil.

## Azərbaycan və rus dili yeniləməsi

Tətbiqə mobil başlıqda və desktop yan panelində AZ/RU seçimi əlavə edilib. Dil seçimi ayrıca `planifyr_language` açarında saxlanır. Dil dəyişdikdə tapşırıqlar, tamamlanma tarixçəsi və açıq formadakı mətnlər dəyişmir.

Menyular, formalar, prioritetlər, təkrarlanma seçimləri, boş və xəta vəziyyətləri, bildirişlər, ehtiyat nüsxə əməliyyatları və əlçatanlıq etiketləri lokallaşdırılıb. Təqvimdə rus ay və həftə adları, tarixlərdə uyğun ay formaları, saylarda rus dilinin cəm qaydaları işlədilir. Səhifənin `lang` atributu da seçilmiş dilə uyğun dəyişir. Brauzerin öz tarix/saat seçicisinin görünüşü sistem parametrlərindən asılı ola bilər.

Yoxlanılıb: dilin yenidən açıldıqda saxlanması, rus interfeysində tapşırıq yaratma və tamamlanma, dillər arasında keçərkən şəxsi mətnlərin və yaddaşın dəyişməməsi, açıq redaktə formasındakı qaralamanın qorunması. Hər iki dildə 320, 390, 768 və 1440 piksel ekranlarda dashboard, statistika və təqvimin ay/həftə/gün görünüşlərində üfüqi daşma aşkarlanmayıb. Hər iki dildə əsas üç görünüş üzrə avtomatik WCAG A/AA yoxlamasında pozuntu və JavaScript icra xətası aşkarlanmayıb.
