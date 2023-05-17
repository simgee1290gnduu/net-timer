# net-timerm
 C# Timer ve DateTimePicker denetimini kullanarak belirtilen saat, dakika ve saniyede bir uyarı sesi veren örneği oluşturacağız
 Örneğimizde DateTimePicker , 2 adet Button, 1 adet Timer ve Label denetimlerini kullanacağız.
Formumuzu oluşturduktan sonra dateTimePicker1 denetiminin Properties penceresinden Format özelliğini  ayarlıyoruz.
SoundPlayer sınıfını kullanabilmek için namespace’ i ekleyelim
using System.Media;
Ses dosyasını çalmak için kullanacağımız player nesnemizi global olarak tanımlayalım.
SoundPlayer player = new SoundPlayer();
Alarm Kur butonu için kodlarımızı yazalım
Timer1 üzerinde çift tıklayarak Timer1_Tick olayına kodlarımızı yazalım.
durdur  butonu ve  form_load  olayı için kodarımızı ayarlıyoruz 
