#Market

Proje, **ASP.NET MVC Core** kullanılarak geliştirilmiş olup, katmanlı mimari yapısı uygulanmıştır. Proje, aşağıdaki katmanlardan oluşmaktadır:

- **Business Katmanı**: İş kurallarını içerir.
- **DataAccess Katmanı**: Veri tabanı işlemleri bu katmanda gerçekleştirilir.
- **Entities Katmanı**: Veri modellerini içerir.
- **Web Katmanı**: Kullanıcı arayüzü bu katmanda yer alır.

Proje, **Entity Framework Code First** yaklaşımıyla geliştirilmiştir. Kullanıcı kimlik doğrulaması ve yönetimi için **Identity Core** kullanılmıştır. Kullanıcı kayıt sürecinde mail doğrulaması yer almaktadır. Ayrıca, hatasız çalışan bir rol sistemi mevcuttur. Ödeme işlemleri için **Iyzico** entegrasyonu yapılmıştır. Bu proje, Kodluyoruz Backend kursu bitirme projesi olarak geliştirilmiştir.

---

## Projenin Bölümleri

Proje, aşağıdaki ana bölümlerden oluşmaktadır:

1. **Front End**
2. **User Area**
3. **Admin Area**

---

### Kullanılan Eklentiler
Projede aşağıdaki eklentiler kullanılmıştır:

- **Datatables**
- **SweetAlert**
- **CKEditor**
- **Google Chart**

---

## Front End

Front End kısmında aşağıdaki sayfalar bulunmaktadır:

### Home
Ana sayfada bir arama butonu ile ürün arama yapılabilir. Sayfada sırasıyla şu bölümler bulunmaktadır:
- **Slider**: Görsel bir kaydırıcı.
- **Products of the Month** ve **Today Offers**: Admin paneli üzerinden değiştirilebilir.
- **Popular Products**: Admin panelinden yönetilebilir.
- **Kategoriler** ve **New Offers**: Admin panelinden ayarlanabilir.

### Products
Ürünler sayfasında şu özellikler bulunmaktadır:
- Ürünler ve kategoriler listelenir (kategoriler admin panelinden yönetilir).
- Ürün detaylarına gidilebilir.
- Ürün istek listesine eklenebilir ya da karta eklenebilir.
- Sayfa üzerinde **sayfalama (paging)** desteği vardır.
- İndirimli ürünler, fiyat ve görsellerle birlikte belirtilir.

### About Us
Bu bölümde kısa bir "Hakkımızda" yazısı ve iletişim bilgileri bulunmaktadır.

### Contact
İletişim sayfasında şu özellikler yer alır:
- İletişim bilgileri.
- Harita entegrasyonu.
- Kullanıcıların mesaj bırakabileceği bir "Leave a Message" bölümü. Bu mesajlar admin panelinde görüntülenebilir ve yanıtlanabilir.

### Login ve Register
- **Login**: Mail doğrulamasını tamamlamış kullanıcılar giriş yapabilir.
- **Register**: Kullanıcı kayıt işlemi sonrası doğrulama maili gönderilir ve doğrulama tamamlandığında giriş yapılabilir.

---

## User Area
Kullanıcılar bu bölümde aşağıdaki işlemleri yapabilir:

- **Sepet İşlemleri**: Karta eklenen ürünlerin ödemesi yapılabilir (Iyzico ile).
- **Sipariş Takibi**: Ödenen ürünler görüntülenebilir ve kargo takibi yapılabilir.
- **İstek Listesi**: İstek listesi yönetilebilir (ekleme/çıkarma).
- **Adres Yönetimi**: Adresler eklenebilir, güncellenebilir ya da silinebilir.
- **Kart Bilgileri Yönetimi**: Kart bilgileri eklenebilir, güncellenebilir ya da silinebilir.
- **Profil Yönetimi**: Kullanıcı bilgileri güncellenebilir.

---

## Admin Area
Admin paneline `/Admin` adresinden giriş yapılabilir. Admin panelinde şu bölümler yer alır:

### Dashboard
Bu bölümde:
- Önemli istatistikler.
- Ana sayfadaki düzenlenebilir bölümleri değiştirme seçenekleri.

### Categories
- Kategorilerin listelenmesi, güncellenmesi, eklenmesi ve **soft delete** işlemleri.
- Bir kategoriyi güncellerken, o kategoriye ait ürünler listelenmektedir.

### Products
- Ürünlerin listelenmesi, eklenmesi, güncellenmesi ve **soft delete** işlemleri.
- Ürün ekleme/güncelleme sırasında açıklama için **CKEditor** kullanılmaktadır.
- Resim ekleme özelliği vardır.
- İndirimli ürünler admin panelinde belirtilebilir, böylece Front End'de kullanıcıya gösterilir.
- **SweetAlert** eklentisi, kullanıcı bilgilendirmeleri için kullanılmıştır.

### Roles
- Yeni roller oluşturulabilir.
- Kullanıcılar rollere eklenebilir/çıkarılabilir.
- Sadece **Admin** rolüne sahip kullanıcılar admin paneline erişebilir.

### Users
- Kullanıcıların listelenmesi.

### Orders
- Siparişlerin görüntülenmesi ve **soft delete** işlemiyle pasif hale getirilmesi.
- Kargo işlemlerinin yönetimi.

### Announcements
- Kullanıcılara yönelik duyurular eklenebilir, güncellenebilir.

### Help Messages
- Kullanıcılardan gelen yardım mesajları görüntülenebilir ve cevaplanabilir.

### Statistic
- Toplam 16 istatistik bulunmaktadır (örneğin, toplam kullanıcı sayısı, en çok harcama yapan kullanıcı vb.).

### Graphics
- 3 farklı grafik türü:
  - **Pie Chart**
  - **Line Chart**
  - **Column Chart**
- Grafikler, **Google Chart** kullanılarak oluşturulmuştur.

---

## Kurulum

Proje kurulumu oldukça basittir:

1. **Proje Clone Alma**:
   ```bash
   git clone https://github.com/username/Market.git
   ```

2. **Veritabanı Kurulumu**:
   - Proje dosyalarının içinde bulunan **script dosyasını** çalıştırarak ya da yedek dosyasını (backup) yükleyerek veritabanını kurabilirsiniz.

3. **Gerekli Bağımlılıkları Yükleyin**:
   - Bağımlılıkları yüklemek için şu komutları çalıştırın:
     ```bash
     dotnet restore
     dotnet build
     ```

4. **Projeyi Çalıştırın**:
   - Projeyi aşağıdaki komutla başlatabilirsiniz:
     ```bash
     dotnet run
     ```

---

## Kullanılan Template

- **HomePage Template**: [w3layouts](https://w3layouts.com)
- **Admin Panel Template**: [AdminLTE](https://adminlte.io)

---


