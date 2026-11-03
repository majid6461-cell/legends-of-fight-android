# گزارش نهایی آزمون — LEGENDS OF FIGHT v0.1.0

تاریخ: ۳ نوامبر ۲۰۲۶

## اجرای CI

- نتیجه: موفق (هر دو Job)
- Run #12: https://github.com/majid6461-cell/legends-of-fight-android/actions/runs/41626668554
- Commit: db591fa69d4d0d9e2693f0b4b3a90a2684071ef3
- Godot: 4.7.2.stable.official.ed1daf0bf
- Import پروژه و Parse اسکریپت‌ها: PASS؛ مرحلهٔ Import بدون SCRIPT ERROR پایان یافت.
- Smoke Test: PASS؛ ۱۲ پروفایل مبارز، ۸ میدان، فیلدهای ضروری و یکتایی نام‌ها بررسی شدند.
- Export APK اندروید: PASS.
- بررسی بسته با aapt: PASS؛ شناسهٔ com.legends.fight، نسخهٔ 0.1.0، حداقل SDK=24 و Target SDK=36.
- ABIهای خروجی: arm64-v8a و x86_64.

## نصب و اجرای شبیه‌ساز

- Job: Install and launch on Android emulator — SUCCESS.
- شبیه‌ساز: Android Emulator، API 35، تصویر google_apis، معماری x86_64، پروفایل Pixel 2.
- نصب با adb install: موفق.
- اجرای لانچر با adb shell monkey: موفق.
- برنامه ۱۵ ثانیه پس از اجرا فعال ماند؛ فرمان pidof شناسهٔ فرایند 2176 را برگرداند.
- بررسی لاگ: هیچ FATAL EXCEPTION در AndroidRuntime مشاهده نشد.

## مشخصات فایل APK نهایی

- نام: LegendsOfFight.apk
- حجم: 57,148,985 بایت
- SHA-256: ec5ee9f962fea2b7eb90d220bdba53e91c15a4af5a2521d0a6a71caa200e6c3c
- Artifact ID: 13225089606
- دانلود: https://github.com/majid6461-cell/legends-of-fight-android/actions/runs/41626668554/artifacts/13225089606
- صحت ساختار ZIP/APK: PASS؛ آزمون unzip -t بدون خطا پایان یافت.

## موارد خارج از آزمون

- نصب و بازی روی گوشی فیزیکی انجام نشده است.
- تست دستی تمام حالت‌ها، تست کنترل دونفره لمسی، پایداری طولانی‌مدت، مصرف باتری، دما و FPS در مدل‌های مختلف گوشی انجام نشده است.
- APK با کلید Debug امضا شده؛ انتشار تجاری نیازمند keystore خصوصی Release است.

## دامنهٔ محصول

این پروژه MVP است. ۱۲ مبارز و ۸ محیط، پروفایل‌ها و مدل‌های رویه‌ای Low-Poly دارند. این نسخه از نظر مدل‌سازی، ریگ، انیمیشن، صدا و پرداخت بصری معادل بازی Tekken نیست. انیمیشن استخوانی حرفه‌ای، صداگذاری اختصاصی، ذخیره‌سازی دائمی پیشرفت و پولیش کامل سیستم مبارزه مراحل بعدی توسعه‌اند.
