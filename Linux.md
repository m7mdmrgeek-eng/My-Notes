# Linux OS

## Linux Structure

Linux هو نظام تشغيل يُستخدم في الحواسيب الشخصية، السيرفرات، وحتى الأجهزة المحمولة. يُعتبر **Linux** أحد أهم أعمدة الأمن السيبراني بفضل قوته، مرونته، وكونه **مفتوح المصدر**.

في هذا القسم سنغطي:
- هيكل Linux
- تاريخه
- فلسفته
- معماريته
- نظام الملفات (File System Hierarchy)

يمكنك التفكير في Linux كأول درس في قيادة سيارة جديدة — فهم أساسياتها ومكوناتها.

### ما هو Linux؟

**Linux** هو نظام تشغيل (Operating System) مثل Windows وmacOS وAndroid.  
نظام التشغيل هو البرمجية التي تدير كل موارد الأجهزة (Hardware) وتتوسط بين البرامج والأجهزة.

يتميز Linux بوجود مئات **التوزيعات (Distros)** المبنية على نواة Linux واحدة، وكل توزيعة مصممة لأغراض مختلفة.

### History of Linux

- **1970**: إصدار نظام **Unix** بواسطة Ken Thompson و Dennis Ritchie في AT&T.
- **1977**: إصدار **Berkeley Software Distribution (BSD)**.
- **1983**: بداية مشروع **GNU** بواسطة **Richard Stallman**، وإنشاء رخصة **GPL**.
- **1991**: **Linus Torvalds** (طالب فنلندي) بدأ تطوير نواة Linux كمشروع شخصي.

**اليوم:**
- نواة Linux تحتوي على أكثر من **23 مليون سطر كود**.
- مرخصة تحت **GNU General Public License v2**.
- يوجد أكثر من **600 توزيعة** Linux.
- أشهر التوزيعات: **Ubuntu, Debian, Fedora, Red Hat, Linux Mint, Manjaro, Parrot OS, Kali Linux**.

**لماذا Linux قوي في الأمن السيبراني؟**
- أكثر استقرارًا وأمانًا من Windows.
- أقل عرضة للـ Malware.
- تحديثات متكررة وسريعة.
- مفتوح المصدر → يمكن فحصه وتعديله بحرية.
- نظام Android مبني على نواة Linux → أكثر نظام منتشر في العالم.

> في هذا الموديول، سنعمل بشكل أساسي على **Parrot OS** (توزيعة مبنية على Debian وتركز على الأمان والخصوصية والتطوير).

### Linux Philosophy

تعتمد فلسفة Linux على **البساطة، التجزئة، والانفتاح**.

#### المبادئ الخمسة الأساسية:

| المبدأ                              | الوصف |
|------------------------------------|------|
| **Everything is a file**           | كل شيء في النظام (أجهزة، عمليات، شبكات) يُعامل كملف |
| **Small, single-purpose programs** | برامج صغيرة تقوم بعمل واحد فقط بكفاءة |
| **Ability to chain programs**      | ربط البرامج مع بعضها (piping) لتنفيذ مهام معقدة |
| **Avoid captive user interfaces**  | التركيز الرئيسي على الـ Terminal (Shell) |
| **Configuration in text files**    | الإعدادات مخزنة في ملفات نصية (مثال: `/etc/passwd`) |

### Linux Components

| المكون                  | الوصف |
|------------------------|------|
| **Bootloader**         | يدير عملية الإقلاع (مثل GRUB في Parrot OS) |
| **OS Kernel**          | النواة — تدير موارد الأجهزة (CPU, Memory, I/O) |
| **Daemons**            | خدمات تعمل في الخلفية |
| **OS Shell**           | واجهة سطر الأوامر (Bash, Zsh, Fish...) |
| **Graphics Server**    | X Server — يدير الواجهة الرسومية |
| **Window Manager / DE**| GNOME, KDE, Cinnamon, MATE... |
| **Utilities**          | الأدوات والبرامج المساعدة |

### Linux Architecture

| الطبقة               | الوصف |
|---------------------|------|
| **Hardware**        | الأجهزة الفعلية (CPU, RAM, HDD...) |
| **Kernel**          | النواة — تتحكم في الموارد وتعزل العمليات |
| **Shell**           | واجهة سطر الأوامر |
| **System Utilities**| الأدوات التي تستخدم وظائف النظام |

### File System Hierarchy (FHS)

Linux يتبع هيكل شجري موحد يُسمى **Filesystem Hierarchy Standard**.

| المسار     | الوصف |
|-----------|------|
| `/`       | الدليل الجذر (Root Directory) |
| `/bin`    | الأوامر الأساسية |
| `/boot`   | ملفات الإقلاع والكيرنل |
| `/dev`    | ملفات الأجهزة |
| `/etc`    | ملفات التكوين والإعدادات |
| `/home`   | مجلدات المستخدمين |
| `/lib`    | المكتبات المشتركة |
| `/media`  | الأجهزة الخارجية (USB, CD...) |
| `/mnt`    | نقطة تركيب مؤقتة |
| `/opt`    | برامج خارجية (Third-party) |
| `/root`   | مجلد المستخدم root |
| `/sbin`   | أوامر إدارة النظام |
| `/tmp`    | ملفات مؤقتة (تُمسح عند الإقلاع) |
| `/usr`    | البرامج، المكتبات، والمستندات |
| `/var`    | ملفات متغيرة (Logs, Mail, Web files, Cron...) |

---

## Section Linux Distributions & Introduction to Shell

### Linux Distributions (Distros)

التوزيعات هي أنظمة تشغيل مبنية على نواة Linux، لكنها تختلف في الحزم، الواجهة، والأدوات.

#### أشهر التوزيعات العامة:
- Ubuntu
- Fedora
- Debian
- Red Hat Enterprise Linux (RHEL)
- CentOS
- Linux Mint

#### التوزيعات الشائعة في مجال الأمن السيبراني:
- **Kali Linux**
- **Parrot OS**
- **BlackArch**
- **BackBox**
- **Pentoo**
- Debian
- Ubuntu

**الفرق الرئيسي** بين التوزيعات يكمن في:
- الحزم المثبتة مسبقًا
- مدير الحزم (Package Manager)
- واجهة المستخدم
- الاستخدام المستهدف (Desktop / Server / Security)

> **نصيحة**: Kali Linux هي الأشهر بين متخصصي الأمن، بينما Ubuntu و Debian أكثر استقرارًا للسيرفرات والاستخدام اليومي.

### Introduction to the Shell

**الـ Shell** هو أهم جزء يجب إتقانه في Linux، خاصة أن معظم السيرفرات تعمل عليه.

الـ **Terminal** (Terminal Emulator) هو البرنامج الذي يتيح لك التفاعل مع الـ Shell.

#### أشهر Shells:
- **Bash** (Bourne-Again Shell) — الأكثر استخدامًا
- Zsh
- Fish
- Tcsh / Csh
- Ksh

### Bash Prompt

الـ Prompt هو السطر الذي يظهر قبل كتابة الأمر.

**أمثلة:**
```
username@hostname[~]$
```
تمام يا محمد، خلاص هعدل الستايل من دلوقتي.

العربي هيبقى **عامية مصرية سيكا** (زي ما بنتكلم في الشارع أو بنراجع مع بعض)، والإنجليزي هيفضل رسمي ومنسق زي ما هو.

هنا **الجزء اللي بعته (Bash Prompt)** منسق بالطريقة الجديدة اللي طلبتها:

---
## Bash Prompt

الـ Bash Prompt حاجة بسيطة وسهلة الفهم. بشكل افتراضي بيوريك معلومات زي اسم المستخدم (مين أنت)، اسم الجهاز (الـ hostname)، والمجلد اللي واقف فيه دلوقتي.  
يعني سطر نص بيظهر قدامك عشان يقولك "النظام جاهز، يلا اكتب الأمر".

الـ Prompt بيظهر في سطر جديد، والمؤشر (الخط الوامض) بيستنى بعديه على طول.

### أشكال الـ Prompt الشائعة

**الشكل الطبيعي:**

```bash
<username>@<hostname><current working directory>$
```

لما تكون في المجلد الرئيسي (Home Directory) بيبقى كده:

```bash
<username>@<hostname>[~]$
```

- الـ **دولار `$`** ده معناه إنك مستخدم عادي (مش root).
- لما تسجل دخول كـ **root**، الرمز بيتغير لـ **الهاش `#`** ويبقى شكله كده:

```bash
root@htb[/htb]#
```

**لما تكون شغال على Reverse Shell أو Shell على الجهاز المستهدف:**
أحيانًا الـ Prompt بيبقى فاضي خالص، مش بيظهر اسم المستخدم ولا اسم الجهاز ولا حتى المسار. ده غالبًا بسبب إن متغير `PS1` مش مضبوط كويس. في الحالة دي بتشوف كده:

**مستخدم عادي:**

```bash
$
```

**روت :**

```bash
#
```

### PS1 Variable

الـ `PS1` ده المتغير اللي بيتحكم في شكل الـ Prompt بالكامل.  
زي قالب بتقدر تغير فيه اللي تحبه: اسمك، اسم الجهاز، المسار، الوقت، الألوان... إلخ.

بتقدر تضيف حاجات زي عنوان الـ IP، التاريخ، والوقت، وحتى لو آخر أمر نجح ولا لأ.  
ده بيفيدك جدًا أثناء Penetration Testing عشان تقدر تتابع خطواتك بسهولة.

### أحرف خاصة تقدر تستخدمها في الـ PS1

| الحرف          | معناه بالعامية |
|---------------|----------------|
| `\d`          | التاريخ (زي Mon Feb 6) |
| `\D{%Y-%m-%d}`| التاريخ بشكل YYYY-MM-DD |
| `\H`          | اسم الجهاز كامل |
| `\j`          | عدد المهام اللي الشيل شغال عليها |
| `\n`          | سطر جديد |
| `\t`          | الوقت دلوقتي (24 ساعة) |
| `\T`          | الوقت (12 ساعة) |
| `\@`          | الوقت بالـ AM/PM |
| `\u`          | اسم المستخدم |
| `\w`          | المسار الحالي كامل |

### نصيحة سريعة

تقدر تخصص شكل الـ Terminal كله (ألوان، خطوط، ثيمات...) عشان تبقى مرتاح وهي بتشتغل.  
تخصيص الـ Prompt بالتفصيل خارج نطاق الموديول ده، بس في أدوات حلوة زي **bash-prompt-generator** و **Powerline** تقدر تجربها وتعدل الـ Prompt زي ما تحب.

---
تمام يا محمد! 🔥  

هنا الجزء الجديد (**Getting Help**) منسق بنفس الستايل اللي بتحبه، بالعامية المصرية السيكا:

---
## Getting Help

دلوقتي بعد ما بنينا أساس كويس في هيكل Linux والتوزيعات والـ Shell، خلينا نبدأ نطبق الكلام ده عمليًا.  
الوقت جاي ننزل في الـ Terminal ونستخدم الأوامر، وكمان نتعلم إزاي نطلب المساعدة لما نقابل أمر مش عارفينه.

هتلاقي نفسك كتير قدام أدوات جديدة أو أوامر فيها خيارات (options) كتير مش حافظها.  
عشان كده مهم جدًا تعرف تشتغل لوحدك وتتعرف على أي أداة بسرعة. أول طريقتين هنستخدمهم هما **man pages** و **الـ help functions**.

### أول أمر: ls

```bash
geekmo1@htb[/htb]$ ls

cacert.der  Documents  Music     Public     Videos
Desktop     Downloads  Pictures  Templates
```

الأمر `ls` بيستخدم عشان يعرض الملفات والمجلدات اللي جوا المجلد الحالي (أو أي مجلد تحدده).  
زي معظم أوامر Linux، `ls` معاه خيارات كتير تقدر تستخدمها عشان تصفي النتيجة أو تغير شكلها.

### طرق طلب المساعدة

#### 1. Manual Pages (man)

دي أهم طريقة. بتعطيك الدليل الكامل والتفصيلي لأي أمر.

**الصيغة:**

```bash
man <tool>
```

**مثال:**

```bash
geekmo1@htb[/htb]$ man ls
```

هيظهرلك الصفحة دي:

```bash
LS(1)                            User Commands                           LS(1)

NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...

DESCRIPTION
       List information about the FILEs (the current directory by default).
       ...
```

(اضغط `q` عشان تخرج)

#### 2. الـ Help Flag

طريقة سريعة عشان تشوف الخيارات بدون ما تقرأ الدليل كله.

**الصيغة:**

```bash
<tool> --help
```

**مثال:**

```bash
geekmo1@htb[/htb]$ ls --help
```

بعض الأوامر (زي `curl`) بتدعم النسخة القصيرة `-h`:

```bash
geekmo1@htb[/htb]$ curl -h
```

#### 3. Apropos (البحث في الوصف)

لو مش فاكر اسم الأمر بالظبط، `apropos` بيساعدك يدور في وصف كل الأوامر.

**الصيغة:**

```bash
apropos <keyword>
```

**مثال:**

```bash
geekmo1@htb[/htb]$ apropos sudo
```

هيطلعلك كل حاجة متعلقة بـ sudo:

```
sudo (8)             - execute a command as another user
sudo.conf (5)        - configuration for sudo front end
visudo (8)           - edit the sudoers file
...
```

### موقع مفيد جدًا

لو عندك أمر طويل ومش فاهمو كويس:

→ [https://explainshell.com/](https://explainshell.com/)

---
تمام يا محمد!  

هنا **Section 6/30** منسق كامل بالعامية المصرية السيكا زي ما طلبت:

---
## System Information

دلوقتي خلينا ندخل في التطبيق العملي عشان نتعود على الـ Terminal والـ Shell.  
متخافش، لو وقفت قدام أمر مش فاهمو تقدر دايمًا تستخدم `-h` أو `--help` أو `man` عشان تطلب مساعدة.

لأننا هنشتغل على أنظمة Linux مختلفة، لازم نعرف نجيب معلومات عن:
- تفاصيل النظام
- العمليات (Processes)
- إعدادات الشبكة
- المستخدمين والصلاحيات
- المجلدات

### أهم الأوامر لجمع معلومات النظام

| الأمر         | الوصف |
|--------------|------|
| `whoami`     | يظهر اسم المستخدم الحالي |
| `id`         | يظهر هوية المستخدم + المجموعات اللي هو فيها |
| `hostname`   | يظهر أو يعدل اسم الجهاز |
| `uname`      | يظهر معلومات عن النواة والجهاز |
| `pwd`        | يظهر المجلد الحالي اللي واقف فيه |
| `ifconfig`   | معلومات الشبكة والواجهات (قديم شوية) |
| `ip`         | أحدث أمر للشبكة (يفضل تستخدمه) |
| `netstat`    | يظهر حالة الشبكة والمنافذ |
| `ss`         | بديل أفضل وأسرع من netstat لمعرفة الـ Sockets |
| `ps`         | يظهر العمليات الشغالة |
| `who`        | يظهر المستخدمين اللي مسجلين دخول دلوقتي |
| `env`        | يظهر المتغيرات البيئية |
| `lsblk`      | يظهر الأقراص والأجهزة التخزينية |
| `lsusb`      | يظهر أجهزة USB المتصلة |
| `lsof`       | يظهر الملفات المفتوحة |
| `lspci`      | يظهر أجهزة PCI |

> معظم الأوامر دي مثبتة مسبقًا، وهي مهمة جدًا مش بس للاستخدام اليومي، لكن كمان لما بنعمل تقييم أمني أو نبحث عن ثغرات ونحاول نرفع الصلاحيات.

### تسجيل الدخول عن طريق SSH

**SSH** (Secure Shell) هو بروتوكول يسمحلك تدخل على جهاز بعيد وتنفذ أوامر عليه.  
هو الأداة المفضلة للإداريين عشان سريع وخفيف ومش بيحتاج واجهة رسومية.

**طريقة الاتصال:**

```bash
geekmo1@htb[/htb]$ ssh htb-student@[IP address]
```

بعد كده استخدم الباسورد اللي هيديهولك.

### أمثلة عملية على الجهاز

#### 1. hostname

```bash
cry0l1t3@htb[/htb]$ hostname

nixfund
```

بيطبع اسم الجهاز اللي إحنا داخلين عليه.

#### 2. whoami

```bash
cry0l1t3@htb[/htb]$ whoami

cry0l1t3
```

أسرع طريقة تعرف بيها أنت مسجل دخول بأي يوزر.  
مهم جدًا لما تاخد Reverse Shell، أول حاجة تسأل نفسك: "أنا مين دلوقتي؟"

#### 3. id

```bash
cry0l1t3@htb[/htb]$ id

uid=1000(cry0l1t3) gid=1000(cry0l1t3) groups=1000(cry0l1t3),1337(hackthebox),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),116(lpadmin),126(sambashare)
```

بيظهرلك:
- uid → رقم المستخدم
- gid → رقم المجموعة الرئيسية
- groups → كل المجموعات اللي اليوزر فيها

**ملاحظة مهمة:** لو لقيت اليوزر في مجموعة `sudo`، ده معناه إنه يقدر ينفذ أوامر بصلاحيات root → فرصة كبيرة لـ Privilege Escalation.

#### 4. uname

```bash
cry0l1t3@htb[/htb]$ uname -a

Linux box 4.15.0-99-generic #100-Ubuntu SMP Wed Apr 22 20:32:56 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
```

الأمر ده بيطلع كل المعلومات عن النظام.  
لو عايز بس إصدار النواة:

```bash
cry0l1t3@htb[/htb]$ uname -r

4.15.0-99-generic
```

المعلومة دي مهمة جدًا عشان تبحث عن exploits خاصة بالكيرنل ده.

---
## Navigation في Linux

التنقل في النظام زي استخدام الماوس بالظبط في ويندوز.  
بدون ما تعرف تتحرك كويس بين المجلدات والملفات، مش هتقدر تعمل حاجة.  
هنتعلم الأوامر اللي بنستخدمها عشان نطبع معلومات عن المجلدات والملفات، وكمان الخيارات المتقدمة اللي بتساعدنا نتحكم في الشكل اللي بنشوفه.

أحسن طريقة تتعلم حاجة جديدة هي **تجربها بنفسك**.  
هنغطي: التنقل، إنشاء الملفات والمجلدات، نقلها، تعديلها، حذفها، البحث عنها، أنواع الـ Redirects، وإيه هي File Descriptors.  
كمان هنشوف الـ Shortcuts اللي بتخلي الشغل في الـ Shell أسهل بكتير.

> نصيحة: جرب كل حاجة على VM محلية عندك، وعمل Snapshot قبل ما تبدأ عشان لو حصل حاجة تقدر ترجع.

### أول حاجة: أنا واقف فين دلوقتي؟ (pwd)

```bash
cry0l1t3@htb[~]$ pwd

/home/cry0l1t3
```

الأمر `pwd` (Print Working Directory) بيقولك أنت واقف في أي مجلد حاليًا.

### عرض محتويات المجلد (ls)

أبسط أمر هو `ls`:

```bash
cry0l1t3@htb[~]$ ls

Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
```

#### خيار `-l` (Long Format)

```bash
cry0l1t3@htb[~]$ ls -l

total 32
drwxr-xr-x 2 cry0l1t3 htbacademy 4096 Nov 13 17:37 Desktop
drwxr-xr-x 2 cry0l1t3 htbacademy 4096 Nov 13 17:34 Documents
...
```

**شرح أعمدة `ls -l`:**

| العمود          | معناه |
|----------------|-------|
| `drwxr-xr-x`   | نوع الملف + الصلاحيات |
| `2`            | عدد الـ Hard Links |
| `cry0l1t3`     | صاحب الملف (Owner) |
| `htbacademy`   | المجموعة (Group) |
| `4096`         | الحجم (بالبايت) أو عدد البلوكات للمجلد |
| `Nov 13 17:37` | تاريخ ووقت آخر تعديل |
| `Desktop`      | اسم الملف أو المجلد |

#### عرض الملفات المخفية (`-a`)

الملفات اللي اسمها بيبدأ بنقطة (`.`) بتبقى مخفية. عشان تشوفها استخدم:

```bash
cry0l1t3@htb[~]$ ls -la
```

#### عرض محتويات مجلد بدون ما ندخله

```bash
cry0l1t3@htb[~]$ ls -l /var/
```

### التنقل بين المجلدات (cd)

```bash
cry0l1t3@htb[~]$ cd /dev/shm

cry0l1t3@htb[/dev/shm]$
```

#### الرجوع للمجلد السابق

```bash
cry0l1t3@htb[/dev/shm]$ cd -

cry0l1t3@htb[~]$
```

#### الرجوع للمجلد الأب (Parent Directory)

```bash
cry0l1t3@htb[/dev/shm]$ cd ..

cry0l1t3@htb[/dev]$
```

### Auto-Complete (أقوى حاجة في الـ Shell)

اكتب `cd /dev/s` وبعدين اضغط **Tab** مرتين → هيوريك كل المجلدات اللي بتبدأ بحرف `s`.

```bash
cry0l1t3@htb[~]$ cd /dev/s [TAB ×2]

shm/  snd/
```

لو كتبت `sh` وضغطت Tab، الـ Shell هيكملها لوحده:

```bash
cry0l1t3@htb[~]$ cd /dev/shm
```

### تنظيف الـ Terminal

```bash
cry0l1t3@htb[/dev]$ cd shm && clear
```

أو استخدم الـ Shortcut:

- **Ctrl + L** → تنظيف الشاشة بسرعة

### التنقل في تاريخ الأوامر

- **سهم لفوق ↑** أو **لتحت ↓** → تتصفح الأوامر اللي كتبتها قبل كده
- **Ctrl + R** → بحث في التاريخ (اكتب جزء من الأمر وهيدورلك عليه)

---
## Working with Files and Directories

الفرق الرئيسي بين شغل الملفات في Linux و Windows إن في ويندوز بنستخدم Explorer (الواجهة الرسومية)، أما في Linux فالـ Terminal هو اللي بيخليك تتحكم في الملفات بسرعة وقوة رهيبة.

في الـ Terminal تقدر:
- تعمل ملفات ومجلدات بسرعة
- تنقل وتنسخ وتحذف
- تعدل ملفات بدون ما تفتح محرر
- تستخدم Regular Expressions عشان تعدل كذا ملف في وقت واحد
- توجه الـ Output لملفات (Redirection)

ده بيوفر وقت كتير جدًا، خاصة لما بتشتغل على ملفات كتير في نفس الوقت.

### إنشاء ملفات ومجلدات

#### 1. إنشاء ملف فارغ (`touch`)

```bash
geekmo1@htb[/htb]$ touch <اسم_الملف>
```

**مثال:**

```bash
geekmo1@htb[/htb]$ touch info.txt
```

#### 2. إنشاء مجلد (`mkdir`)

```bash
geekmo1@htb[/htb]$ mkdir <اسم_المجلد>
```

**مثال:**

```bash
geekmo1@htb[/htb]$ mkdir Storage
```

#### إنشاء مجلدات متداخلة بسرعة (`-p`)

لو عايز تعمل مجلدات جوا بعض بدون ما تعملها واحد واحد:

```bash
geekmo1@htb[/htb]$ mkdir -p Storage/local/user/documents
```

عشان تشوف الشكل كله استخدم أمر `tree`:

```bash
geekmo1@htb[/htb]$ tree .

.
├── info.txt
└── Storage
    └── local
        └── user
            └── documents

4 directories, 1 file
```

#### إنشاء ملف داخل مجلد معين

```bash
geekmo1@htb[/htb]$ touch ./Storage/local/user/userinfo.txt
```

### نقل وإعادة تسمية (mv)

الأمر `mv` بيستخدم للنقل **و** إعادة التسمية في نفس الوقت.

**الصيغة:**

```bash
mv <الملف_القديم> <الملف_الجديد_أو_المكان>
```

**مثال - إعادة تسمية:**

```bash
geekmo1@htb[/htb]$ mv info.txt information.txt
```

**مثال - نقل ملفات:**

أولاً نعمل ملف جديد:

```bash
geekmo1@htb[/htb]$ touch readme.txt
```

وبعدين ننقل الملفين:

```bash
geekmo1@htb[/htb]$ mv information.txt readme.txt Storage/
```

### نسخ الملفات (cp)

```bash
geekmo1@htb[/htb]$ cp Storage/readme.txt Storage/local/
```

دلوقتي نشوف الشكل النهائي:

```bash
geekmo1@htb[/htb]$ tree .

.
└── Storage
    ├── information.txt
    ├── local
    │   ├── readme.txt
    │   └── user
    │       ├── documents
    │       └── userinfo.txt
    └── readme.txt

4 directories, 4 files
```

### ملاحظات مهمة

- تقدر تستخدم **Redirection** (`>` و `>>`) عشان توجه النتيجة لملف.
- في أقسام جاية هنتعلم محررات النصوص زي `nano` و `vim`.
- الأمر `cp` و `mv` و `rm` من أقوى الأوامر في إدارة الملفات.

### تمرين اختياري

جرب دلوقتي تحذف الملفات والمجلدات اللي عملتها باستخدام الأدوات اللي اتعلمناها.  
لو مش عارف الأمر بتاع الحذف، ابحث على جوجل، ده جزء طبيعي من التعلم ومش غش أبدًا.  
البحث هيساعدك تشوف طرق مختلفة وتفهم أكتر.

---

## Editing

بعد ما اتعلمنا إزاي نعمل ملفات ومجلدات، خلينا نتعلم دلوقتي إزاي نعدل في الملفات.

في Linux فيه طرق كتير لتعديل الملفات، أشهر محررات النصوص هما **Vi / Vim** و **Nano**.  
هنبدأ بالـ **Nano** عشان أسهل وأبسط، خاصة لو أنت لسة جديد.

### Nano Editor

عشان تفتح ملف جديد أو تعدل ملف موجود بـ Nano:

```bash
geekmo1@htb[/htb]$ nano notes.txt
```

هيفتحلك الـ Nano Editor زي كده:

```bash
  GNU nano 2.9.3                                    notes.txt                                              

Here we can type everything we want and make our notes.


^G Get Help    ^O Write Out   ^W Where Is    ^K Cut Text    ^J Justify     ^C Cur Pos     M-U Undo
^X Exit        ^R Read File   ^\ Replace     ^U Uncut Text  ^T To Spell    ^_ Go To Line  M-E Redo
```

#### أهم اختصارات Nano (مهم تحفظها)

- `Ctrl + O` → حفظ الملف (Write Out)
- `Ctrl + X` → خروج من Nano
- `Ctrl + W` → بحث عن كلمة (Where Is)
- `Ctrl + K` → قص (Cut)
- `Ctrl + U` → لصق (Uncut)
- `Ctrl + C` → يوريك مكان المؤشر الحالي

**مثال على البحث:**
اضغط `Ctrl + W` واكتب كلمة تبحث عنها، وبعدين اضغط Enter.  
عشان تروح للكلمة اللي بعدها اضغط `Ctrl + W` تاني و Enter.

**حفظ وخروج:**
- `Ctrl + O` → حفظ → اضغط Enter
- `Ctrl + X` → خروج

### عرض محتوى الملف بعد الحفظ (cat)

```bash
geekmo1@htb[/htb]$ cat notes.txt

Here we can type everything we want and make our notes.
```

### ملف مهم جدًا في الأمن السيبراني: /etc/passwd

الملف ده بيحتوي على معلومات كل المستخدمين في النظام زي:
- اسم المستخدم
- User ID (UID)
- Group ID (GID)
- Home Directory

> زمان كان بيحتوي على كلمات السر (Hash)، دلوقتي كلمات السر مخزنة في ملف `/etc/shadow` اللي صلاحياته أقوى بكتير.

لو صلاحيات `/etc/passwd` أو أي ملف حساس مش مضبوطة كويس، ده ممكن يفتح باب كبير لـ **Privilege Escalation**.

### VIM Editor

**Vim** محرر قوي جدًا ومشهور في عالم Linux، وهو تطوير للـ Vi القديم.

```bash
geekmo1@htb[/htb]$ vim
```

Vim مختلف عن Nano لأنه **Modal Editor**، يعني فيه أكتر من وضع (Mode):

| الوضع (Mode)     | الوصف |
|------------------|------|
| **Normal**       | الوضع الافتراضي - كل ضغطة بتتعامل كأمر |
| **Insert**       | وضع الكتابة (بتكتب نص عادي) |
| **Visual**       | وضع تحديد جزء من النص |
| **Command**      | وضع كتابة أوامر (بتبدأ بـ `:`) |
| **Replace**      | استبدال النص القديم بالجديد |
| **Ex**           | وضع تنفيذ أوامر متعددة |

#### أهم أمر في Vim

للخروج من Vim:
- اضغط `:` ثم اكتب `q` واضغط Enter → `:q`

### تعلم Vim بسرعة (Vim Tutor)

أفضل طريقة تتعلم Vim هي عن طريق الـ Tutor:

```bash
geekmo1@htb[/htb]$ vimtutor
```

أو داخل Vim اكتب:

```bash
:Tutor
```

الـ Tutor بياخد حوالي 25-30 دقيقة وهيساعدك تتعود على Vim بطريقة عملية.

> Vim صعب في الأول، بس لما تتعود عليه هيبقى أقوى أداة عندك في الـ Terminal.

---
## Find Files and Directories

لما تدخل على نظام Linux، هتحتاج دايمًا تعرف تلاقي الملفات والمجلدات بسرعة.  
مش هتقدر تمشي يدوي في كل مجلد وتشوف آخر تعديل إيه. فيه أدوات قوية بتساعدك في ده.

### 1. which

الأمر `which` بيطلعلك المسار بتاع البرنامج اللي هيتنفذ لو كتبت اسمه.

**مثال:**

```bash
geekmo1@htb[/htb]$ which python

/usr/bin/python
```

لو البرنامج مش موجود، مش هيطلع أي حاجة.

> مفيد جدًا عشان تعرف البرامج زي `curl`، `netcat`، `wget`، `python`، `gcc` موجودة ولا لأ.

### 2. find (أقوى أداة بحث)

الأمر `find` مش بس بيلاقي ملفات، ده كمان بيقدر يفلتر النتايج حسب:
- النوع (ملف ولا مجلد)
- الاسم
- صاحب الملف
- الحجم
- التاريخ
- وأكتر من كده

**الصيغة الأساسية:**

```bash
find <المكان> <الخيارات>
```

**مثال قوي:**

```bash
geekmo1@htb[/htb]$ find / -type f -name "*.conf" -user root -size +20k -newermt 2020-03-03 -exec ls -al {} \; 2>/dev/null
```

#### شرح الخيارات اللي استخدمناها:

| الخيار                    | معناه بالعامية |
|--------------------------|----------------|
| `-type f`                | ابحث عن **ملفات** فقط (f = file) |
| `-name "*.conf"`         | اسم الملف ينتهي بـ `.conf` |
| `-user root`             | صاحب الملف لازم يكون root |
| `-size +20k`             | الحجم أكبر من 20 كيلو بايت |
| `-newermt 2020-03-03`    | الملفات اللي اتعدلت بعد التاريخ ده |
| `-exec ls -al {} \;`     | نفذ أمر `ls -al` على كل نتيجة |
| `2>/dev/null`            | أخفي كل الأخطاء (مهم جدًا عشان النتيجة تكون نظيفة) |

### 3. locate (أسرع طريقة)

`locate` أسرع بكتير من `find` لأنه بيشتغل على قاعدة بيانات محلية.

**أول حاجة لازم تعملها (تحديث القاعدة):**

```bash
geekmo1@htb[/htb]$ sudo updatedb
```

**بعد كده ابحث:**

```bash
geekmo1@htb[/htb]$ locate "*.conf"
```

هيطلع كل الملفات اللي اسمها بتنتهي بـ `.conf` في ثواني.

**ملاحظة:**
- `locate` أسرع، لكن خيارات الفلترة فيه أقل من `find`.
- استخدم `find` لما تحتاج فلترة دقيقة، و`locate` لما عايز نتيجة سريعة.

### تمرين اختياري

جرب الأدوات اللي اتعلمناها دلوقتي وابحث عن كل حاجة متعلقة بـ **netcat** أو **nc**.

 ---
## File Descriptors and Redirections

**File Descriptor (FD)** هو رقم بيستخدمه الـ Kernel في Linux عشان يتابع عمليات الـ Input والـ Output (I/O).  
كل ملف مفتوح أو socket أو أي حاجة بتتعامل مع الإدخال والإخراج ليها رقم (File Descriptor).

فكر فيه زي **التذكرة** اللي بتاخدها لما تسلم الجاكيت بتاعك في الـ Coatroom.  
التذكرة (الـ FD) هي اللي بتربطك بالجاكيت (الملف). بدونها النظام مش هيعرف يوصل للملف الصح.

### الـ File Descriptors الثلاثة الافتراضية في Linux

| الرقم | الاسم       | الوصف |
|------|------------|------|
| **0** | **STDIN**  | الإدخال القياسي (من الكيبورد عادة) |
| **1** | **STDOUT** | الإخراج القياسي (اللي بيظهر في الـ Terminal) |
| **2** | **STDERR** | إخراج الأخطاء (الرسائل الحمراء "Permission denied" إلخ) |

### أمثلة عملية

#### 1. STDIN و STDOUT مع `cat`

```bash
cat
SOME INPUT   ← (ده STDIN - FD 0)
SOME INPUT   ← (ده STDOUT - FD 1)
```

#### 2. STDOUT و STDERR مع `find`

```bash
geekmo1@htb[/htb]$ find /etc/ -name shadow
```

هتلاقي كتير رسائل **"Permission denied"** (دي STDERR - FD 2).

#### إخفاء الأخطاء (Redirect STDERR)

```bash
geekmo1@htb[/htb]$ find /etc/ -name shadow 2>/dev/null
```

الـ `2>/dev/null` بيرمي كل الأخطاء في الـ "سلة المهملات" عشان الـ Terminal يبقى نظيف.

#### توجيه الإخراج لملف (Redirect STDOUT)

```bash
geekmo1@htb[/htb]$ find /etc/ -name shadow 2>/dev/null > results.txt
```

دلوقتي كل النتايج السليمة (STDOUT) راحت في الملف `results.txt`.

#### توجيه STDOUT و STDERR لملفات منفصلة

```bash
geekmo1@htb[/htb]$ find /etc/ -name shadow 2> stderr.txt 1> stdout.txt
```

- `1>` → STDOUT
- `2>` → STDERR

#### إضافة محتوى لملف موجود (Append)

```bash
geekmo1@htb[/htb]$ find /etc/ -name passwd >> stdout.txt 2>/dev/null
```

`>>` بيضيف في نهاية الملف بدون ما يمسح اللي قبله (مش زي `>` اللي بيحذف ويكتب من أول وجديد).

#### استخدام STDIN من ملف

```bash
geekmo1@htb[/htb]$ cat < stdout.txt
```

### Here Document (<< EOF)

طريقة حلوة تكتب نص كبير وتوجهه لملف:

```bash
geekmo1@htb[/htb]$ cat << EOF > stream.txt
هنا بتكتب أي نص تحبه
وكل سطر جديد
وبعدين تكتب EOF عشان يقفل
EOF
```

### Pipes (`|`)

الـ Pipe بياخد الـ STDOUT من أمر ويحطه كـ STDIN في الأمر اللي بعده.

**مثال:**

```bash
geekmo1@htb[/htb]$ find /etc/ -name "*.conf" 2>/dev/null | grep systemd
```

**مثال أقوى (عدد النتايج):**

```bash
geekmo1@htb[/htb]$ find /etc/ -name "*.conf" 2>/dev/null | grep systemd | wc -l
```

---

**خلاصة سريعة:**

- `>`   → توجيه STDOUT (وبيحذف الملف لو موجود)
- `>>`  → توجيه STDOUT وإضافة في الآخر
- `2>`  → توجيه STDERR
- `2>/dev/null` → إخفاء كل الأخطاء
- `|`   → Pipe (يربط بين أوامر)

دلوقتي تقدر تبني أوامر معقدة ونظيفة جدًا!

---
تمام يا محمد!  

هنا **Filter Contents** منسق بالعامية المصرية السيكا زي ما بتحب:

---

## Filter Contents

في القسم السابق اتعلمنا إزاي نوجه الـ Output من أمر لأمر تاني.  
دلوقتي هنتعلم إزاي نقرأ الملفات مباشرة من الـ Terminal بدون ما نفتح محرر نصوص.

فيه أدوات قوية جدًا اسمها **Pagers** زي `more` و `less` بتساعدك تشوف محتوى الملفات الكبيرة صفحة صفحة.

### more

```bash
geekmo1@htb[/htb]$ cat /etc/passwd | more
```

الملف `/etc/passwd` زي دليل تليفونات لكل المستخدمين في النظام.  
بيحتوي على: اسم المستخدم، UID، GID، Home Directory، والـ Shell الافتراضي.

لما تستخدم `more` هيفتحلك الصفحة الأولى، وتقدر تتحرك بالـ Space أو Enter.  
عشان تخرج اضغط `q`.

### less (أفضل وأقوى من more)

```bash
geekmo1@htb[/htb]$ less /etc/passwd
```

`less` أقوى بكتير من `more`، وفيه مميزات زيادة (تقدر تبحث، ترجع لورا، إلخ).  
لما تخلّص اضغط `q`، والـ Output مش هيفضل ظاهر في الـ Terminal (عكس `more`).

### head و tail

- `head` → يظهر أول سطور الملف (افتراضيًا 10 سطور)
- `tail` → يظهر آخر سطور الملف

```bash
geekmo1@htb[/htb]$ head /etc/passwd
geekmo1@htb[/htb]$ tail /etc/passwd
```

### sort

لو النتايج مش مرتبة، استخدم `sort` عشان ترتبها أبجديًا أو رقميًا:

```bash
geekmo1@htb[/htb]$ cat /etc/passwd | sort
```

### grep (أهم أداة فلترة)

`grep` بيبحث عن كلمة أو نمط معين.

**مثال: البحث عن يوزرات بيستخدموا bash**

```bash
geekmo1@htb[/htb]$ cat /etc/passwd | grep "/bin/bash"
```

**استبعاد نتايج (خيار -v)**

```bash
geekmo1@htb[/htb]$ cat /etc/passwd | grep -v "false\|nologin"
```

### cut

لو عايز تقطع جزء معين من السطر حسب فاصل (Delimiter):

```bash
geekmo1@htb[/htb]$ cat /etc/passwd | grep -v "false\|nologin" | cut -d":" -f1
```

`-d":"` → الفاصل هو `:`
`-f1`   → خد العمود الأول فقط (اسم اليوزر)

### tr (استبدال حروف)

```bash
geekmo1@htb[/htb]$ cat /etc/passwd | grep -v "false\|nologin" | tr ":" " "
```

بيحول كل `:` إلى مسافة.

### column (عرض بشكل جدولي جميل)

```bash
geekmo1@htb[/htb]$ cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | column -t
```

### awk (قوي جدًا)

```bash
geekmo1@htb[/htb]$ cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | awk '{print $1, $NF}'
```

`$1` → أول عمود  
`$NF` → آخر عمود

### sed (استبدال نصوص بـ Regular Expressions)

```bash
geekmo1@htb[/htb]$ ... | sed 's/bin/HTB/g'
```

`s` → substitute  
`g` → global (استبدل الكل)

### wc (عدد السطور أو الكلمات)

```bash
geekmo1@htb[/htb]$ ... | wc -l
```

---

### تمارين عملية (Optional Exercises)

استخدم ملف `/etc/passwd` وحاول تعمل الآتي:

1. اعرض السطر الخاص باليوزر `cry0l1t3` فقط.
2. اعرض أسماء كل اليوزرات فقط.
3. اعرض اسم اليوزر `cry0l1t3` مع UID بتاعه.
4. اعرض اسم `cry0l1t3` و UID مفصولين بفاصلة `,`.
5. اعرض اسم `cry0l1t3` و UID و الـ Shell مفصولين بفاصلة `,`.
6. اعرض كل اليوزرات مع UID و Shell مفصولين بفاصلة `,`.
7. نفس اللي فوق بس استبعد اللي فيهم `nologin` أو `false`.
8. نفس اللي فوق + عد عدد السطور في النتيجة النهائية.

دي كمان [Linux Modules Room THM (Try Hack Me)
](https://tryhackme.com/room/linuxmodules)

---

 