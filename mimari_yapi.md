Aşağıda verdiğin Notion içeriğini **metinlere dokunmadan**, yalnızca **Markdown (MD) formatına** çevirdim.
Başlık yapıları, kod blokları, alıntılar ve aside’lar MD uyumlu hale getirildi.

---

````md
# Genel Yapı

## 🧩 Client

### 🔹 **UI**

#### **Sorumluluklar**
- XAML ile kullanıcı arayüzü tasarımı.
- Kullanıcı etkileşimlerini yönetme (button click, form load vb.).
- Command pattern ile kullanıcı aksiyonlarını yönetme.
- Data binding ile veri görüntüleme ve düzenleme.
- Form validasyonları ve kullanıcı geri bildirimleri.
- Servis katmanına istek yapma ve sonuçları işleme.

#### **Teknik Yapılar**
- XAML ile UI tasarımı.
- Custom control'ler (TLabeledSearchTextBox, TComboEditorLabeled vb.).
- BrowseForm ve TransactionForm taban sınıfları: Liste ve kart formları için ortak UI davranışları.
- Infragistics controller’i.
- Event handler'lar ile kullanıcı etkileşimleri.
- ICommand interface ile command pattern.
- DelegateCommand ile komut yönetimi.
- OnPropertyChanged ile property binding.
- DataContext ile veri bağlama.
- OneWay, TwoWay binding.
- Expander (Expanded event) ile tembel (lazy) yükleme: Combo verileri sadece ilk açılışta çekilir.
- TTabControl (TabControlSelectionChanged event) ile tembel (lazy) yükleme.
- Execute<TReq,TResp>() generic çağrı mekaniği: İstemci tarafında tanımlı ancak servis katmanına delegasyon yapan standart iletişim noktası.

#### **Notlar**
- Form ekranlarındaki işlem butonları kod tarafında tanımlanan command’lara göre geliyor.

---

### 🔹 **Types**

#### **Sorumluluklar**
- Client-Server arasında veri transferi için veri modelleri (Contract, Request) sağlama.
- UI ve servisler arasında taşınacak verinin yapısını belirleme.
- Serileştirilebilir (Serializable) veri nesneleri sağlama.
- UI ile veri bağlama (data binding) için gerekli bildirim mekanizmasını sağlama.

#### **Teknik Yapılar**
- Partial Class ve Designer File Kullanımı: Otomatik ve manuel kod ayrımı.
- Property’ler ve Field’lar: Taşınacak verinin alanları.
- OnPropertyChanged ile property change notification.
- Serializable attribute ile serileştirme.
- Nullable property'ler ile optional veri alanları.
- Default value assignment.

---

### 🔹 **Proxy**

#### **Sorumluluklar**
- UI ile servis/iş katmanı arasındaki iletişimi soyutlama.
- Servis çağrılarını merkezi bir noktadan yönetme.
- Request/Response nesnelerinin iletimini sağlama.

#### **Teknik Yapılar**
- Executer<TReq, TResp> generic sınıfı: Tüm servis çağrılarında kullanılan temel proxy mekanizması.

---

## 🧩 Server

### 🔹 **Service**

#### **Sorumluluklar**
- Client (UI) ile Server (Orchestration/Business) arasındaki iletişimi sağlama.
- Gelen istekleri ilgili Orchestration metodlarına yönlendirme.

#### **Teknik Yapılar**
- WCF servis altyapısı.

---

### 🔹 **Orchestration**

#### **Sorumluluklar**
- Client request'lerini karşılama ve yönlendirme.
- Business katmanı ile koordinasyon.
- Birden fazla business fonksiyonu için transaction yönetme.
- İş akışlarını organize etme  
  - Business katmanında tek amaca hizmet eden birden fazla fonksiyon, orchestration katmanında bir araya getirilir, gerekirse transaction kullanılarak tutarlılık sağlanır.
- Request validation ve response hazırlama.

#### **Teknik Yapılar**
- Partial Class ve Designer File Kullanımı: Otomatik ve manuel kod ayrımı.
- ObjectHelper ile context yönetimi.
- Method delegation ile business layer çağrıları.
- Transaction yönetimi.
- GenericResponse ile standart response yapısı.
- Error handling ve result management.

---

### 🔹 **Business**

#### **Sorumluluklar**
- Orchestration’dan gelen çağrıları işleme.
- İş kurallarını ve domain mantığını uygulama.
- Veritabanı işlemlerini (CRUD, stored procedure çağrısı) gerçekleştirme.  
  - Prosedür ve business fonksiyonu tek görev yapar, orchestration fonksiyonu bunları organize eder.
- SQL parameter'ları hazırlama ve binding.
- SQL command'ları oluşturma ve execute etme.
- SqlDataReader'dan object'lere veri aktarımı.
- Veritabanından gelen verileri contract'lara mapping.
- Database transaction yönetimi.
- Orchestration’a sonuç dönme.

#### **Teknik Yapılar**
- Partial Class ve Designer File Kullanımı: Otomatik ve manuel kod ayrımı.
- ObjectHelper base class ile database context.
- SqlCommand ile stored procedure çağrıları.
- SqlDataReader ile veri okuma.
- DBLayer ile database abstraction.
- Parameter binding ile SQL injection koruması.
- SQLDBHelper ile type-safe veri dönüşümleri.
- GenericResponse ile standart return yapısı.

---

### 🔹 **Database**

#### **Sorumluluklar**
- CRUD işlemlerini gerçekleştirme.
- Stored procedure’ler ile karmaşık sorgu ve işlemleri yönetme.

#### **Teknik Yapılar**
- Tables, Views, Stored Procedures, Functions

---

> 💡 Stored Procedure/Table etrafında otomatik kod üretimi ile oluşturulmuş katmanlı mimari.

---

> ⚙️  
> **Client (UI/Types)**  
> ⇣ Kullanıcı arayüzünde bir işlem tetikleniyor.  
> ⇣ Request nesnesi dolduruluyor.  
> ⇣ Execute metodu çağrılıyor.  
>
> **Service (Proxy)**  
> ⇣ Execute metodu, arka planda bir servis çağrısı yapıyor.  
> ⇣ Request nesnesi serialize edilip, sunucuya gönderiliyor.  
>
> **Server (Orchestration/Business)**  
> ⇣ Sunucuda ilgili servis endpoint'i isteği alıyor.  
> ⇣ Execute’a verdiğimiz request üzerinden hangi namesapce altındaki metotlara gideceğini anlıyor.  
> ⇣ Request.MethodName ile hangi işlemin yapılacağı belirleniyor.  
> ⇣ Sunucu tarafında Orchestration katmanı ilgili metodu çağırıyor.  
> ⇣ İş kuralları ve veri erişimi burada gerçekleşiyor.  
>
> **Database**  
> ⇣ Gerekli işlemler (güncelleme, ekleme, silme) veritabanında yapılıyor.  
> ⇣ Sonuçlar bir GenericResponse<T> ile dönüyor.  
>
> **Client**  
> ⇣ Sunucu, sonucu serialize edip istemciye döner.  
> ⇣ Execute metodu sonucu deserialize edip, client koduna iletir.

---

# Liste Ekranları

## **UI**

### **İlk Veri Yükleme**

```csharp
public override void LoadData()
{
    base.LoadData();
    BindingDataClass.IsFullData = false;
    FullListCommandExecute(); // İlk veri yükleme tetikleniyor
}
````

---

## **UI ⇢ Proxy ⇢ Service ⇢ Orchestration**

### **Request Oluşturma ve Servis Çağrısı**

```csharp
private void FullListCommandExecute()
{
    StockCardListRequest request = new StockCardListRequest();
    request.MethodName = "GetStockCardList";
    request.RelatedCustomerId = BindingDataClass.RelatedCustomerId;
    request.StockIdStart = BindingDataClass.StockStartId;
    request.StockIdEnd = BindingDataClass.StockEndId;
    request.UserId = ApplicationContext.User.Userid;
    request.IsFullData = BindingDataClass.IsFullData;

    GenericResponse<List<StockCardListContract>> response =
        Execute<StockCardListRequest, GenericResponse<List<StockCardListContract>>>(request);
}
```

---

## **Orchestration ⇢ Business**

```csharp
public GenericResponse<List<StockCardListContract>> GetStockCardList(StockCardListRequest request, ObjectHelper objectHelper)
{
    OSYS.Business.UsedCars.StockCardList bo = new OSYS.Business.UsedCars.StockCardList(objectHelper.Context);
    GenericResponse<List<StockCardListContract>> response =
        bo.GetStockCardList(request.StockIdStart, request.StockIdEnd, request.UserId);

    return returnObject;
}
```

---

## **Business ⇢ Database**

```csharp
command = this.DBLayer.GetDBCommand("UsedCar.sel_GetStockCardList");
this.DBLayer.AddInParameter(command, "@StockIdStart", SqlDbType.Int, stockIdStart);
sp = this.DBLayer.ExecuteReader(command);
```

---

## **Database**

```sql
SELECT Top (@count)
vMn.StockId, vMn.InsertDate, vMn.BranchName
FROM UsedCar.vwStockCard vMn (nolock)
```

---

## **UI**

```csharp
if (!response.Success)
{
    ShowStatusMessage(GlobalKeysProperties.Instance.ProcesesFailure, DialogTypes.Warning);
}
else
{
    ControlGridDataSource = response.Value;
}
```

---

> 📌
> **StockCardListContract**
> Veritabanından çekilen ve ekranda listelenen stok kartı verilerini temsil eder.
>
> **StockCardListRequest**
> Kullanıcı filtrelerini business katmanına taşır.
>
> **BindingDataClass**
> UI filtre alanlarını yöneten yardımcı sınıftır.

---

# Diğer Notlar

> Proje derlendiğinde dll’ler `C:\OSYS\Client\bin\` altına kopyalanır.
> `C:\OSYS\Client\Bin\OSYS.UI.Container.exe` çalıştırılır.
>
> **Client** için `OSYS.UI.Container.exe`
> **Server** için `w3wp.exe` debug attach yapılır.
