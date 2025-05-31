# Web Automation Testing dengan Cucumber dan Selenium

## Team Members
**Kelompok A11**
- Muhamad Fahrizal Al-Zaelani
- Muhammad Fikri Nur Sya'Bani
- Saabiq M A

## Requirement
- Java Development Kit (JDK) 17 ++
- Maven (opsional, karena sudah disediakan Maven Wrapper)
- Internet untuk mengunduh dependensi Maven dan WebDriver

## Cara Menjalankan Pengujian

1. **Clone repo** (jika menggunakan Git):
   ```powershell
   git clone [URL_REPOSITORY]
   cd WebAutomation
   ```

2. **Jalankan testing** menggunakan Maven Wrapper:
   ```powershell
   ./mvnw clean test
   ```
   Atau jika menggunakan Maven yang sudah terinstal:
   ```powershell
   mvn clean test
   ```

3. **Create laporan Allure**:
   ```powershell
   ./mvnw allure:report
   ```
   Atau:
   ```powershell
   mvn allure:report
   ```

4. **Melihat laporan Allure**:
   ```powershell
   ./mvnw allure:serve
   ```
   Atau:
   ```powershell
   mvn allure:serve
   ```
   Perintah ini akan membuka browser secara otomatis dengan laporan Allure.

## Men-Deploy Laporan Allure ke GitHub Pages

### 1. Persiapan Laporan untuk GitHub Pages
1. Jalankan test dan hasilkan laporan Allure:
   ```powershell
   mvn clean test allure:report
   ```

2. Gunakan script yang disediakan untuk menyiapkan laporan untuk GitHub Pages:
   ```powershell
   .\prepare-allure-for-github-pages.ps1
   ```
   Script ini akan menyalin laporan ke dalam direktori `docs/` dan membuat file `.nojekyll`.

### 2. Men-Deploy ke GitHub
1. Commit dan push perubahan ke repositori GitHub Anda:
   ```powershell
   git add docs/ .nojekyll
   git commit -m "Add Allure report for GitHub Pages"
   git push origin main
   ```

2. Buka repositori GitHub Anda di browser.
3. Pergi ke **Settings** > **Pages**.
4. Di bagian **Source**, pilih **Deploy from a branch**.
5. Pilih branch **main** dan direktori **/docs** kemudian klik **Save**.
6. Tunggu beberapa menit hingga GitHub Pages di-deploy.

### 3. Akses Laporan Online
Setelah deployment selesai, laporan Allure akan tersedia di URL:
```
https://[username].github.io/[repository-name]/
```
