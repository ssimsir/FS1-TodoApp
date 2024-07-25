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

## Dağıtım

Bu uygulama, [Render.com](https://render.com) üzerinde dağıtılmak üzere yapılandırılmıştır. Aşağıdaki adımları izleyerek uygulamayı Render.com'a dağıtabilirsiniz.

### Adım 1: Render.com Hesabı Oluşturun ve Giriş Yapın

### Adım 2: Yeni Web Hizmeti Oluşturun

1. "New" butonuna tıklayın ve "Web Service" seçeneğini seçin.
2. Projenizi barındırmak için GitHub, GitLab veya Bitbucket ile bağlanın.
3. Deploy etmek istediğiniz depoyu seçin.

### Adım 3: Proje Ayarlarını Yapılandırın

- **Name**: Uygulamanız için bir isim belirleyin.
- **Region**: Size en yakın olan bölgeyi seçin.
- **Branch**: Deploy etmek istediğiniz branch'ı seçin.
- **Build Command**: `npm install`
- **Start Command**: `npm start`

### Adım 4: Çevresel Değişkenleri Ayarlayın

"Advanced" sekmesinde, gerekli çevresel değişkenleri ekleyin (örneğin, `MONGODB_URI`).

### Adım 5: Uygulamayı Deploy Edin

"Create Web Service" butonuna tıklayın. Render.com, projenizi otomatik olarak build edecek ve deploy edecektir.

## CORS Sorunu Çözümü

Eğer CORS hatası alıyorsanız, Express.js uygulamanızda `cors` paketini kullanarak gerekli ayarları yapın.

### Adım 1: CORS Paketini Kurun

```bash
npm install cors
```

### Adım 2: CORS Orta Katmanını Ekleyin

`server.js` veya `app.js` dosyanıza şu kodu ekleyin:

```javascript
const cors = require('cors');

// CORS ayarları
const corsOptions = {
  origin: 'https://todoapp-ufnx.onrender.com', // Frontend URL'nizi buraya yazın
  optionsSuccessStatus: 200
};

app.use(cors(corsOptions));
```

## Katkıda Bulunma

Katkıda bulunmak isterseniz lütfen önce bir konu açın. Büyük değişiklikler için lütfen önce neyi değiştirmek istediğinizi tartışmak için bir konu açın.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Lisans

Bu proje MIT lisansı altında lisanslanmıştır. Daha fazla bilgi için `LICENSE` dosyasına bakın.
