# সেলফ প্র্যাকটিস (Self Practice) অ্যান্ড্রয়েড প্রজেক্ট - বিশ্লেষণ ও সমাধান

## ১. প্রজেক্ট পরিচিতি
এই প্রকল্পটি একটি অ্যান্ড্রয়েড ওয়েবভিউ (WebView) অ্যাপ্লিকেশন, যা স্থানীয় HTML/CSS/JS এসেট (file:///android_asset/index.html) নিরাপদে লোড করে কুইজ ও সেলফ প্র্যাকটিস অনুশীলন পরিবেশনা করে।

## ২. শনাক্তকৃত ত্রুটিসমূহ ও সংশোধন:
১. **Android 12+ এ ক্র্যাশ সমস্যা**:
   - কারণ: Android 12 (API 31) থেকে লঞ্চার Activity-তে 'android:exported="true"' থাকা বাধ্যতামূলক।
   - সমাধান: AndroidManifest.xml-এ MainActivity-তে 'android:exported="true"' যুক্ত করা হয়েছে।

২. **DOM Storage (localStorage) নিষ্ক্রিয় থাকা**:
   - কারণ: ওয়েবভিউতে ডিফল্টভাবে localStorage বন্ধ থাকে। ফলে কুইজের স্কোর ও অগ্রগতি সেভ হতে গিয়ে ক্র্যাশ করত।
   - সমাধান: MainActivity.java-তে 'webSettings.setDomStorageEnabled(true)' যুক্ত করা হয়েছে।

৩. **ব্যাক বাটন চাপলে অ্যাপ বন্ধ হয়ে যাওয়া**:
   - কারণ: হার্ডওয়্যার ব্যাক বাটন চাপলে ওয়েব পেজের পূর্ববর্তী পাতায় ফিরে যাওয়ার কোড ছিল না।
   - সমাধান: 'webView.canGoBack()' হ্যান্ডলার যুক্ত করা হয়েছে।

৪. **ক্লিয়ারটেক্সট ট্রাফিক ব্লক (Android 9+)**:
   - কারণ: HTTP লিঙ্ক সরাসরি ব্লক থাকত।
   - সমাধান: 'android:usesCleartextTraffic="true"' সক্রিয় করা হয়েছে।

## ৩. যেভাবে APK তৈরি করবেন:
- **পদ্ধতি ১ (GitHub Actions - সম্পূর্ণ ফ্রি ও ক্লাউডে)**:
  ১. "Download Fixed Project ZIP" বাটনে ক্লিক করে জিপ ফাইল ডাউনলোড করুন।
  ২. আপনার GitHub অ্যাকাউন্টে একটি রিপোজিটরি তৈরি করে ফাইলগুলো আপলোড করুন।
  ৩. অ্যাকশনস (Actions) ট্যাবে স্বয়ংক্রিয়ভাবে ২ মিনিটের মধ্যে 'app-debug.apk' তৈরি হবে এবং ডাউনলোড লিঙ্ক পেয়ে যাবেন।

- **পদ্ধতি ২ (Android Studio)**:
  ১. জিপ ফাইল আনজিপ করে Android Studio দিয়ে 'Open Project' করুন।
  ২. মেনু থেকে Build -> Build Bundle(s) / APK(s) -> Build APK(s) চাপুন।
  ৩. 'locate' এ ক্লিক করে 'app-debug.apk' পেয়ে যাবেন।

- **পদ্ধতি ৩ (টার্মিনাল)**:
  ১. প্রজেক্ট ফোল্ডারে টার্মিনাল খুলে লিখুন: './gradlew assembleDebug'
  ২. APK লোকেশন: app/build/outputs/apk/debug/app-debug.apk

## ৪. অ্যান্ড্রয়েড ফোনে ইনস্টল করার নিয়ম:
১. APK ফাইলটি আপনার ফোনে ডাউনলোড করুন।
২. ফাইলে ক্লিক করুন। "Install Unknown Apps" অনুমতি চাইলে 'Allow from this source' চালু করুন।
৩. Google Play Protect যদি "Unrecognized app" বা সতর্কতা দেয়, তবে "More details" চেপে "Install anyway" চাপুন।
৪. ইনস্টলেশন সম্পন্ন হলে অ্যাপটি ওপেন করুন!
