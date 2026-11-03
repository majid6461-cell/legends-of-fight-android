# گزارش نهایی آزمون — LEGENDS OF FIGHT v0.1.0

تاریخ: ۳ نوامبر ۲۰۲۶

## اجرای CI

- نتیجه: موفق (هر دو Job)
- Run #13: https://github.com/majid6461-cell/legends-of-fight-android/actions/runs/41626883972
- Commit: db591fa69d4d0d9e2693f0b4b3a90a2684071ef3
- Godot: 4.7.2.stable.official.ed1daf0bf
- Import و Parse اسکریپت‌ها: PASS؛ Import بدون SCRIPT ERROR پایان یافت.
- Smoke Test: PASS؛ ۱۲ پروفایل مبارز، ۸ میدان، فیلدهای ضروری و یکتایی نام‌ها بررسی شدند.
- Export APK: PASS.
- مشخصات بسته با aapt: PASS؛ شناسه com.legends.fight، نسخه 0.1.0، حداقل SDK=24 و Target SDK=36.
- معماری‌های خروجی: arm64-v8a و x86_64.

## نصب و اجرای شبیه‌ساز

- Job: Install and launch on Android emulator — SUCCESS.
- شبیه‌ساز: Android Emulator، API 35، تصویر google_apis، معماری x86_64، پروفایل Pixel 2.
- نصب با adb install: موفق.
- اجرای لانچر با adb shell monkey: موفق.
- برنامه ۱۵ ثانیه پس از اجرا فعال ماند؛ pidof شناسهٔ فرایند ۲۱۷۶ را برگرداند.
- بررسی لاگ: هیچ FATAL EXCEPTION در AndroidRuntime مشاهده نشد.

## مشخصات فایل APK نهایی

- نام: LegendsOfFight.apk
- حجم: 57,148,985 بایت
- SHA-256: 2e7c125908b0a0572e7684a055356a50c1ad1dd8d4db61382a8100add66c90b8
- Artifact ID: 13226666054
- دانلود: https://github.com/majid6461-cell/legends-of-fight-android/actions/runs/41626883972/artifacts/13226666054
- صحت ZIP/APK: PASS؛ آزمون unzip -t بدون خطا پایان یافت.

## موارد خارج از آزمون

- نصب و بازی روی گوشی فیزیکی انجام نشده است.
- تست دستی تمام حالت‌ها، کنترل دونفره لمسی، پایداری طولانی‌مدت، مصرف باتری، دما و FPS روی مدل‌های مختلف گوشی انجام نشده است.
- APK با کلید Debug امضا شده؛ انتشار تجاری نیازمند keystore خصوصی Release است.

## دامنه محصول

این نسخه MVP است. ۱۲ مبارز و ۸ محیط دارای پروفایل و مدل‌های رویه‌ای Low-Poly هستند. این نسخه از نظر مدل‌سازی، ریگ، انیمیشن، صدا و پرداخت بصری معادل بازی Tekken نیست. انیمیشن استخوانی حرفه‌ای، صداگذاری اختصاصی، ذخیره‌سازی دائمی پیشرفت و پولیش کامل سیستم مبارزه مراحل بعدی توسعه‌اند.
