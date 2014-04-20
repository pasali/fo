#   Git Iş Akışı

.fx: first

pasali `<mhmtbsl@bil.omu.edu.tr>`

http://mhmtbsl.net/

Şubat 2014

---

##   Git Kullanımı Ve Olası Sorunlar

-   Diğer geliştricilerinin değişikliklerinin üzerine yazmak(git push --force)

        git config --system receive.denyNonFastForwards true

-   Yerel deponuzda commitlenmemiş değişikliklerinizin üzerine yazmak

-   Conflicts(çakışmalar)

---

##   Çakışmalar(conflict) Nasıl  Çözülür?

-   meld, vimdiff, diffmerge, git-mergetool...
-   Basit bir text editorde iş görür
-   Conflict örneği;

        <<<<<<< HEAD
        Hello, master change.
        =======
        Hello, branch b1 change.
        >>>>>>> b1
---
##   Değişiklik(Commit) Mesajları Nasıl Yazılır?

-   En fazla 50 karakterlik bir başlık(işi özetleyen)
-   Başlık büyük harfle başlayacak(sonda nokta yok)
-   En fazla 72 karakterlik bir açıklama (gerekirse)
-   Başlık ve açıklama boş satır ile ayrılacak
-   "düzeltme", "ekleme" yerine "düzeltildi", "eklendi"

---

##   Örnek Değişiklik (Commit) Mesajı


        bin: Kopyala yapıştır hatası düzeltildi

        Kopyala yapıştırla gelen "estetik tırnaklar"dan dolayı bu ayar
        etkin olduğunda veritabanı bağlantıları kopuyordu. Sadece bu
        iğrenç hata nedenle yarım saat harcadım. İbret alınsın!
---

##   Değişiklik (Commit) Mesajını Düzeltme

-   Son değişiklik(Commit) mesajını düzeltme

        git commit --amend -m "Yeni mesaj buraya"

-   Text Editor ile düzeltmek için

        git commit --amend

-   Herhangi bir commit'i düzeltmek için

        git log --oneline # commit idsini öğrenmek için
        git rebase -i {id}^
        # Açılan pencerede "pick" değişip "reword" yapıp kaydedince
        # düzeltme penceresi açılır

---

##   Git - rebase

-   `git merge` gibi dalları birleştirir
-   Commit geçmişinin doğrusal olmasını sağlar
-   Commit geçmişini bozar
-   Ortak çalışalan depolarda kullanılmamalıdır.

---

##  Merge vs. Rebase

   ![RebaseVsMerge](media/rebasevsmerge.png)

---
##   Projeye Yeni Özellik Ekleme

-    
-    
-    

---

##   Hata düzeltme

-

---

##   Kişisel kopya

-

---

##   squash merge

-   git merge --squash bugfix
-   git commit -m 'fix bug'

---

##   git work flow

-   `master` dalındaki her şey dağıtıma hazır olmalı
-   yeni bir özellik üzerinde `master` dalına bir dal ekleyerek çalış
-   değişiklikleri yeni dal adıyla sunucuya gönder
-   yardım almak ve ya `merge` işlemi için `pull request` gönder
-   biri `review` yaptıktan sonra isteği onaylarsa `merge` yap
-   artık `master` dalına gönderebilirsin

---
