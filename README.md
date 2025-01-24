#Market_Tr

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



# Market_En

The project was developed using **ASP.NET MVC Core** with a layered architecture. The project consists of the following layers:

- **Business Layer**: Contains business logic.
- **DataAccess Layer**: Handles database operations.
- **Entities Layer**: Contains data models.
- **Web Layer**: Includes the user interface.

The project was built with **Entity Framework Code First** approach. **Identity Core** was used for user authentication and management. Email verification is required during user registration. A fully functional role-based system is implemented. **Iyzico** is integrated as the payment system. This project was created as a graduation project for the Kodluyoruz Backend course.

---

## Project Sections

The project is divided into the following main sections:

1. **Front End**
2. **User Area**
3. **Admin Area**

---

### Plugins Used
The project uses the following plugins:

- **Datatables**
- **SweetAlert**
- **CKEditor**
- **Google Chart**

---

## Front End

The Front End section includes the following pages:

### Home
The homepage features a search button for finding products. The page includes:
- **Slider**: A visual carousel.
- **Products of the Month** and **Today Offers**: These can be managed from the Admin panel.
- **Popular Products**: Configurable via the Admin panel.
- **Categories** and **New Offers**: Can be adjusted through the Admin panel.

### Products
The products page includes:
- A list of products and categories (categories are managed in the Admin panel).
- Access to product details.
- Adding products to the wishlist or cart.
- **Paging** support for product listings.
- Discounted products are displayed with updated prices and visuals.

### About Us
This page contains a short "About Us" text and contact information.

### Contact
The contact page features:
- Contact details.
- Map integration.
- A "Leave a Message" section where users can send messages. These messages can be viewed and replied to from the Admin panel.

### Login and Register
- **Login**: Verified users can log in.
- **Register**: Users can sign up with their details. After registration, a verification email is sent, and users can log in after completing the verification.

---

## User Area
Users can perform the following actions:

- **Cart Management**: Make payments for items in the cart (via Iyzico).
- **Order Tracking**: View purchased items and track shipping.
- **Wishlist Management**: View and remove items from the wishlist.
- **Address Management**: Add, update, or delete addresses.
- **Card Management**: Add, update, or delete card information.
- **Profile Management**: Update user information.

---

## Admin Area
The Admin panel can be accessed by navigating to `/Admin`. The Admin panel includes the following sections:

### Dashboard
This section displays:
- Key statistics.
- Options to modify dynamic sections of the homepage.

### Categories
- List, update, add, and **soft delete** categories.
- When updating a category, all products in that category are listed.

### Products
- List, add, update, and **soft delete** products.
- **CKEditor** is used for product descriptions during addition and updates.
- File upload support for product images.
- Discounted products can be specified in the Admin panel and displayed to users on the Front End.
- **SweetAlert** is used for user notifications.

### Roles
- Create new roles.
- Add or remove users from roles.
- Only users with the **Admin** role can access the Admin panel.

### Users
- Displays a list of users.

### Orders
- View orders and mark them as inactive with **soft delete**.
- Manage shipping operations.

### Announcements
- Add or update announcements visible to users.

### Help Messages
- View and respond to messages sent from the help panel on the Front End.

### Statistic
- Includes 16 statistics (e.g., total number of users, top-spending user).

### Graphics
- Features 3 types of charts:
  - **Pie Chart**
  - **Line Chart**
  - **Column Chart**
- Charts are implemented using **Google Chart**.

---

## Installation

Setting up the project is straightforward:

1. **Clone the Project**:
   ```bash
   git clone https://github.com/username/Market.git
   ```

2. **Database Setup**:
   - Use the provided **script file** in the project directory or restore from the backup file to set up the database.

3. **Install Dependencies**:
   - Run the following commands to install dependencies:
     ```bash
     dotnet restore
     dotnet build
     ```

4. **Run the Project**:
   - Start the project with the following command:
     ```bash
     dotnet run
     ```

---

## Templates Used

- **HomePage Template**: [w3layouts](https://w3layouts.com)
- **Admin Panel Template**: [AdminLTE](https://adminlte.io)

---



