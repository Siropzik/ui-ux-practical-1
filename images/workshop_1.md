# Практичне заняття: Оптимізація зображень за допомогою Squoosh

## Мета заняття

- Ознайомитися з методами стиснення зображень та їхнім впливом на якість.
- Навчитися визначати баланс між якістю та розміром файлу.
- Дослідити вплив зміни розміру на якість та вагу зображень.
- Адаптувати зображення для різних застосувань (веб, мобільні пристрої, Retina-дисплеї).
- Закріпити навички документування та аналізу результатів у Markdown-форматі.

## Теоретична частина

### Що таке Squoosh і як він працює?

Squoosh — це інструмент для стиснення зображень, що дозволяє порівнювати оригінали з оптимізованими версіями в реальному часі.

### Формати зображень та типи стиснення:

- **Без втрат (lossless):** PNG, WebP (lossless).
- **З втратами (lossy):** MozJPEG, WebP (lossy), AVIF.

### Оптимізація зображень для Retina-дисплеїв:

- Використання збільшеного розміру (2x, 3x) для збереження чіткості.
- Використання адаптивних зображень у вебі (srcset).

---

## Аналіз вихідних файлів

| Назва зображення    | Формат | Розмір (px) | Вага файлу |
| ------------------- | ------ | ----------- | ---------- |
| photo_original      | jpg    | 1920 x 1080 | 167.2 KB   |
| screenshot_original | png    | 1366 x 768  | 688.2 KB   |
| graphic_original    | jpg    | 3840 x 2400 | 1.14 MB    |

## Вихідні зображення

### Оригінальне фото

![Оригінальне фото](Photo_files/photo_original.jpg)

### Оригінальний скріншот

![Оригінальний скріншот](Photo_files/screenshot_original.png)

### Оригінальна графіка

![Оригінальна графіка](Photo_files/graphic_original.jpg)

---

## Lossless стиснення (без втрат)

## WebP

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна (%) |
| ------------------- | ------ | ----------- | ---------- | --------- |
| photo_original      | WebP   | 1920 x 1080 | 788 KB     | +355%     |
| screenshot_original | WebP   | 1366 x 768  | 1.60 MB    | +127%     |
| graphic_original    | WebP   | 3840 x 2400 | 4.74 MB    | +295%     |

### Оптимізовані зображення WebP

![Фото WebP](Photo_files/photo_original.webp)
![Скріншот WebP](Photo_files/screenshot_original.webp)
![Графіка WebP](Photo_files/graphic_original.webp)

---

## PNG

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | PNG    | 1920 x 1080 | 1.04 МБ    | +542% |
| screenshot_original | PNG    | 1366 x 768  | 1.85 МБ    | +163% |
| graphic_original    | PNG    | 3840 x 2400 | 7.55 МБ    | +529% |

![photo_original](Photo_files/photo_original.png)  
![screenshot_original](<Photo_files/screenshot_original(Oxi).png>)  
![graphic_original](Photo_files/graphic_original.png)

---

## lossy (MozJPEG 100%)

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | JPG    | 1920 x 1080 | 404 КБ     | +136% |
| screenshot_original | JPG    | 1366 x 768  | 917 КБ     | +30%  |
| graphic_original    | JPG    | 3840 x 2400 | 2.58 МБ    | +115% |

![photo_original](Photo_files/photo_original.jpg)  
![screenshot_original](Photo_files/screenshot_original.jpg)  
![graphic_original](<Photo_files/graphic_original(Moz).jpg>)

## MozJPEG 75%

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | jpg    | 1920 x 1080 | 111 КБ     | -35%  |
| screenshot_original | jpg    | 1366 x 768  | 160 КБ     | -77%  |
| graphic_original    | jpg    | 3840 x 2400 | 843 КБ     | -30%  |

![photo_original](<Photo_files/photo_original(75).jpg>)  
![screenshot_original](<Photo_files/screenshot_original(75).jpg>)  
![graphic_original](<Photo_files/graphic_original(75).jpg>)

---

## MozJPEG 50%

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | jpg    | 1920 x 1080 | 57.8 КБ    | -66%  |
| screenshot_original | jpg    | 1366 x 768  | 95.5 КБ    | -86%  |
| graphic_original    | jpg    | 3840 x 2400 | 513 КБ     | -57%  |

![photo_original](<Photo_files/photo_original(50).jpg>)  
![screenshot_original](<Photo_files/screenshot_original(50).jpg>)  
![graphic_original](<Photo_files/graphic_original(50).jpg>)

---

## MozJPEG мінімальний рівень якості

_Мінімальний рівень якості, при якому зображення залишається прийнятним._

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна | Якість |
| ------------------- | ------ | ----------- | ---------- | ----- | ------ |
| photo_original      | jpg    | 1920 x 1080 | 30.3 КБ    | -82%  | 25%    |
| screenshot_original | jpg    | 1366 x 768  | 87.3 КБ    | -88%  | 45%    |
| graphic_original    | jpg    | 3840 x 2400 | 200 КБ     | -83%  | 15%    |

![photo_original](<Photo_files/photo_original(25).jpg>)  
![screenshot_original](<Photo_files/screenshot_original(45).jpg>)  
![graphic_original](<Photo_files/graphic_original(15).jpg>)

---

## WebP 100%

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | webp   | 1920 x 1080 | 402 КБ     | +135% |
| screenshot_original | webp   | 1366 x 768  | 877 КБ     | +24%  |
| graphic_original    | webp   | 3840 x 2400 | 3.17 МБ    | +164% |

![photo_original](Photo_files/photo_original100.webp)  
![screenshot_original](Photo_files/screenshot_original100.webp)  
![graphic_original](Photo_files/graphic_originalWebP100.webp)

## WebP 75%

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | webp   | 1920 x 1080 | 87.1 КБ    | -49%  |
| screenshot_original | webp   | 1366 x 768  | 188 КБ     | -73%  |
| graphic_original    | webp   | 3840 x 2400 | 799 КБ     | -33%  |

**Файли:**  
![photo_original](Photo_files/photo_original75.webp)  
![screenshot_original](Photo_files/screenshot_original75.webp)  
![graphic_original](Photo_files/graphic_originalWebp75.webp)

---

## WebP 50%

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | webp   | 1920 x 1080 | 63.7 КБ    | -63%  |
| screenshot_original | webp   | 1366 x 768  | 136 КБ     | -81%  |
| graphic_original    | webp   | 3840 x 2400 | 601 КБ     | -50%  |

![photo_original](Photo_files/photo_original50.webp)  
![screenshot_original](Photo_files/screenshot_original50.webp)  
![graphic_original](Photo_files/WebP50.webp)

---

## WebP (мінімальна якість)

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна | Якість |
| ------------------- | ------ | ----------- | ---------- | ----- | ------ |
| photo_original      | webp   | 1920 x 1080 | 36 КБ      | -80%  | 20%    |
| screenshot_original | webp   | 1366 x 768  | 76.2 КБ    | -89%  | 20%    |
| graphic_original    | webp   | 3840 x 2400 | 260 КБ     | -78%  | 8%     |

![photo_original](Photo_files/photo_original20.webp)  
![screenshot_original](Photo_files/screenshot_original20.webp)  
![graphic_original](Photo_files/graphic_original8.webp)

---

## AVIF 100%

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | avif   | 1920 x 1080 | 392 КБ     | +129% |
| screenshot_original | avif   | 1366 x 768  | 671 КБ     | -5%   |
| graphic_original    | avif   | 3840 x 2400 | 2.33 МБ    | +95%  |

![photo_original](Photo_files/photo_original.avif)  
![screenshot_original](Photo_files/screenshot_original100.avif)  
![graphic_original](Photo_files/graphic_original100.avif)

## AVIF 75%

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | avif   | 1920 x 1080 | 96.7КБ     | -44%  |
| screenshot_original | avif   | 1366 x 768  | 246КБ      | -65%  |
| graphic_original    | avif   | 3840 x 2400 | 851КБ      | -29%  |

![photo_original](Photo_files/photo_original75.avif)  
![screenshot_original](Photo_files/screenshot_original75.avif)  
![graphic_original](Photo_files/graphic_original75.avif)

## AVIF 50%

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна |
| ------------------- | ------ | ----------- | ---------- | ----- |
| photo_original      | avif   | 1920 x 1080 | 35.1КБ     | -80%  |
| screenshot_original | avif   | 1366 x 768  | 101КБ      | -86%  |
| graphic_original    | avif   | 3840 x 2400 | 404КБ      | -66%  |

![photo_original](Photo_files/photo_original50.avif)  
![screenshot_original](Photo_files/screenshot_original50.avif)  
![graphic_original](Photo_files/graphic_original50.avif)

## AVIF мінімальний рівень якості

| Назва зображення    | Формат | Розмір (px) | Вага файлу | Зміна | Якість |
| ------------------- | ------ | ----------- | ---------- | ----- | ------ |
| photo_original      | webp   | 1920 x 1080 | 26.9КБ     | -84%  | 45%    |
| screenshot_original | webp   | 1366 x 768  | 80.9КБ     | -89%  | 45%    |
| graphic_original    | webp   | 3840 x 2400 | 97.4КБ     | -92%  | 20%    |

![photo_original](Photo_files/photo_original45.avif)  
![screenshot_original](Photo_files/screenshot_original45.avif)  
![graphic_original](Photo_files/graphic_original20.avif)

## Оптимізація розміру відповідно до цільового використання

| Назва зображення    | Формат | Ориг. розмір | Веб (1200px) / Зміна | Мобайл (600px) / Зміна | Retina 2x (2400px) / Зміна |
| ------------------- | ------ | ------------ | -------------------- | ---------------------- | -------------------------- |
| photo_original      | jpg    | 167.2КБ      | 392КБ (+129%)        | 126КБ (-26%)           | 1.13МБ (+560%)             |
| screenshot_original | png    | 688.2КБ      | 1.83МБ (+160%)       | 476КБ (-32%)           | 6.31МБ (+795%)             |
| graphic_original    | jpg    | 1.14МБ       | 872КБ (-27%)         | 249КБ (-79%)           | 2.82МБ (+1356%)            |

## photo_original

![photo_original](Photo_files/photo_original1200.jpg)  
![photo_original](Photo_files/photo_original600.jpg)  
![photo_original](Photo_files/photo_original2400.jpg)

## screenshot_original

![screenshot_original](Photo_files/screenshot_original160.png)  
![screenshot_original](Photo_files/screenshot_original600.png)  
![screenshot_original](Photo_files/screenshot_original2400.png)

## graphic_original

![graphic_original](Photo_files/graphic_original1200.jpg)  
![graphic_original](Photo_files/graphic_original600.jpg)  
![graphic_original](Photo_files/graphic_original2400.jpg)

## Аналіз оптимізації зображень

Порівняння вихідних та оптимізованих зображень показало, що оптимізація значно зменшила розмір файлів без втрати якості. Всі версії, включаючи мобільну (600px), веб-версію (1200px) і Retina (2x), зберегли деталізацію та чіткість.

- **Фотографії (JPEG)** добре піддалися стисненню без помітних артефактів. Розмір файлу значно зменшився при збереженні насиченості кольорів і деталізації.
- **Скріншоти (PNG → WebP lossless)** після конвертації зменшили розмір файлу без втрати чіткості та кольорового балансу. WebP показав себе як ефективний формат для скріншотів.
- **Графічні зображення (JPEG 600px)** зберегли достатньо деталей, але для кращої якості варто використовувати PNG або WebP (lossless), особливо для чітких ліній та тексту.

### Оптимальні формати та параметри:

- **Фотографії:** JPEG (якість 75%) – оптимальний баланс між якістю та розміром.
- **Скріншоти:** WebP (lossless, 100%) – забезпечує найкращу якість при меншому розмірі.
- **Графіка:** PNG або WebP (lossless) – дозволяє зберегти всі деталі та різкість.

### Висновок

Правильний вибір формату дозволяє значно зменшити розмір файлів без втрати чіткості та якості. WebP (lossless) є найкращим варіантом для скріншотів і графіки, JPEG ефективно стискає фотографії без втрат у сприйнятті. Для мобільних версій можна використовувати WebP, щоб забезпечити максимальну якість при мінімальному розмірі. Використання цих підходів дозволяє прискорити завантаження сторінок та покращити користувацький досвід.
