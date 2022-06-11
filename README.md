# Su Seviyesi Kontrolü
## MARMARA ÜNİVERSİTESİ
## TEKNOLOJİ FAKÜLTESİ
## Elektrik Elektronik Mühendisliği 
## Ölçme ve Enstrümantasyon
### Ad-Soyad: Aylin ÖZCAN
### Öğrenci Numarası: 170519046
### Kullanılan Malzemeler
- Arduino UNO
- Su Seviyesi Sensörü
- Buzzer Aktif Ses Modülü
- Erkek-Erkek Jumper Kablo
- Dişi-Erkek Jumper Kablo 

### Devrenin Board Tasarımı

Arduino UNO kullanılarak su seviyesi kontrolü sağlandı. Kullanılan Su Seviyesi sensörünün iletken hatlarının su ile teması sonucu sensörün çıkış pininde analog bir değer okunmaktadır. Okunan bu değer belirlenen eşik değerinin üstünde olduğu takdirde uyarı vermesi için Buzzer Aktif Ses modülü kullanılmıştır. 
| Su Seviyesi | Buzzer |
|--|--|
| Su Seviyesi<500 | Ses çıkarmaz |
| Su Seviyesi>500 | Ses çıkarır |

<img width="235" alt="Ekran görüntüsü 2022-06-05 174042" src="https://user-images.githubusercontent.com/93606005/172055996-c616f7e6-dbb2-46e6-be87-28a3bec5b7d6.png">

### Arduino Kod
```
//Aylin ÖZCAN 170519046

int sensor=A0;
int buzzer=8;
int esikdegeri=500;
int suseviyesi;

void setup() {
  Serial.begin(9600);
  pinMode(buzzer,OUTPUT);
  
}


void loop() {
  suseviyesi=analogRead(sensor);
//Serial.print("Sensor degeri: ");
  Serial.println(suseviyesi);
  delay(100);
  if(suseviyesi > esikdegeri){
    digitalWrite(buzzer,HIGH);
    delay(100);
    digitalWrite(buzzer,LOW);
    delay(100);
  }

  else{
    digitalWrite(buzzer,LOW);
    }
}

```
### Kontrol Paneli ve Blok Diyagramı
<img width="593" alt="Blok diyagramı" src="https://user-images.githubusercontent.com/93606005/172056337-a894e6a9-31f1-4923-a059-bdba49d85fbd.png">
<img width="669" alt="front panel" src="https://user-images.githubusercontent.com/93606005/172056367-e9c9f6f6-3064-4dcb-8acd-739260bb7f46.png">

### Arduino ve Kontrol Paneli Çıktıları
- Su Seviyesi sensörüne su teması olmadığında

<img width="792" alt="Arduino sıfır" src="https://user-images.githubusercontent.com/93606005/172056442-298a3625-a20e-4ce1-b869-1b511041c68a.png">
<img width="671" alt="Labview sıfır" src="https://user-images.githubusercontent.com/93606005/172056533-f5fc2e41-5783-4031-966f-44dc54146078.png">

- Su Seviyesi 570

<img width="794" alt="arduino573" src="https://user-images.githubusercontent.com/93606005/172056581-bbabfa50-6b80-4668-bb7d-ec70bbff62f1.png">
<img width="651" alt="labview 577" src="https://user-images.githubusercontent.com/93606005/172056590-c8e718cd-eb34-4ede-bd7d-ec2aee9a8b21.png">

- Su Seviyesi 748

<img width="817" alt="arduino 750" src="https://user-images.githubusercontent.com/93606005/172056621-9219bbb5-8f27-4673-a253-216c8293cdbb.png">
<img width="710" alt="Ekran görüntüsü 2022-06-05 162744" src="https://user-images.githubusercontent.com/93606005/172056609-6d4036b5-e97b-4d52-b03f-88bc7c70547e.png">

| Su Seviyesi | Buzzer |
|--|--|
| Su Seviyesi=0| Ses çıkarmaz |
| Su Seviyesi=570|Ses çıkarır |
| Su Seviyesi=748 |Ses çıkarır |

[LABWİEV DOSYALARINA ERİŞİM LİNKİ ][(https://drive.google.com/drive/folders/1sfm7uOUn1OdS-ZRUzJ6rGv0hdDpRFc0G?usp=sharing)](https://drive.google.com/drive/folders/1qGoCeAHdDEwEiF3CEodmcjsGhMJuUOAf?usp=sharing)


