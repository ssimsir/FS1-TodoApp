# Todo App

Bu proje, Node.js ve Express.js ile oluşturulmuş bir Todo uygulamasıdır. Uygulama, kullanıcıların yapılacak işler listesini oluşturmasını, görüntülemesini, güncellemesini ve silmesini sağlar. 

https://todo-app-fs1.vercel.app/

## Özellikler

- Todo ekleme
- Todo listeleme
- Todo güncelleme
- Todo silme

## Kurulum

Projenin çalıştırılabilmesi için Node.js ve npm'in yüklü olması gerekmektedir. Projeyi klonladıktan sonra bağımlılıkları yüklemek için aşağıdaki adımları izleyin.

### Adım 1: Depoyu Klonlayın

```bash
git clone <repository-url>
cd todo-app
```

### Adım 2: Bağımlılıkları Yükleyin

```bash
npm install
```

### Adım 3: Çevresel Değişkenleri Ayarlayın

Proje kök dizininde bir `.env` dosyası oluşturun ve gerekli çevresel değişkenleri ekleyin.

```env
PORT=3000
MONGODB_URI=<your-mongodb-uri>
```

### Adım 4: Uygulamayı Başlatın

```bash
npm start
```

## Kullanım

Uygulama, tarayıcı üzerinde çalıştırılmak üzere geliştirilmiştir. Aşağıdaki rotaları kullanarak Todo işlemlerini gerçekleştirebilirsiniz.

### Tüm Todo'ları Listeleme

```http
GET /todos
```

### Yeni Bir Todo Ekleme

```http
POST /todos
```

- Body (JSON):

```json
{
  "title": "Yeni Todo",
  "description": "Todo açıklaması"
}
```

### Bir Todo'yu Güncelleme

```http
PUT /todos/:id
```

- Body (JSON):

```json
{
  "title": "Güncellenmiş Todo",
  "description": "Güncellenmiş açıklama"
}
```

### Bir Todo'yu Silme

```http
DELETE /todos/:id
```

## Lisans

Bu proje MIT lisansı altında lisanslanmıştır. Daha fazla bilgi için `LICENSE` dosyasına bakın.
