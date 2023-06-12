# net-timerm
 C# Timer ve DateTimePicker denetimini kullanarak  belirtilen saat  saat ,dakika ve saniyede bir uyarı veren  proje olustuacağım.
 projeyi  datetimepicker ,2 adet button ş1 adet timer ve label denetiminde kulanacağız.
 Formumuzu oluşturduktan sonra dateTimePicker1 denetiminin Properties penceresinden Format özelliğini ayarlıyoruz.
 SoundPlayer sınıfını kullanabilmek için namespace’ i ekleyelim.
Ses dosyasını çalmak için kullanacağımız player nesnemizi global olarak tanımlayalı
Alarm Kur butonu için aşağıdaki kodları yazalım.

 
private void button1_Click(object sender, EventArgs e)
        {
            timer1.Start();
            label2.Text = "Alarm Kuruldu.";
            button1.Enabled = false
            Timer1 üzerinde çift tıklayarak Timer1_Tick olayına kodlarımızı yazalım.

 
private void timer1_Tick(object sender, EventArgs e)
        {
            DateTime dateTime = DateTime.Now;
            DateTime alarmTime = dateTimePicker1.Value;
 
            if(dateTime.Hour==alarmTime.Hour && dateTime.Minute==alarmTime.Minute && dateTime.Second == alarmTime.Second)
            {
                timer1.Stop();
                label2.Text = "Alarm Çalıyor...";
 
                
                player.SoundLocation = @"D:\Downloads\Music\alarm.wav";
                player.PlayLooping();
            }
        }
 
Burada benim kullandığım ses dosyası “D:\Downloads\Music\alarm.wav” olarak ayarlı durumda. Sizin kullanacağınız ses dosyası ismi ve konumu farklı olacaktır.

Durdur Butonu için kodlarımız:

 
private void button2_Click(object sender, EventArgs e)
        {
            player.Stop();
            label2.Text = "Alarm Durduruldu.";
            button1.Enabled=true;
        }
 
Form_Load olayı için kodlarımız:

 
private void Form1_Load(object sender, EventArgs e)
        {
            label2.Text = "...";
        }
 
Kodlarımızın tamamı:

 
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Media;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
 
namespace alarm
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
 
        SoundPlayer player = new SoundPlayer();
 
        private void button1_Click(object sender, EventArgs e)
        {
            timer1.Start();
            label2.Text = "Alarm Kuruldu.";
            button1.Enabled = false;
        }
        
        private void timer1_Tick(object sender, EventArgs e)
        {
            DateTime dateTime = DateTime.Now;
            DateTime alarmTime = dateTimePicker1.Value;
 
            if(dateTime.Hour==alarmTime.Hour && dateTime.Minute==alarmTime.Minute && dateTime.Second == alarmTime.Second)
            {
                timer1.Stop();
                label2.Text = "Alarm Çalıyor...";
 
                
                player.SoundLocation = @"D:\Downloads\Music\alarm.wav";
                player.PlayLooping();
            }
        }
 
        private void button2_Click(object sender, EventArgs e)
        {
            player.Stop();
            label2.Text = "Alarm Durduruldu.";
            button1.Enabled=true;
        }
 
        private void Form1_Load(object sender, EventArgs e)
        {
            label2.Text = "...";
        }
    }
}
 


 


