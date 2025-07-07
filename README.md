 
### 🚀 **Git & GitHub Tam Kılavuzu: Temelden İleri Seviyeye**  
*(Kurulum → Klonlama → Değişiklik → Push → Ekip Yönetimi)*

---

### 1. **Git Kurulumu**  
- **Windows/macOS/Linux** için [Git resmi sitesi](https://git-scm.com/downloads)'nden indirin.  
- Kurulumu doğrulayın:  
  ```bash
  git --version
  ```

---

### 2. **Repo Klonlama (Public/Private)**  
#### 🔓 **Public Repo** (Herkese Açık):  
```bash
git clone https://github.com/kullanici_adi/repo_adi.git
```

#### 🔒 **Private Repo** (Özel):  
**A. Token ile Kimlik Doğrulama:**  
1. GitHub'da **Settings > Developer Settings > Personal Access Tokens > Generate new token**  
2. `repo` iznini seçip token oluşturun.  
3. Klonlama:  
   ```bash
   git clone https://TOKEN@github.com/kullanici_adi/repo_adi.git
   ```  
   *Örnek: `git clone https://ghp_AbCd123@github.com/ahmet/özel-repo.git`*

**B. SSH ile (Tavsiye Edilen):**  
1. SSH anahtarı oluştur:  
   ```bash
   ssh-keygen -t ed25519 -C "email@adresiniz.com"
   ```
2. Public key'i GitHub'a ekle:  
   **Settings > SSH and GPG Keys > New SSH Key**  
3. Klonlama:  
   ```bash
   git clone git@github.com:kullanici_adi/repo_adi.git
   ```

---

### 3. **Branch Yönetimi**  
```bash
cd repo_adi  # Repo klasörüne gir

# Mevcut branch'leri listele
git branch -a

# ekip2 branch'ine geç (varsa)
git checkout ekip2

# YOKSA yeni branch oluştur ve geç:
git checkout -b ekip2
```

---

### 4. **Değişiklik Yapma & Commit**  
1. Dosyaları düzenleyin (VS Code, Notepad vb.).  
2. Değişiklikleri staged alanına ekle:  
   ```bash
   git add .           # Tüm değişiklikler
   # VEYA
   git add dosya.txt   # Tek dosya
   ```
3. Commit oluştur:  
   ```bash
   git commit -m "ekip2 için güncellemeler"
   ```

---

### 5. **Değişiklikleri GitHub'a Gönderme (Push)**  
```bash
# İlk kez push ediyorsanız:
git push --set-upstream origin ekip2

# Sonraki push'lar için:
git push origin ekip2
```

---

### 6. **Özel Repo'ya Ekip Üyesi Ekleme**  
1. Repo > **Settings > Collaborators > Add people**  
   <img src="https://i.imgur.com/3tZ8h7T.png" width="400" alt="Collaborator Ekleme">  
2. GitHub kullanıcı adını girip yetki seviyesi belirleyin:  
   - **Read**: Sadece görüntüleme  
   - **Write**: Değişiklik gönderebilir (tavsiye edilen)  
   - **Admin**: Tam yetki  
3. Kişi e-posta davetini kabul etmeli.

---

### 7. **Takım Çalışması İpuçları**  
- **Değişiklikleri Çekme:**  
  ```bash
  git pull origin ekip2   # Uzaktaki değişiklikleri al
  ```
- **Çakışma (Conflict) Çözümü:**  
  1. Çakışan dosyaları düzenle (`<<<<<<< HEAD` işaretlerini kaldır).  
  2. Değişiklikleri tekrar commit et:  
     ```bash
     git add .
     git commit -m "Çakışma çözüldü"
     git push origin ekip2
     ```

---

### 🚨 **Sık Karşılaşılan Sorunlar & Çözümler**  

| **Hata**                                      | **Çözüm**                                                                 |
|-----------------------------------------------|---------------------------------------------------------------------------|
| `Repository not found`                        | - Token/SSH izinlerini kontrol edin<br>- Repo adını doğrulayın            |
| `Permission denied (publickey)`               | [SSH key'ini GitHub'a ekleyin](https://docs.github.com/tr/authentication) |
| `Updates were rejected`                       | Önce uzaktaki değişiklikleri çekin: `git pull origin ekip2`              |
| `Branch 'ekip2' does not exist`               | Önce branch oluşturun: `git checkout -b ekip2`                           |
| İki faktörlü doğrulama (2FA) hatası           | Token kullanın (şifre yerine)                                            |

---

### 🔧 **Özet Komut Tablosu**  
| Aşama                     | Komut                                       |
|---------------------------|---------------------------------------------|
| **Klonlama (SSH)**        | `git clone git@github.com:kullanici/repo.git` |
| **Yeni Branch**           | `git checkout -b ekip2`                     |
| **Değişiklik Kaydetme**   | `git add . && git commit -m "Mesaj"`        |
| **Push**                  | `git push origin ekip2`                     |
| **Ekip Değişikliği Çekme**| `git pull origin ekip2`                     |

---

### 📌 **Proje Yönetimi İpuçları**  
1. **.gitignore** kullanın (şifreler, IDE dosyaları vs. repo'ya eklenmesin).  
2. Commit mesajlarını açıklayıcı yazın ("düzeltme" yerine "kullanıcı girişi hata düzeltmesi").  
3. `ekip2` branch'ine push yaptıktan sonra **Pull Request (PR)** açarak ana branch'e birleştirin.  

---

### 🌟 **Ek Kaynaklar**  
- [Git Resmi Dokümanı](https://git-scm.com/doc)  
- [GitHub SSH Key Rehberi](https://docs.github.com/tr/authentication/connecting-to-github-with-ssh)  
- [Branch Stratejileri](https://nvie.com/posts/a-successful-git-branching-model/)

---

Bu belgeyi PDF olarak kaydetmek için:  
1. Tüm içeriği kopyalayın  
2. [Markdown to PDF](https://markdowntopdf.com/) sitesine yapıştırıp dönüştürün.  

Herhangi bir adımda takılırsanız **hatayı veya ekran görüntüsünü paylaşın**, anında çözüm sunayım! 💻🔧
