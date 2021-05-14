- phpMyAdmin SQL Dump
- الإصدار 4.9.0.1
- https://www.phpmyadmin.net/
-
- المضيف: المضيف المحلي
- وقت الإنتاج: 14 سبتمبر 2019 الساعة 03:42 مساءً
- إصدار الخادم: 10.4.6-MariaDB
- إصدار PHP: 7.3.9

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO" ،
تعيين AUTOCOMMIT = 0 ؛
بدء المعاملة ؛
تعيين المنطقة الزمنية = "+00: 00" ؛


/ *! 40101 SETOLD_CHARACTER_SET_CLIENT =CHARACTER_SET_CLIENT * / ؛
/ *! 40101 SETOLD_CHARACTER_SET_RESULTS =CHARACTER_SET_RESULTS * / ؛
/ *! 40101 SETOLD_COLLATION_CONNECTION =COLLATION_CONNECTION * / ؛
/ *! 40101 SET NAMES utf8mb4 * / ؛

-
- قاعدة البيانات: `sn`
-

- ------------------------------------------------ --------

-
- هيكل الجدول لجدول "التعليقات"
-

إنشاء جدول "تعليقات" (
  `c_id` bigint (50) ليس فارغًا ،
  `c_author_id` العلامة التجارية (11) NOT NULL ،
  `c_post_id` كبير الحجم (11) NOT NULL ،
  مجموعة الأحرف `c_content` varchar (10000) utf8mb4 ليست فارغة ،
  `c_edited` int (11) NOT NULL DEFAULT 0 ،
  "c_time_edited" varchar (100) CHARACTER SET utf8mb4 NOT NULL DEFAULT '0' ،
  `c_time` int (11) NOT NULL
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول للجدول "متابعة"
-

إنشاء جدول "متابعة" (
  `id` bigint (11) NOT NULL ،
  "uf_one" بيجينت (11) ليس فارغًا ،
  "uf_two" bigint (11) ليس NULL
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول لجدول "الإعجابات"
-

إنشاء جدول "الإعجابات" (
  `id` bigint (11) NOT NULL ،
  (11) ليس فارغًا ،
  `post_id` bigint (11) NOT NULL
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- بنية الجدول لجدول "الرسائل"
-

إنشاء جدول "رسائل" (
  `id` int (11) NOT NULL ،
  `m_id` bigint (11) NOT NULL ،
  `message` varchar (1538) CHARACTER SET utf8mb4 NOT NULL ،
  "m_from" بيجينت (11) ليس فارغًا ،
  `m_to` bigint (11) NOT NULL ،
  `m_time` int (11) NOT NULL ،
  `m_seen` int (11) ليس NULL افتراضيًا 0
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول للجدول "mynotepad"
-

إنشاء جدول "mynotepad" (
  `main_id` int (11) NOT NULL ،
  `id` bigint (20) NOT NULL ،
  موضوع "author_id" كبير (11) NOT NULL ،
  "note_title" varchar (1000) مجموعة أحرف utf8mb4 ليست فارغة ،
  "note_content" varchar (10000) CHARACTER SET utf8mb4 NOT NULL ،
  "note_time" int (11) NOT NULL
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول لجدول "الإخطارات"
-

إنشاء جدول "الإخطارات" (
  `id` int (11) NOT NULL ،
  `n_id` bigint (11) NOT NULL ،
  `from_id` bigint (11) NOT NULL ،
  `for_id` bigint (11) NOT NULL ،
  `notifyType_id` كبير الحجم (11) NOT NULL ،
  `notifyType` varchar (100) NOT NULL ،
  `مرئي` int (11) ليس افتراضيًا 0 ،
  "time" int (11) NOT NULL
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول للجدول `r_star`
-

إنشاء جدول "r_star" (
  `id` bigint (11) NOT NULL ،
  `u_id` bigint (11) NOT NULL ،
  `p_id` بيجينت (11) ليس فارغًا
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول للجدول "محفوظ"
-

إنشاء جدول "محفوظ" (
  `main_id` int (11) NOT NULL ،
  `id` bigint (20) NOT NULL ،
  موضوع `post_id` (11) ليس فارغًا ،
  `user_saved_id` العلامة التجارية الكبيرة (11) NOT NULL ،
  `save_time` int (11) NOT NULL
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول لجدول "التسجيل"
-

إنشاء جدول "تسجيل" (
  `main_id` int (11) NOT NULL ،
  `id` bigint (50) NOT NULL ،
  مجموعة الأحرف `Fullname` varchar (1000) utf8mb4 ليست فارغة ،
  "اسم المستخدم" varchar (1000) مجموعة الأحرف utf8mb4 ليست فارغة ،
  "البريد الإلكتروني" varchar (1000) مجموعة الأحرف utf8mb4 ليست فارغة ،
  "كلمة المرور" varchar (1000) مجموعة الأحرف utf8mb4 ليست فارغة ،
  عدد "المتابعين" int (100) ليس NULL افتراضيًا 0 ،
  "صورة المستخدم" varchar (300) مجموعة الأحرف utf8mb4 ليست فارغة ،
  `user_cover_photo` varchar (300) CHARACTER SET utf8mb4 DEFAULT NULL ،
  مجموعة أحرف `المدرسة` varchar (1000) utf8mb4 DEFAULT NULL ،
  مجموعة الأحرف `work` varchar (1000) utf8mb4 DEFAULT NULL ،
  `work0` varchar (1000) مجموعة أحرف utf8mb4 DEFAULT NULL ،
  مجموعة أحرف `country` varchar (1000) utf8mb4 DEFAULT NULL ،
  "عيد ميلاد" varchar (1000) مجموعة الأحرف utf8mb4 DEFAULT NULL ،
  `تحقق` int (11) ليس فارغًا افتراضيًا 0 ،
  varchar (1000) مجموعة الأحرف "الموقع" utf8mb4 الافتراضي NULL ،
  مجموعة الأحرف `bio` varchar (1000) utf8mb4 DEFAULT NULL ،
  مجموعة الأحرف `admin` varchar (50) utf8mb4 DEFAULT NULL ،
  مجموعة الأحرف `` gender` varchar (1000) utf8mb4 NOT NULL ،
  "login_attempts` int (11) الافتراضي 0 ،
  "اللغة" varchar (100) مجموعة الأحرف utf8mb4 DEFAULT NULL ،
  عدد العمليات "aSetup" int (11) NOT NULL افتراضي 0 ،
  "online" int (100) ليس افتراضيًا 0
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول لجدول "supportbox"
-

إنشاء جدول "supportbox" (
  `id` int (11) NOT NULL ،
  `r_id` bigint (11) ليس فارغًا ،
  `from_id` bigint (11) NOT NULL ،
  `for_id` bigint (11) NOT NULL ،
  "r_type" varchar (100) مجموعة أحرف utf8mb4 ليست فارغة ،
  `subject` varchar (1000) CHARACTER SET utf8mb4 NOT NULL ،
  `report` varchar (1000) CHARACTER SET utf8mb4 NOT NULL ،
  `r_time` int (11) NOT NULL ،
  مجموعة الأحرف `r_replay` varchar (1000) utf8mb4 DEFAULT NULL ،
  `r_replay_time` int (11) DEFAULT NULL ،
  `status` int (11) NOT NULL افتراضي 0
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول للجدول "typing_m"
-

إنشاء جدول "كتابة_ م" (
  `id` bigint (11) NOT NULL ،
  "t_from" بيجينت (11) ليس فارغًا ،
  `t_to` bigint (11) NOT NULL
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

- ------------------------------------------------ --------

-
- هيكل الجدول للجدول "wpost"
-

إنشاء جدول "wpost" (
  `post_id` bigint (50) ليس فارغًا ،
  موضوع "author_id" كبير (11) NOT NULL ،
  `post_img` varchar (1000) مجموعة أحرف utf8mb4 DEFAULT NULL ،
  "post_time" int (11) NOT NULL ،
  "post_content" مجموعة أحرف النص المتوسط ​​utf8mb4 ليست فارغة ،
  مجموعة الأحرف "p_title" varchar (1000) utf8mb4 DEFAULT NULL ،
  `p_likes` int (100) ليس NULL افتراضيًا 0 ،
  `p_privacy` int (11) ليس NULL افتراضيًا 0 ،
  "مشترك" varchar (1000) CHARACTER SET utf8mb4 DEFAULT NULL
) المحرك = مجموعة InnoDB الافتراضية = latin1 ؛

-
- فهارس للجداول الملغاة
-

-
- فهارس لجدول "التعليقات"
-
تعديل الجدول "التعليقات"
  إضافة مفتاح أساسي (`c_id`) ؛

-
- فهارس الجدول "متابعة"
-
تعديل الجدول "متابعة"
  إضافة مفتاح أساسي (`id`) ؛

-
- فهارس لجدول "الإعجابات"
-
تعديل الجدول "الإعجابات"
  إضافة مفتاح أساسي (`id`) ؛

-
- فهارس لجدول "الرسائل"
-
ALTER TABLE "الرسائل"
  إضافة مفتاح أساسي (`id`) ؛

-
- فهارس الجدول "mynotepad"
-
تعديل الجدول "mynotepad"
  إضافة مفتاح أساسي (`main_id`) ؛

-
- فهارس لجدول "الإخطارات"
-
ALTER TABLE "الإخطارات"
  إضافة مفتاح أساسي (`id`) ؛

-
- فهارس الجدول "r_star"
-
تعديل الجدول `r_star`
  إضافة مفتاح أساسي (`id`) ؛

-
- فهارس الجدول "محفوظ"
-
ALTER TABLE `حفظ`
  إضافة مفتاح أساسي (`main_id`) ؛

-
- فهارس جدول "التسجيل"
-
تعديل الجدول "الاشتراك"
  إضافة مفتاح أساسي (`main_id`) ؛

-
- فهارس الجدول "supportbox"
-
ALTER TABLE "supportbox"
  إضافة مفتاح أساسي (`id`) ؛

-
- فهارس الجدول "typing_m"
-
ALTER TABLE `typing_m`
  إضافة مفتاح أساسي (`id`) ؛

-
- فهارس الجدول "wpost"
-
تعديل الجدول "wpost"
  إضافة مفتاح أساسي (`post_id`) ؛

-
- AUTO_INCREMENT للمناضد المغمورة
-

-
- AUTO_INCREMENT لجدول "التعليقات"
-
تعديل الجدول "التعليقات"
  تعديل عدد الأحرف الكبيرة `c_id` (50) NOT NULL AUTO_INCREMENT ؛

-
- AUTO_INCREMENT للجدول "متابعة"
-
تعديل الجدول "متابعة"
  تعديل `id` bigint (11) NOT NULL AUTO_INCREMENT ، AUTO_INCREMENT = 16 ؛

-
- AUTO_INCREMENT لجدول "الإعجابات"
-
تعديل الجدول "الإعجابات"
  تعديل `id` bigint (11) NOT NULL AUTO_INCREMENT ، AUTO_INCREMENT = 12 ؛

-
- AUTO_INCREMENT لجدول "الرسائل"
-
ALTER TABLE "الرسائل"
  تعديل `id` int (11) NOT NULL AUTO_INCREMENT ، AUTO_INCREMENT = 7 ؛

-
- AUTO_INCREMENT للجدول "mynotepad"
-
تعديل الجدول "mynotepad"
  تعديل `main_id` int (11) NOT NULL AUTO_INCREMENT ؛

-
- AUTO_INCREMENT لجدول "الإخطارات"
-
ALTER TABLE "الإخطارات"
  تعديل `id` int (11) NOT NULL AUTO_INCREMENT ، AUTO_INCREMENT = 19 ؛

-
- AUTO_INCREMENT للجدول `r_star`
-
تعديل الجدول `r_star`
  تعديل `id` bigint (11) NOT NULL AUTO_INCREMENT ، AUTO_INCREMENT = 4 ؛

-
- AUTO_INCREMENT للجدول "محفوظ"
-
ALTER TABLE `حفظ`
  تعديل `main_id` int (11) NOT NULL AUTO_INCREMENT ، AUTO_INCREMENT = 2 ؛

-
- AUTO_INCREMENT لجدول "التسجيل"
-
تعديل الجدول "الاشتراك"
  تعديل `main_id` int (11) NOT NULL AUTO_INCREMENT ، AUTO_INCREMENT = 14 ؛

-
- AUTO_INCREMENT للجدول "صندوق الدعم"
-
ALTER TABLE "supportbox"
  تعديل `id` int (11) NOT NULL AUTO_INCREMENT ؛

-
- AUTO_INCREMENT للجدول "typing_m"
-
ALTER TABLE `typing_m`
  تعديل `id` bigint (11) NOT NULL AUTO_INCREMENT ، AUTO_INCREMENT = 8 ؛
ارتكب؛

/ *! 40101 SET CHARACTER_SET_CLIENT = @ OLD_CHARACTER_SET_CLIENT * / ؛
/ *! 40101 SET CHARACTER_SET_RESULTS = @ OLD_CHARACTER_SET_RESULTS * / ؛
/ *! 40101 SET COLLATION_CONNECTION = @ OLD_COLLATION_CONNECTION * / ؛
# bubble
