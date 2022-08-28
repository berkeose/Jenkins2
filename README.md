# Jenkins 

## EN BASİT HALİYLE NASIL ÇALIŞIR?
![1_S8C5nrFNzK1UJ-MJNKXFHQ](https://user-images.githubusercontent.com/81867200/187045350-de74b888-570a-4e28-833b-728b52bb9189.jpeg)

### Jenkins basit tanım ile, bir yazılım projesinde dinamik olarak gerekli olan yapısal işlemleri otomatize ederek projeyi hızlı, kolaylıkla hata raporlaması ve kolay test edilip hataların fixlenebilmesini sağlayan bir CI(Continous Integration) aracıdır.


## JENKINS'IN ETKİLEŞİMLERİ
![133](https://user-images.githubusercontent.com/81867200/187045617-a2fb7581-611c-4064-b974-3098c7c72163.jpg)

## JENKINS MASTER SLAVE YAPISI

### -Bazı durumlarda, yapılarınızı test etmek için birkaç farklı ortama ihtiyacınız olabilir. Bu ihtiyacı tek Jenkins sunucusu ile karşılayamazsınız.
### -Çok büyük projeler her commit için build edildiğinde tek sunucu tüm yükü idare edemez.
### -Yukarıdaki belirtilen ihtiyaçları karşılamak için Jenkins dağıtık mimari ortaya çıkmıştır.

### JENKINS DAĞITIK MİMARİ
### Jenkins, dağıtık yapıları yönetmek için Master-Slave mimarisi kullanır. Bu mimaride Master ve Slave TCP/IP protokolü üzerinden iletişim kurar.

### Jenkins Master
### -Build işlemlerini zamanlar.
### -Build işlemleri için Slave oluşturur.
### -Slave sunucuları izlemek.
### -Build sonuçlarını sunar.
### -Doğrudan build işlemi yapabilir.

### Jenkins Slave
### -Jenkins Master sunucudan gelen istekleri takip eder.
### -Çeşitli işletim sistemlerinde çalışabilir.
### -Master sunucudan gelen build işlemlerini istenildiği şekilde gerçekleştirir.

### Aşağıdaki şemada 3 Slave sunucu yöneten bir Jenkins Master sunucu var.
![jenkins-master-slave](https://user-images.githubusercontent.com/81867200/187045880-111673f6-cc0b-4ed3-a770-222ace6ea8b1.png)

## CONTINUOUS DELIVERY - SÜREKLİ TESLİMAT
## Jenkins yazılım geliştirme sürecinde belirlenen kaynaktan projeye ulaşır ve belirlenen şartlarda çalışıp projeyi derler. Derleme başarılı ise testleri çalıştırır. Bu iki aşamada herhangi bir sorunla karşılaşmazsa 3. aşama olan deploy işlemini gerçekleştirir. Bu durum Sürekli Teslimat (CD: Continious Delivery) işlemi olarak nitelendirilebilir. Sürekli teslimatta amaç projeyi sürekli güncel ve çalışır bir vaziyette tutmak ve canlı ortama benzer bir ortama aktarmaktır. Jenkins eğer build veya test aşamasında herhangi bir hata ile karşılaşırsa deploy işlemini gerçekleştirmez ve geliştiriciyi bilgilendirir. Bu süreç sürekli tekrar eder. Jenkins bunlara ek olarak statik analiz, versiyon kontrol sistemi, dağıtım gibi birçok geliştirme sürecini entegre eder.

### "Continuous Delivery doesn't mean every change is deployed to production ASAP.
###    It means every change is proven to be deployable at any time."
###           Carl Caum from the Puppet Blog

### Kısaca Sürekli Teslimat(CD),deploy etmek zorunda olmadığın ama her zaman buna hazır olduğun andır.

### Continus Delivery aşağıdaki üç disiplinin kombinasyonu demektir.
### - Continuous Integration
### - Continuous Testing
### - Continuous Deployment (istendiğinde)
### Bu sürece konfigurasyon yönetimi de eklenecek.

### HEDEFLER
### -Kullanıcıya çalışan yazılımı olabildiğince hızlı verebilmek
### -Sıklıkla otomatize edilmiş sürümler sunmak

### FAYDALAR
### Düşük risk, stres
### -Hızlı yatırımın geri dönüşü (ROI)
### -İş ihtiyaçlarına geliştirilmiş yanıt verebilmek
### -İyileştirilmiş kalite
### -Hızlıca hataya düşmek (fail-fast)
### -Yüksek özgüven

## DELIVERY    VS.      DEPLOYMENT

### DELIVERY:
### Sırf yazılımcı yazdığı kodun kullanıldığını görsün diye mutlu etmek ama sonuçlardan dolayı patronu endişelendirmek için yapılır
### Delivery ile yapılan sürüm sonuçları geri alınamayacak ve hassas kararların verilmesini gerektiren, elle yapılacak sürümdür.

### DEPLOYMENT:
### Daha çok cloud ortamında sunucularını hızlıca geri dönebilen, ortak componenti ve veritabanları olmayan, işin hatasız olacağını çok geniş verilerle, regresyonlarla koşan, business’ın “tüm sorumluluk bendedir, kesinti mesinti hepsinin hesabını ben veriyorum” diyebildiği şirketlerde kullanılır.
### Deployment ile yapılan sürüm otomatik olduğu için ya hassas kararların verilmesi gerekmeyen ya da arkasında ciddi testlerin yapılarak sonucun sorunsuz olacağına inanıldığı otomatik yapılan sürümdür.

![cdvscd](https://user-images.githubusercontent.com/81867200/187047120-fd733089-6dd3-43e5-bae9-a13bf1d8ebc1.png)

## Continuous Delivery vs. Deployment
### Sürekli Teslimat(cDelivery), başarılı olan bir yapıyı (build) bir ortama atmanın bir yoludur. 
### Burada teslimat ile dağıtım arasında ince bir ayrım vardır.
### Teslimat manuel yolla, dağıtım ise otomatik yapılır. 
### Sürekli teslimat düzgün bir şekilde uygulandığında, müşteriler her zaman standartlaştırılmış bir test sürecinden geçmiş hazır yapıya sahip olacaklardır.

## CONTINOUS INTEGRATION
### Kodu alıp kaynak yönetim sisteminde derleyerek üstünde unit testleri ve otomatize edilmiş süreçlerden geçirip kodun sorunsuz olduğunu gördüğümüz süreçtir.
### Yazılan kodun, geliştirilen modülün — kısaca geliştirme ortamından çıka gelen bir parçanın — projeye dahil edilmesi esnasında bir takım süreçlerden geçirilmesine verilen isim. Bağımlılıkların repolardan indirilmesi, projeye dahil edilmesi, geliştirilen kod parçacığın testlerden (unit, integration, vs…) geçirilmesi, olası durumlara göre geliştiriciye veya işin sorumlusuna bilgi verilmesi (push notification, sms, mail, vs…), işin paketlenmesi gibi eylemlerin tamamı, genellikle bu kavramın bir parçası olarak hayatımızda yer ediyor.

### Sürekli entegrasyon (Continuous Integration = CI), kod üzerinde yapılan her değişikliğin ardından, tüm sistemin çalışır durumda olduğunu, yapılan değişikliğin sistemin bazı bölümlerinde kırılmalara yol açmadığını tespit etmek için kullanılan yöntemdir.
### Kırılmaları birim testlerle tespit ederiz. Bu testler, yapılan değişikliğin neticesi olarak yeni bir yapı (build) hazırlandıktan sonra otomatik olarak çalıştırılır.
### Yapılan değişiklik yeni yapının bir parçası olduğu için, testlerde oluşan hatalar, yapılan değişikliğin sistemi kırdığı anlamına gelmektedir. Bu durumdan tüm programcılar haberdar edilerek, hatanın bir an önce giderilmesi ve testlerin her zaman olumlu sonuç vermesi sağlanır.
### Sürekli entegrasyon ile programcılar tarafından kod üzerinde yapılan çalışmalar neticesinde her zaman çalışır bir sürümün oluşması sağlanmış olur.

## NEDEN SÜREKLİ ENTEGRE EDİLMELİ?
### Oluşturduğunuz yazılım sistemini sürekli entegre etmiyorsanız, zamanı gelince toptan entegre etmek zorundasınız.  Bunun, neden yazılım hayatınızda karşılaşabileceğiniz en büyük sorun olabileceğini bir örnek vererek açıklamak istiyorum.
### Şimdi şunu hayal edin: Yeni bir otomobilin tasarlanması projesinde yer aldınız. Otomobil tasarlandı ve otomobili oluşturan parçalar 5 değişik ülkede, 20 değişik firma tarafından üretildi. Bu ülkelerde kullanılan uzunluk ve ağırlık birimleri (metre, kg vs.) değişik olabilir. Görev dağılımı esnasında yanlış anlamalardan dolayı üretilen parçalar birbirine uyumlu olmayabilir. Eğer tüm parçalar üretildikten sonra bir çırpıda tüm otomobili oluşturmak isterseniz, üretim sürecinde meydana gelen hataları daha önceden tespit edemediğiniz için, yamuk yumuk bir otomobil ortaya çıkacaktır. Ama üretim esnasında koordineli bir şekilde otomobili parça parça bir araya getirip, parçalar uyuşuyor mu diye kontrol etmiş olsaydınız, meydana gelen uyuşmazlıkları çok erken tespit ederek, gerekli değişiklikleri yapabilirdiniz. Bu yazılım sektörü için de geçerli.  Oluşturulan sistem komponentleri ne kadar erken entegre edilirse, oluşan uyuşmazlıklar o kadar erken tespit edilir ve gerekli değişiklikler yapılabilir.

### Sürekli entegrasyon çevik süreçlerde çok önemli bir yazılım metodudur. Sistem üzerinde yapılan her değişiklik sürekli entegrasyonu otomatik olarak gerçekleştiren sunucu tarafından kontrol edilir.  Yazılımda kırılmalar oluşması (compile hataları, eksik sınıflar vs.) durumunda, tüm ekip sürekli entegrasyon sunucusu tarafından uyarılır. Bu geribildirim sayesinde entegrasyonun ne safhada olduğu anlaşılır.

## CONTINOUS TESTING
### Derlenmiş kodun üstünde entegrasyon, fonksiyonel vb. testlerin geçirildiği ve koda güvenin sağlandığı süreçtir.

## NEDEN CONTINOUS TESTING
### Çevikleşen yazılım dünyasının omurgasını oluşturan sürekli geri bildirim yaklaşımına hayat veren “Continuous Testing”; daha hızlı, hatasız ve kapsamlı test aktiviteleri ile bir araya getirilen yazılım parçalarının sorunsuz çalıştığından emin olmayı sağlar.
## Continuous Testing, DevOps dönüşümünün en önemli ve ilk adımlarındandır. Kurumsal çevikliğin sağlanmasında önemli bir mühendislik aşaması ve ürüne yeni eklenen özelliklerin mevcut fonksiyonaliteyi bozmadığının garantisidir.

![ct](https://user-images.githubusercontent.com/81867200/187047623-617e5ade-e0a2-4cd8-a1e7-694485c1bb5f.png)

## JENKINS DÜNYASINDA GEÇEN TEMEL KAVRAMLAR

### Node
### Node, jenkins prosesinin üzerinde çalıştığı sunucuyu ifade ediyor.
### Pipeline
### Pipeline ise, işlerin ardışık bir sırada yapılması, bir işlemin çıktısının sonraki gelen işlemin girdisi olması anlamına gelmektedir.
### Fabrikadaki üretim bantlarını aklımıza getirelim. Üretilen eşya, hattın içerisinde farklı duraklara gelir. Her durakta bir işlem görür ve sonraki aşamaya geçer.
### Stage
### Pipeline içerisinde yer alan fazları ifade eder. Örneğin standart bir yazılım projesinde build -> test -> deploy adımlarından her birisi bir fazı ifade eder.
### Step
### Stage içerisinde yer alan adımları ifade eder.

### Jenkins üzerinde kodumuzun geçtiği aşamaları düşünelim:


### Build -> Test -> Deployment
### Build (derleme) aşamasını bir evre (stage) olarak düşünelim. Test evresi de sonraki evre. Deployment evresi de en son çalışacak evre olarak düşünelim. Bu işlemler Jenkins üzerinde ardışık bir sırada çalışmaktadır.

### Build işlemi hatalı olursa, yani kodumuz derlenmez ise, sonraki evreye geçmeyecektir. Aynı şekilde test safhasında hata oluşursa, deployment işlemi gerçekleşmeyecektir.

### Pipeline mantığı bu şekilde çalışmaktadır.

## JENKINS'IN YAPISI
![piplen](https://user-images.githubusercontent.com/81867200/187047761-0bcf2f7f-62e1-4ac9-8c3c-baadcb2291b1.png)

### Her iş bir diğerini tetikler, eğer başarısız olan iş olursa tüm süreç başarısız olarak kesilir

## Pipeline & Groovy’e Dair Bilinmesi Gerekenler
### Boru Hattı davranışını anlamak için nasıl yürütüldüğü hakkında birkaç noktayı anlamalısınız.
### - Adımların (steps) dışında, tüm pipeline mantığı, Groovy koşulları, döngüler, vb. ister basit ister karmaşık
### olsun, düğüm (node) bloğunun içinde bile olsa master Jenkins üstünde koşar.
### - Adımlar (steps), uygun olan yerlerde iş yapmak için uygulayıcıları (executors) kullanabilirler, ancak her
### adım küçük de olsa master’a ek yük yükler.
### - Pipeline kodu Groovy olarak yazılır, ancak yürütme modeli derleme zamanında Devam Geçiş Stili'ne
### (CPS -Continuation Passing Style-) dönüştürülür.
### - Bu dönüşüm, pipeline için değerli güvenlik ve dayanıklılık sağlar, ancak bazı sıkıntılarla birlikte gelir:
### - Adımlar (steps) Java kodunu çağırabilir ve Java kodu sayesinde hızlı ve verimli bir şekilde
### çalışabilir, ancak Groovy normalden daha yavaş çalışır.
### - Groovy çok daha fazla bellek gerektirir, çünkü nesne tabanlı bir sözdizimi bellekte tutulur.
### - Boru hatları, master’ın fail olmasından kurtulabilmek için programı ve durumunu kalıcı hale getirir.

![DAĞITIMHATTO](https://user-images.githubusercontent.com/81867200/187048073-245b2060-a931-4a56-bb03-4c217b06c277.png)

## JENKINS İÇİNDE KULLANILAN TEKNOLOJİLER
![JENKİNSİÇİ](https://user-images.githubusercontent.com/81867200/187048107-bf8e9a60-cc46-4223-bc59-161a57335c8e.png)

## JENKINS MİMARİSİ
### - Jenkins, her yazılım gibi bir işletim sistemi(host) üstünde koşar.
### - Java application container veya application server üstünde koşar (varsayılan olarak Jetty kullanır)
### - Jetty ve jenkinsi başlatma, durdurma ve izlemek için harici bir servis uygulaması çalışır.
### - Views ile projeleri(jobs olarak da bilinir) ve klasörleri gruplar Jenkins.
### - Projeler iş kuyruklarını (job queue) ve bunları çalıştıracak executerları tetikler.
![arcj](https://user-images.githubusercontent.com/81867200/187048310-fd148097-fdbc-42a6-80b8-7c65dc7f3261.png)


![1](https://user-images.githubusercontent.com/81867200/187048401-cc0ebb49-4845-47b7-a87f-6f004b5035e9.png)


### İlk olarak bir job yaratmak için bir Job ismi belirtip nasıl yapılandıracağımızı seçiyoruz.
![1](https://user-images.githubusercontent.com/81867200/185698209-2a3b7742-bf35-4808-b705-e02707e11958.png)
### WORKSPACES
![2](https://user-images.githubusercontent.com/81867200/187048560-60ee566d-0254-4c76-b29b-9d0e115c707a.png)

### DİZİN LAKAPLARI
![3](https://user-images.githubusercontent.com/81867200/187048943-e2d8c726-dfd3-4bdb-aa48-7f858de7c1b6.png)

### PROJE-JOB YAPILANDIRMA DURUMLARI
![4](https://user-images.githubusercontent.com/81867200/187048996-79a4849d-2525-4839-a052-8cbc848dbd5c.png)

### PIPELINE NASIL TANIMLANIR?
### Jenkins Pipeline tanımı JenkinsFile isminde bir dosyaya yazılır.

### İki türlü tanımlama şekli var: Declarative, Scripted

### Bu iki tür pipeline yazım şeklinden declarative olanı sonradan gelmiş ve daha gelişmiş olanıdır.
### Resmi Jenkins dokümanlarında tavsiye edilen yöntem declarative tanımlamadır.
### Scripted tanımlamada groovy kullanılarak yapılır. Declarative tanımlama tavsiye edilmesine rağmen, scripted tanımlama ile herhangi bir kısıtlama olmadan herşeyi yapabiliyorsunuz.
### Scripted tanımlama bize daha esnek bir tanımlama imkanı sunuyor. İkisini de tercih edebilirsiniz.

## DECLARATIVE VS SCRIPTED
### Deklaratif ardışık düzen ile Komutlu ardışık düzen arasındaki temel fark, sözdizimleri ve esneklikleriyle ilgilidir.

### Deklaratif pipeline, pipeline’ı kod konsepti olarak destekleyen nispeten yeni bir özelliktir. Pipeline kodunun okunmasını ve yazılmasını kolaylaştırır. Bu kod Git gibi bir kaynak kontrol yönetim sistemine kontrol edilebilen bir Jenkinsfile içinde yazılmıştır.

### Oysa (Scripted) kodlanmış pipeline, kodu yazmanın geleneksel bir yoludur. Bu satırda Jenkinsfile Jenkins UI örneğine yazılır. 
### Bu boru hatlarının her ikisi de Groovy DSL'ye dayanmasına rağmen, scripted pipeline, Groovy tabanlı daha katı sözdizimleri kullanır çünkü Groovy üzerine inşa edilen ilk pipeline idi. 

### Bu Groovy komut dosyası genellikle kullanıcılar tarafından benimsenmediğinden, daha basit ve daha seçenekli bir Groovy sözdizimi sunmak için deklaratif ardışık düzen eklendi.

### Deklaratif (bildirimli) ardışık düzen, "pipeline" etiketli bir blok içinde tanımlanırken, komut dosyası verilen ardışık düzen, bir "node" içinde tanımlanır.

## SCRIPTED
### Scripted pipeline, Jenkins pipeline’ı kod olarak yazmanın geleneksel bir yoludur. İdeal olarak, Scripted pipeline Jenkins web arayüzünde Jenkins dosyasında yazılır. 

### Deklaratif düzenden farklı olarak, scripted pipeline katı bir sözdizimi kullanır. Bu nedenle, scripted pipeline kodlanmış pipeline üzerinde büyük denetim sağlar ve komut dosyasının akışını kapsamlı bir şekilde değiştirebilir.
### Bu, geliştiricilerin kod olarak ileri ve karmaşık boru hattı geliştirmelerine yardımcı olur.
![5](https://user-images.githubusercontent.com/81867200/187049274-0abd17c4-3b2f-4307-9772-97fb8c4f35ee.png)
### Node, Jenkins mimarisinin, node veya agent projelerin iş yükünün bir kısmını çalıştıracağı ve ana düğümün (master node) işin yapılandırmasını (configuration) işleyeceği kısmıdır.
### Stage bloğu görev ilerledikçe tek bir aşama veya çoklu olabilir. Ve ortak aşamaları olabilir.

![6](https://user-images.githubusercontent.com/81867200/187049350-084f4826-9e8c-412d-b4c8-180af842be6e.png)
### -groovy kodunu kullanabilirsin
### -Hata kontrolü ve raporlaması mevcut

![7](https://user-images.githubusercontent.com/81867200/187049384-bbda9180-1044-411f-b5d5-82ec6c723494.png)
###  -Ön tanımlı kısımlar
### - Kod mantığı kullanılamaz
### - DSL- yönelimli kontrol ve raporlama mevcut
### - Blue-Ocean uyumlu

## PARAMETER
### İster önceden ister Jenkinsfile üstünde parametreleri tanımlayalım, projeyi build ettiğimizde parametreleri görebiliriz.

## INPUT & PARAMETER & CHOICE
![8](https://user-images.githubusercontent.com/81867200/187049452-e39a9300-7e38-4d87-b249-ec00c0d30441.png)

![9](https://user-images.githubusercontent.com/81867200/187049601-cc9e233c-9923-40f0-9502-85ad6fd8c6c9.png)

## TRY & CATCH
![10](https://user-images.githubusercontent.com/81867200/187049695-083eaea4-da44-4d27-9b25-7278197b1645.png)

## AGENT
### Agent, tüm boru hattının (pipeline) veya özellikle bir aşamanın (stage) çalıştığı yerdir. Örneğin, Docker. Agent aşağıdaki parametreleri alır:

### ● any: tüm pipeline’ın kullanılabilir herhangi bir agent üstünde çalışacağı anlamına gelir.
### ● none: blok altındaki tüm aşamaların (stage) ayrı olarak agent ile bildirilmesi gerektiği anlamına gelir.
### ● label: sadece Jenkins ortamı için bir etiket
### ● docker: Docker ortamında pipeline’ı çalıştırmak içindir.

## JENKINS DOMAIN SPECIFIC LANGUAGE
### - Groovy temelli
### - Süreçlerin adımlarını orkestre eder
### - Bir pipeline script gibi job içinde veyaa repository içinde tutulan harici bir dosya olarak “Jenkinsfile” adında saklanabilir.
![ne](https://user-images.githubusercontent.com/81867200/187049896-a75bbc98-57a5-4631-84e0-fc022ae5435f.png)

## YEREL MAKİNEYE JENKİNS KURULUMU
### -https://www.jenkins.io/doc/pipeline/tour/getting-started/ adresinden adım adım takip edebilirsiniz.
### -https://www.jenkins.io/download/ adresten war dosyasını indir.
### -konsoldan şu komutu çalıştır.
### - java -jar jenkins.war --httpPort=8080
### - internet gezgininden http://localhost:8080 adresini aç
### jenkins.war çalıştırıldığında $user.home/.jenkins dizinini oluşturmak ister. Hızlıca çalıştırmak için oluşturduğumuz run.bat dosyası çalışıp uygulama ayaklandığında %USERPROFILE%\.jenkins klasörü oluşur ve pluginler bu klasöre yüklenir.
![ym1](https://user-images.githubusercontent.com/81867200/187050080-87e067f5-35ac-4ab7-b282-7e6ffc225dec.png)
### Farklı bir dizinde .jenkins klasörünü barındırmak istersek(https://www.youtube.com/watch?v=m47MWSXNslg) ortam değişkenlerinden JENKINS_HOME anahtarına istediğimiz yeni dizinin adresini girip .jenkins dizininin içeriğini taşıyabiliriz.
![ym2](https://user-images.githubusercontent.com/81867200/187050195-8a2b97b6-28de-4349-bfc5-e71e4927320c.png)

### İleride çalıştıracağımız “echo cem” işleminin çıktılarını aşağı tarafta incelediğimizde; jenkins’in docker yansısı

### - eğer linux ise, echo işlemini /bin/sh üstünde çalıştırmakta,
### - windows ise cmd üstünde koşturmakta

### Host olarak hangi işletim sistemi koşuyorsa buna uygun command yazmamız veya docker yansısını komutlarımıza göre seçmemiz gerek.

### Linux host üstünde koşan Jenkins için sh ile çalışıyorken bat ile komutlarımızı çalıştırıyoruz.

![ym3](https://user-images.githubusercontent.com/81867200/187050248-0b5fefc2-055d-4eb7-b7fd-846d19dca392.png)

## DOCKER İLE JENKINS KURULUMLARI

### Master Agent Node
### Birinci ve yöneten Jenkins düğümünün kurulumu

### Hangi Docker Yansısı?
### Birinci Jenkins düğümü için (eskiden master derdik) jenkins/jenkins yansısını kullanabilirken, ikinci yahut işçi jenkins ajanları için jenkins/slave yansısını kullabiliriz (slave de yakında kaldırılır).

### $ docker pull jenkins/jenkins
### $ docker pull jenkins/slave

## DOCKER İLE MASTER JENKINS KURULUMU - 1
![DJ1](https://user-images.githubusercontent.com/81867200/187073080-6b5fbfb5-381f-4dc9-bc47-bd0c15b0d73b.png)
### Jenkins docker görüntünüzün (image) içinde docker görüntüleri (images) oluşturmayı planlamıyorsanız, örneğimdeki --privileged bayrağını göz ardı edebilirsiniz.

### Reverse proxy olarak nginx çalıştırmak istersek, nginx dosyasının default.conf içeriği:
![DJ2](https://user-images.githubusercontent.com/81867200/187073166-11d37744-0da6-4726-a05a-342d5a28666d.png)

## Docker ile Master Jenkins Kurulumu - 2
### Docker ile ister komut satırından ister kitematic ile jenkins/jenkins isimli docker yansısını yükleyebiliriz.

### Kurulum sonrasında docker attach  container-id ile container konsol ekranında neler olduğunu görebiliriz.
  ![DJ3](https://user-images.githubusercontent.com/81867200/187073245-8569f0f7-038e-47b7-ad9c-c6ae367c3f1d.png)
### Komut satırında -d anahtarı olmada çalıştırırsak jenkins ön planda çalışır ve işletilen komutların çıktılarını yani jenkins processinin I/O çıktılarını kullandığımız konsol üstünde görebiliriz. Ama -d anahtarını kullanırsak bu bilgileri görmek için docker attach container-name komutunu çalıştırmamız gerekir.
![DJ4](https://user-images.githubusercontent.com/81867200/187073363-3acbda15-2bf8-45d2-a0ab-1966f4f1e32e.png)

### Slave Agent Node
### Sonraki Jenkins ajan düğümlerinin kurulumları

## DOCKER İLE SLAVE JENKINS KURULUMU
![DJ5](https://user-images.githubusercontent.com/81867200/187073445-e62298a9-fa73-40af-814d-0e54e82a0398.png)

## Slave Jenkins Ajanı Üstünde İş Çalıştırmak
![DJ6](https://user-images.githubusercontent.com/81867200/187073612-b5990bdb-5652-4a38-a77d-4d5df5fb247e.png)

## Jenkins Terminali Root İle Kullanmak
![DJ7](https://user-images.githubusercontent.com/81867200/187074043-921673ce-5f04-466a-b40b-dd44ac121eee.png)
### Konteyner ile terminal bağlantısı kurmak istediğimizde --user root argümanı eklersek root yetkisiyle bash’e bağlanabiliriz. root Kullanıcısıyla apt işlemlerini yapabilir ve sistem seviyesinde nodejs kurulumu sağlarız. --privileged Argümanı da root ile bağlanmamızı sağlar.
![DJ8](https://user-images.githubusercontent.com/81867200/187074093-355f5664-fbc3-48cc-bf7b-63a080e2e6cd.png)

## JENKINS'IN VARSAYILAN DİLİNİ DEĞİŞTİRMEK
![DJ9](https://user-images.githubusercontent.com/81867200/187074248-095bb3a8-78bd-475f-83c2-5baf7ea5e110.png)
### Özetle:
### - Locale eklentisini indir
### - Jenkins -> Ayarlar/Configuration Kısmında “Varsayılan Dil” yerine istediğiniz dili kısa koduyla yazın (tr, en, fr gibi)
### - İnternet gezgininizin diliyle görüntülenmemesi için altındaki “ignore browser preference..” seçilir
![DJ10](https://user-images.githubusercontent.com/81867200/187074283-8409ba9e-9902-4b78-acc7-c204600d1d26.png)

## DOCKER İLE MASTER JENKINS KURULUMU - 3
### Jenkins'in Şifresi
### Kurulum sırasında jenkins ilk giriş için bir şifre oluşturacak ve bunu konsolumuza yazacak. jenkins_home Dizinini bağladığınız kendi diskinizdeki klasörü silerseniz ve jenkins tekrar kurulurken yine aynı konsolu göreceksiniz.

### Eğer burayı kaçırırsanız docker stop "container-name" ile konteynerınızı durdurup başka bir konsol ekranından docker attach <container-name|id> ile birazdan açacağınız docker container konsolunu takip edebilirsiniz. Tekrar docker start "container-name" ile başlatırken attach olduğunu konsolda gizli anahtarı görebilirsiniz.

### Docker logs "container-name" ile de ulaşabilirsiniz.
![DJ11](https://user-images.githubusercontent.com/81867200/187074481-2399b3fc-dc66-4b63-86b5-281013a93f32.png)

![DJ12](https://user-images.githubusercontent.com/81867200/187074488-844f4ffc-d136-4c1a-80b5-74baca0ce7e2.png)

## NODEJS KURULUMU - 1
### Konteyner ile terminal bağlantısı kurmak istediğimizde --user root argümanı eklersek root yetkisiyle bash’e bağlanabiliriz. root Kullanıcısıyla apt işlemlerini yapabilir ve sistem seviyesinde nodejs kurulumu sağlarız.

![NODEJS1](https://user-images.githubusercontent.com/81867200/187074613-db7d724b-251b-4d9f-9f41-9ba27bb5bea6.png)
### NOT: Resimde gördüğünüz gibi root yetkisi olmadan :/$ ile diğer türlü :/# ile terminale düşüyoruz.

### NodeJs kurulumu için paket listesini güncelleyelim ve sistem üstünde nodejs kurulumu yapalım ve sonunda node ve npm versiyonunu görüntüleyelim:
![NODEJS2](https://user-images.githubusercontent.com/81867200/187074685-1deed9d5-b985-43c0-967f-22b6802d4d19.png)

![NODEJS3](https://user-images.githubusercontent.com/81867200/187074700-b3293845-f489-4a7f-a566-b558d84ed1b6.png)

## NODEJS KURULUMU - 2
### Jenkins “NodeJS Plugin” eklentisiyle (plugin) nodejs çalıştırabilir. Bu eklentiyle Nodejs’in farklı sürümlerini araç olarak (tools) kurabilir ve job içinde shell için PATH'e kaydeder ve npm, node uygulamalarını çalıştırabilirsiniz.
![NODEJS4](https://user-images.githubusercontent.com/81867200/187074834-896e9740-489b-4c64-a50e-4353aa074e7b.png)

## NODEJS İÇİN TOOLS ARKA PLANDA NE YAPAR?
### NodeJS eklentisi kurulduktan sonra Manage Jenkins > Global Tool Configuration içinde hangi NodeJS sürümlerini kullanmak istiyorsanız bir etiketle tanımını yaparsınız. Aşağıdaki örnekte 3 farklı sürüm için 3 etiket tanımlanmış. Hangisi job içinde kullanılırsa o sürüm /var/jenkins_home/tools içine indirilir ve shell içinden erişilebilmesi için geçici PATH içinde tanımlanır. Böylece node veya npm çağrısı yapıldığında NodeJS uygulamalarına erişilebilinir.
 ![NODEJS5](https://user-images.githubusercontent.com/81867200/187075014-31cda5c5-adbc-47fa-b60e-580a5e27f246.png)
 
![NODEJS6](https://user-images.githubusercontent.com/81867200/187075017-930d9bd0-2faf-4aca-a71f-822872f548a1.png)

## JENKINS KONTEYNER İÇİNDE NODEJS KURULUMU
### Önce terminal ekranına giriş yapalım:
![DNODEJS](https://user-images.githubusercontent.com/81867200/187075246-1355a512-7c9b-4444-ab0a-45a62492ab0e.png)

### Paket listesini güncelleyip node kurulumu yapalım ve unutmayalım setup_8.x deprecate olduğu için yerine 10 veya 12 kurmak daha iyi olacaktır:
![DNODEJS1](https://user-images.githubusercontent.com/81867200/187075253-ede0eb77-88e9-47af-8c6f-3f469b334311.png)

### Ve son çıktı:
![DNODEJS2](https://user-images.githubusercontent.com/81867200/187075266-dc379a63-fe2f-4a38-99c0-5c3ad869d7e5.png)


## SSH JENKINS SLAVE

## SANAL/FİZİKİ MAKİNA
![SF](https://user-images.githubusercontent.com/81867200/187075386-ef312cdf-8749-4470-a1d3-c7bea82067bc.png)

## DOCKER KONTEYNER
![DOCKERCONT](https://user-images.githubusercontent.com/81867200/187075722-c297bee6-8705-486c-9a39-53827687c903.png)

## DOCKER JENKINS SLAVE

## DOCKER KONTEYNER İÇİNDE JENKINS SLAVE ÇALIŞTIRMAK - 1
![DOCKERCONT1](https://user-images.githubusercontent.com/81867200/187075778-2ae8adf7-9f1f-4855-a043-7b423699cd64.png)

## DOCKER KONTEYNER İÇİNDE JENKINS SLAVE ÇALIŞTIRMAK - 2
![DOCKERCONT2](https://user-images.githubusercontent.com/81867200/187075999-805219d5-6a34-4c48-b058-5ca9be2bbf09.png)

## DOCKER RUN İLE SLAVE NODE
![DOCKERCONT3](https://user-images.githubusercontent.com/81867200/187076082-b3c02960-6ec4-48df-952f-8dd9f2663fce.png)

## GIT'I TANITALIM
![JENGIT](https://user-images.githubusercontent.com/81867200/187076189-7bad137c-5552-4496-b571-d65a0dfe38a2.png)
### whereis git diyerek konteyner içinde git’in yerini buluruz ve node üstünde Tool Locations içine git’in dosya yolunu gireriz, hepsi bu.
![JENGIT1](https://user-images.githubusercontent.com/81867200/187076233-ee619a35-b607-4952-b5dd-80967c94e856.png)
## DİSKİMİZİ BAĞLAYALIM
![DISK](https://user-images.githubusercontent.com/81867200/187076350-8fc64515-ea71-4910-9f09-0cca24da704a.png)
## WHEREIS NPM
![WHEREIS](https://user-images.githubusercontent.com/81867200/187076473-4105a232-acd2-4fee-af5e-b98254ab40ad.png)

## -JENKINS AYARLARI-

## JENKINS İLE ADMIN KULLANICISI OLUŞTURMAK
### İlk ekrana girdiğiniz gizli kelimeden sonra önerilen pluginleri kurar ve ardından kullanıcı tanımlarsınız. Ve artık jenkins hizmetinize sizin tayin ettiğiniz (örn. 8080) porttan başlatılır.


## GLOBAL TOOL CONFIGURATION

### JDK
### Linux üstünde $ which javac ile JDK dizininin yolunu öğrenebilir ve Global Tool tanımlayabiliriz.
![JDK](https://user-images.githubusercontent.com/81867200/187076923-41f93929-16f9-43e6-81ca-46b608941aac.png)

### GIT
### Linux üstünde $ which git ile GİT dizininin yolunu öğrenebilir ve Global Tool Configuration içinde tanımlayabiliriz.
![GIT](https://user-images.githubusercontent.com/81867200/187076960-de9d2794-c096-4c51-9c09-cb4ac39bdb7a.png)

### NODEJS
### Linux üstünde $ which node ile Node dizininin yolunu öğrenebilir ve Global Tool Configuration içinde tanımlayabiliriz.
![NODEJSSSS](https://user-images.githubusercontent.com/81867200/187077004-7936d08c-120e-4894-9fab-d878d7bc74c7.png)

## GITHUB AUTHENTICATION
### Bilgisayarınızda lokalde çalışan bir jenkins olsun. Kodlarınızı barındırdığınız git adresini projenizin Source Code Management sekmesine girdiniz. Jenkins arka tarafta HEAD metoduyla ilgili adrese bir istek yapacak. Eğer kullanıcı bilgileriniz geçerli değilse aşağıdaki hatayı verecek.
 ![GITAUT](https://user-images.githubusercontent.com/81867200/187077102-18817392-3fe0-4f31-b007-94301896c739.png)
 
 ### Bu durumda artık github için bir kullanıcı doğrulama yöntemi seçerek devam etmeliyiz.
### - Windows Kimlik Yöneticisinde kullanıcı bilgilerinin depolanması
### - Username ve Password ikilisi olan credential
### - Github Token kullanmak

### KULLANICI BİLGİLERİ YÖNETİCİSİ
### Konsol üstünden github reposunun clone ile çekilmesi sağlandığında Windows Kimlik Bilgileri Yöneticisi kullanıcı bilgilerini depolayacak ve eğer Credentials açılır kutusundan bir seçim yapılmamışsa, Jenkins her github için arka planda yapacağı istekte sistemde kayıtlı olan bu bilgileri kullanacak.
![KULLANICI](https://user-images.githubusercontent.com/81867200/187077652-af41a937-a36c-4768-8e0d-58a5095e12b2.png)

![KULLANICI1](https://user-images.githubusercontent.com/81867200/187077669-11d8d88b-de81-4684-a42f-138a2340478a.png)
### Github için yapılacak istek başarısızsa aşağıdaki gibi, başarılıysa boş gövdeli cevap döner
![KULLANICI2](https://user-images.githubusercontent.com/81867200/187077684-436b3cad-fc62-4707-8651-da6a15a6b875.png)

### GİTHUB KULLANICI ADI VE ŞİFRESİ
### Sistemde kayıtlı kullanıcı bilgileri yerine belirlediğimiz credential ile bağlanmak istediğimiz durumdur. Github reposunu yazdığımız yerde Add düğmesiyle (veya Jenkins Credential menüsünden) Username with Password tipinde bir tanımlama yaparız. Kullanıcı adı ve şifresiyle bir credential oluşturup projenin Source Code Management sekmesinde Credentials açılır kutusunda seçili hale getirebiliriz.
![KULLANICI3](https://user-images.githubusercontent.com/81867200/187077846-72d641d2-4c61-49df-ba18-ceb37f906450.png)


### GIT TOKEN İLE WEBHOOK 
### (1) Github üstünden bir Token yaratıp Jenkins içinde yeni bir Credential olarak tanımlarız. (2) Bu kez Jenkins’in tüm projeleri tarafından kullanılabilecek şekilde token bilgisini ayarlayacağız Manage Jenkins / Configure System / Github içinde az önce oluşturduğumuz TOKEN seçilerek Github server ile webhook için kullanılacak token ayarlanır. 
![KULLANICI4](https://user-images.githubusercontent.com/81867200/187077940-958515ec-6c42-4127-b4a5-ae4dba569ec1.png)

### Oluşturduğumuz token’ın testi için curl -u username:token https://api.github.com/user komutunu konsoldan çalıştırabiliriz.

### GITHUB AYARI
### Github üstündeki bir repoya bağlanmak istersek github sunucu ayarlarına hangi token ile bağlanacağımızı söylememiz gerekiyor. Sonrasında projemizin General ayarlarında bu projenin bir Github projesi olduğunu seçmeli ve Source Code Management içinde git seçeneğini işaretleyip hangi adresten veri çekeceksek projenin bağlı olduğu github kaynak kodunun adresini ve hangi branch üstünde koşacağımızı belirtmeliyiz.
![KULLANICI5](https://user-images.githubusercontent.com/81867200/187078097-459db0ed-e8c4-4ee7-af3e-6cf8046698ee.png)

### Build ettiğimizde kodun indiğini görürüz.

### GITHUB PUBLIC REPO AYARI
### Projenin (burada ng_form adında freestyle tipinde), Configure sekmesinden Source Code Management kısmında Git seçilip, clone yapmak için kullandığımız adresini yapıştıralım. Projeyi build ettiğimizde kodlar çekilerek workspace içine dosyalarımız konulacak.
![KULLANICI6](https://user-images.githubusercontent.com/81867200/187078218-a5bffad1-cc19-4881-ba39-135d2dd0b837.png)

### GITHUB PRIVATE REPO AYARI
### Önce kayıtlı şifreyi silelim ki; github üstünde private repomuza giderken şifre sorulur hale gelsin ve yerelde çalışan jenkins için de şifre istensin. Böylece Github token yaratma yoluna gidelim. git config --global credential.helper store ile kullanıcı adı ve şifresini bilgisayara depolayacağız demiş oluruz. Kullanıcı adı ve şifresini ilk girdiğimiz anda önce %USERPROFILE\.git-credentials dosyasına https://gitKullaniciAdi:gitSifresi@github.com bilgisi yazılır ardından Windows Kimlik Bilgileri Yöneticisi bu bilgileri ön bellekler.

### Eğer Windows Kimlik Bilgileri Yöneticisi üstünden siler tekrar git clone ile yerele kodları çekmek istediğimizde kullanıcı bilgileri WinKimlikBilgYöneticisi üstünden okunmak istenir, bulunamayınca .git-credentials dosyasından veriler okunur ve WinKimlikBilgYöneticisi üstüne tekrar yazılır.Bir sonraki clone işleminde WinKimlikBilgYöneticisi kullanıcı bilgilerini servis eder ve .git-credentials dosyasına gerek kalmadan kullanıcı girişi sağlanmış olur.
![KULLANICI7](https://user-images.githubusercontent.com/81867200/187078377-2f2024f7-e65d-450f-b203-3176ba9729ee.png)


## DECLARATIVE PIPELINE VE GİT AKSİYONLARI
![DECPIP](https://user-images.githubusercontent.com/81867200/187078478-e852b88c-b25e-4931-bb82-8d995308f614.png)

![DECPIP1](https://user-images.githubusercontent.com/81867200/187078500-8e5bfffa-8e60-440c-b8c3-17792c54da82.png)

![DECPIP2](https://user-images.githubusercontent.com/81867200/187078549-29a891dd-86ae-4eba-b229-0945ad39b702.png)


## PROJELERİ SIRALI TETİKLEMEK
### Sıralı Olarak Proejeleri Build Etmek
![SIRALI](https://user-images.githubusercontent.com/81867200/187078640-57f0ac38-cb19-4f83-8a75-88f0651296ec.png)

### Delivery Pipeline ile Görselleştirme
![SIRALI1](https://user-images.githubusercontent.com/81867200/187078908-c5fdd6ba-ef60-4b71-97c4-a71c4a2406d7.png)


## AGENT/NODE TANIMLAMA (SLAVE JENKINS)
![JMS](https://user-images.githubusercontent.com/81867200/187078990-af94b652-d3d0-4d6b-8210-5dc7b88a9509.png)

### GEREKENLER
### - VirtualBox veya VMware Player kurula
### - En hafifinden linux kurulu bir disk indirilip sanal makine (virtual machine) çalıştırılabilir.
### - Sanal makine içine java kurulabilir.
### - openssh-server linux içine kurulup dışarıdan erişilebilir hale getirilebilir.
### - jenkins içinde yeni vm’in bilgileriyle bir node/agent oluşturulabilir.

### SANAL LINUX KURULUMU
### https://www.osboxes.org/linux-lite/ Adresinden linux kurulu disk indirilerek VirtualBox üstüne eklenir.Hemen “passwd” komutuyla osboxes.org kullanıcısı, “sudo passwd root” ile root şifresi değiştirilir.
![LINUX](https://user-images.githubusercontent.com/81867200/187079243-9c40d10c-7a6c-4b7a-b43e-a976290e579e.png)

![LINUX1](https://user-images.githubusercontent.com/81867200/187079341-9451a833-7305-42eb-9688-aeddd25c6d38.png)

### LINUX AĞ AYARLARI
### mtui kullanıcı arayüzü, dhclient veya ifconfig ile ağ işlemlerini yapabiliriz.

### Ağ Ayarlarını Görüntülemek
### DHCP Sunucusuna “merhaba” gönderip iletişimi görelim
#### $ dhclient -v
#### $ ifconfig -a

### Ağ Ayarlarını Tazelemek
#### $ sudo dhclient -v -r
#### $ ifconfig ağ_adı down
#### $ ifdown ağ_adı
#### $ ifconfig ağ_adı up
#### $ ifup ağ_adı

### Ağ Servisini Yeniden Başlatmak
#### $ /etc/init.d/nscd restart



### JAVA YÜKLEMEK & KALDIRMAK
![JAVAKUR](https://user-images.githubusercontent.com/81867200/187079584-5b47bdd9-62ec-474c-b86c-6b97e657cdfd.png)

### YENİ KULLANICI TANIMLAMAK 
### Master olan Jenkins projelerin tanımlandığı, ayarlarının yapılıp yapılandırmak için tetiklendiği ve çıktıların gözlemlendiği ilk kurulumumuzdur.
 
### Diğer sunucular (node/agent’lar) ise agent.jar isimli dosyanın sürekli çalışıp master jenkins tarafından gelen işlerin yapıldığı düğümlerdir. Bu düğümlere job’ların yüklenmesi için bir kullanıcı tanımlanır ve master jenkins, sshmarifetiyle bağlanarak ilgili agent.jar dosyasını yükler ve çalıştırır. agent.jar Dosyası tabiatı gereği Java kurulumu da gerektirdiği için önceden yüklenmiş olması gerekir.
 
### Kullanıcı Silmek
### Silinmek istenen kullanıcı aktif bir processleri killall ile durdurulur veya zorla (force) silmek istediğimizi -f argümanı ile veririz.
#### $ killall -u kullanıcı_adı
#### $ userdel -f --remove-home kullanıcı_adı

### Yeni Kullanıcı Oluşturmak
#### $ useradd -m cemkins

### Yeni Kullanıcıya Şifre Atamak
### cemkins kullanıcısının yeni şifresini iki kez girilir ve yeni kullanıcıyla sisteme giriş yapılar.
#### $ passwd cemkins


### Yeni Kullanıcı Profilinde Jenkinse Özel Dizin Oluşturmak
### Yeni kullanıcının profili /home/kullanıcıAdı dizininde oluşacaktır. Jenkins bu klasörün altına remote.jar dosyası ve remote dizini oluşturacağı için derli toplu olsun diye biz jenkinsKokDizini diye bir klasör oluşturalım.
#### $ mkdir jenkinsKokDizini


### SSH KURULUMU
### ssh Secure Shell anlamıa gelir ve telnetin şifrelenmiş halidir. sshd ise servis (daemon) halinde çalışan ssh sunucusudur. shd_config içinde yapılan değişikliklerin etkili olması için servisin tekrar başlatılması gerekir.

### ssh Server Kurulur
#### $ sudo apt-get install openssh-server

### ssh Servisi Faal Edilir
#### $ sudo systemctl enable ssh

### ssh Servisi Başlatılır
#### $ sudo systemctl start ssh

### Servisin Durumu Kontrol Edilir
#### $ sudo systemctl status ssh

### ssh Bağlantısı Test Edilir
#### $ ssh root@makina-adı|ip



### Dışarıdan Bağlanmak İçin Ayar Yapılandırılır
### # ile başlayan satırlar yorum satırı demektir. Bazı komutların yorum satırı olmadığı belirtmemiz gerekecek:
#### $ vi /etc/ssh/sshd_config

#### #PermitRootLogin prohibit-password
#### satırı aşağıdaki hale getirilir
#### PermitRootLogin yes

#### #PasswordAuthentication yes
#### yorum satırı olmaktan çıkarılır
#### PasswordAuthentication yes

#### Eğer ssh key ile giriş yapılabilsin istiyorsak aşağıdaki satırlar yorum satırı olmaktan çıkarılır
#### #PubkeyAuthentication yes
#### #AuthorizedKeysFile .ssh/authorized_keys


### SSH SORUN GİDERME
#### SSH bağlantısı sırasında “Host key verification failed.*” hatası alınırsa, bağlantı kurulacak makina için “bilinen hostlar” dosyasında güncelleme yapmak için $ ssh-keygen -R 192.168.99.102 komutu çalıştırılır. IP adresi, bağlantı kurmak istediğiniz uzak makinanın adresi veya ismidir. 
![SSH](https://user-images.githubusercontent.com/81867200/187081125-d11efc35-befd-4da6-a76c-7ec524491d5e.png)
#### known_hosts dosyası .ssh dizini altındadır.
#### $ ssh-keygen -R <ip | host_adı>
#### Komutuyla her uzak bağlantı için bir key üreterek
#### güvenilir bağlantılar listesine ekler.


#### SSH servisini otomatik üretiyorduk ve diyelimki ayarlar dosyası çalışmaz hale geldi ve aşağıdaki hatayı almaya başladık:
#### Unit sshd.service could not be found

#### Tüm openssh-server’ı kaldırmak yerine konfigurasyon dosyalarını kaldırıp tekrar kurulum yapmak yeterli olacaktır.
#### $ apt-get purge openssh-server
#### $ apt-get install openssh-server

#### Elbette tüm ssh server’ın kaldırılıp tekrar kurulmasında da sakınca yok
#### $ apt-get remove --purge openssh-server
#### $ apt-get install openssh-server
#### $ service ssh restart
#### $ service ssh status


### Docker Jenkins İçin Plug-In Kurulumunda Hata
#### Docker versiyonu jenkins/jenkins yansısını kullanıyor ve plugin güncellemesi yapamadığını görüyorsanız jenkinsin pluginleri indirebileceği adresi ortam değişkeni olarak jenkins kabınıza vermeniz gerekiyor.

#### Bunu 3 farklı adresi verip deneyebilirsiniz:
#### 1. http://ftp-nyc.osuosl.org/pub/jenkins
#### 2. http://mirrors.jenkins-ci.org
#### 3. https://updates.jenkins.io/download/plugins
#### Kitematik ile veya docker kabınızı çalıştırırken yapabilirsiniz
#### docker run --name jenkinscim
#### .... #### -e JENKINS_UC_DOWNLOAD
#### 'http://ftp-nyc.osuosl.org/pub/jenkins'
#### jenkins/jenkins

![SSH1](https://user-images.githubusercontent.com/81867200/187081373-59aae5a8-7db5-4990-b1f1-cf32c47d4d8b.png)

### AGENT LAUNCH SORUN GİDERME
![SSH2](https://user-images.githubusercontent.com/81867200/187081468-a41e55fd-1148-4166-a96c-b302447307a3.png)


## AGENT TANIMLAMA
![AGENT](https://user-images.githubusercontent.com/81867200/187081554-aa963456-3e16-48e0-9468-e46f974641d9.png)

![AGENT2](https://user-images.githubusercontent.com/81867200/187083637-e28c1321-f01a-475f-bac3-ee08d709ef64.png)


## PRIVATE DOCKER REGISTRY
### Private Registry Kurulumu
#### $ docker run -d -p 5000:5000 --restart always --name registry registry:2

![DOCKERREGISTRY](https://user-images.githubusercontent.com/81867200/187083858-672657bb-cd7e-49b9-94c8-1a85e14812ef.png)


## OPENSSH - SERVER KURULUMU

### OPENSSH-SERVER YÜKLEMEK & KALDIRMAK
#### Sadece openssh-server’ı kaldırmak istiyorsak:
#### $ sudo apt-get remove openssh*
#### openssh-server’ı tüm bağımlılıklarıyla kaldırmak istiyorsak:
#### $ sudo apt-get remove --auto-remove openssh*
#### openssh-server ve ayar dosyalarını kaldırmak istiyorsak:
#### $ sudo apt-get purge openssh*
#### openssh-server, bağımlılıkları ve ayar dosyalarınıkaldırmak istiyorsak:
#### $ sudo apt-get purge --auto-remove openssh*
#### $ apt-get update
#### $ apt-get install openssh-server

### Kurulum Detayları:
![OPENSSH](https://user-images.githubusercontent.com/81867200/187084074-a45facb7-56dd-4711-b918-36d5a878d7ee.png)


## GIT'E SSH ANAHTARIYLA BAĞLANMAK
### SSH ANAHTARLARI OLUŞTURMAK VE KULLANIMA AÇMAK
![GITSSH](https://user-images.githubusercontent.com/81867200/187084165-d539183e-9a0b-4fa3-865a-4bfdf2241e0e.png)

### GITHUB & JENKINS SSH ANAHTAR AYARLARI
#### Jenkins üstünde Global Credential oluşturuyoruz.
####  - SSH Username with private key seçeneğiyle
####  - Username ile bağlanacağımız sistemin kullanıcı adı,
####  - ID bilgisini biz yazarsak anlamlı ve eşsiz bir tanımlama, boş bırakırsak UUID değer atanır,
####  - Private Key kısmına bir önceki sayfada hazırladığımız SSH anahtarının private kısmını yapıştırırız. Böylece Jenkins privte anahtar içeren dosyayı aramak, dosya         yoluna bağlı kalmak zorunda olmayacaktır.
#### -  Passphrase ise ssh-keygen ile SSH anahtarını oluştururken bize gizli bir parola girmemizi istediğinde yazdığımız metin.

#### Github üstünden kişisel ayarlardan SSH and GPG keys sekmesinde ise Key kısmına SSH anahtarımızın public anahtarının içeriğini yapıştırıyoruz ve tanımlama için title alanına ayrıştırılabilir bir metin girilir.

![GITSSH1](https://user-images.githubusercontent.com/81867200/187084303-bc4d2fb3-a92c-4352-ae36-43a3586fa9e9.png)

## GIT'E KULLANICI ADI & PARALOYLA BAĞLANMAK
### FREESTYLE PROJEDE HTTPS & SSH GIT REPO BAĞLANTISI
#### Jenkins üstünde oluşturduğumuz “SSH Username with private key” türündeki credential’ı kullanabileceğimiz GİT SCM Reposuna SSH ile bağlantı kurmamız gerekiyor.
![HTTPSSSH](https://user-images.githubusercontent.com/81867200/187084476-3b7f68cc-d516-4327-ae15-8d85434cf794.png)
![HTTPSSSH1](https://user-images.githubusercontent.com/81867200/187084527-66228896-8b5c-490c-ba94-369146c28ecb.png)
![HTTPSSSH2](https://user-images.githubusercontent.com/81867200/187084566-aac66186-2f10-464e-9037-7ee85e54b668.png)

### Pipeline Projede Https & SSH Git Repo Bağlantısı
#### Jenkins üstünde oluşturduğumuz “SSH Username with private key” türündeki credential’ı kullanabileceğimiz GİT SCM Reposuna SSH ile bağlantı kurmamız gerekiyor.
![PIPHTTPSSSH](https://user-images.githubusercontent.com/81867200/187084727-e3e16ffb-4c63-422e-a7ee-86c0b84d8a2b.png)

## BITBUCKET PROJESIYLE JENKINS JOB TETIKLEMEK
http://www.adobe.com.by/pdf/meetup-12/Meetup_12_Mytroshin.pdf
http://www.adobe.com.by/en/#archive1

## LINUX MINT'E JENKINS KURULUMU
![LINUXMINT](https://user-images.githubusercontent.com/81867200/187084858-df261ce8-0315-4dd4-9a3d-652f4e0a1680.png)

## GROOVY İLE SCRIP YAZMAK
### VERİ TİPLERİ
![GRROOVY](https://user-images.githubusercontent.com/81867200/187084935-a228649a-0e93-4da9-bb61-e8a97ea73414.png)

### BAŞLIKLAR
https://www.leveluplunch.com/groovy/examples/#groovy-net
https://www.leveluplunch.com/groovy/examples/#groovy-xml
https://www.leveluplunch.com/groovy/examples/#groovy-string
https://www.leveluplunch.com/groovy/examples/#groovy-number
https://www.leveluplunch.com/groovy/examples/#groovy-html
https://www.leveluplunch.com/groovy/examples/#groovy-date
https://www.leveluplunch.com/groovy/examples/#groovy-collections

### STRING
![STRING](https://user-images.githubusercontent.com/81867200/187085733-92f82ce1-ee6a-437d-b107-b70f55a64a45.png)

![STRING1](https://user-images.githubusercontent.com/81867200/187085821-74b2b7cc-b36c-4d50-8eb1-41336ad1b309.png)

![STRING2](https://user-images.githubusercontent.com/81867200/187085936-1fafacbd-9fea-4f26-ad7f-d4457ebf2be9.png)

### STRING MANİPÜLASYONLARI
![STRING3](https://user-images.githubusercontent.com/81867200/187085994-d3aa923b-f641-4c34-a630-05bc7b40f703.png)

### ARRAY FONKSİYONLARI
![STRING4](https://user-images.githubusercontent.com/81867200/187086045-f8d7a34d-2f87-4e83-83a5-cd4e31f99795.png)

### LIST
![STRING5](https://user-images.githubusercontent.com/81867200/187086109-a93b9c5a-f89d-43b7-847d-133ebcd67836.png)

### SET
![STRING6](https://user-images.githubusercontent.com/81867200/187086158-715e0289-7454-4a4a-b7f0-45f228f0f378.png)

### MAP
![STRING7](https://user-images.githubusercontent.com/81867200/187086208-f92df70b-7980-4402-bddc-289f8fc60337.png)

### RANGE
![STRING8](https://user-images.githubusercontent.com/81867200/187086252-dc6b91ae-cfa3-47d3-8065-7f050cf62496.png)

### LOOP
![STRING9](https://user-images.githubusercontent.com/81867200/187086298-57e04807-b01d-4a78-bb43-05d2b0423ae2.png)

### DÜZENLİ İFAEDELER REGEXP
![STRING10](https://user-images.githubusercontent.com/81867200/187086363-cdecdbae-f11c-4d20-bbee-893012064f0d.png)


## JENKINS SH

### SH
![SH](https://user-images.githubusercontent.com/81867200/187086674-335936a1-6f99-48c7-a081-ca60eeff347b.png)

## JENKINS DEĞİŞKEN TANIMLAMA
![SH1](https://user-images.githubusercontent.com/81867200/187086701-af6cb61b-e388-4cc8-b086-e6a25bf4b96b.png)

![SH2](https://user-images.githubusercontent.com/81867200/187086738-dbe54884-053b-4eca-8c6e-e758b92feb59.png)

![SH3](https://user-images.githubusercontent.com/81867200/187086763-a2edbebe-d04e-4fd9-9065-4112628c22df.png)

![SH4](https://user-images.githubusercontent.com/81867200/187086794-65245fe3-af76-44ac-afa0-72bb21910440.png)

## JENKINS ENVIRONMENT VARIABLES

### ENVIRONMENT VARIABLE
#### İşletim sisteminin ortam değişkenlerine windows için
#### %DeğişkenAdı% , linux için $DeğişkenAdı ile erişiyoruz.
#### Ortam değişkenleri tüm hat içerisinden erişilebilen yerel ve global değişkenlerdir.
#### İşletim sistemi seviyesinde tanımlı env. vars’a erişmek için windows os üstünde koşan bir batch için $env.PATH,

### Environment Tanımı & Refactor Etmek
![ENV](https://user-images.githubusercontent.com/81867200/187086936-779eccb6-9e65-4b4c-8ad6-cc65e070c542.png)

### ENV VAR SIRALAMASI
![ENV1](https://user-images.githubusercontent.com/81867200/187086991-5d52b819-0fca-4ab8-9b09-547cbbef8eb6.png)

### Global ve Local Değişkenler ve Local Ortam Değişkenleri
![ENV2](https://user-images.githubusercontent.com/81867200/187087053-c9789e89-0e2c-4de9-8575-208283c6a951.png)

![ENV3](https://user-images.githubusercontent.com/81867200/187087097-ca3ef8ea-c39c-45a1-a6eb-7b5b416ba163.png)

![ENV4](https://user-images.githubusercontent.com/81867200/187087127-457b1dfe-1b76-4027-85d1-042ad810d6b4.png)

### GLOBALDE TANIMLI ÖZEL ENV. VAR.
#### Jobların erişmesini istediğiniz temel değerleri global env. vars. içinde tanımlayabilirsiniz. Örneğin sprint koşunuzun numarası, üretilecek projenin versiyon numarası vs. için değerleri globalde bir kere tanımlayıp tüm projeler için globaldeki değişkenler gibi (örneğin BUILD_NUMBER’a WORKSPACE’e erişir gibi) erişebilirsiniz.

![ENV5](https://user-images.githubusercontent.com/81867200/187087198-1355e6c9-9463-42ef-8a5a-d9db909f92a2.png)

## JENKINS DECLARATIVE PIPELINE ÖRNEĞİ

### DECLARATIVE JENKINS
![PIPDEEC](https://user-images.githubusercontent.com/81867200/187087287-f2f6b216-3ceb-49f4-82db-acad77c92754.png)

### DECLARATIVE PIPELINE'I ANLAMAK
#### DSL ile Jenkins Script arasındaki fark; daha kolay kodlama yapabileceğimiz Domain Specific Language olarak tanımlayabiliriz.
![PIPDEEC1](https://user-images.githubusercontent.com/81867200/187087352-4575691d-a786-4dcd-984f-6ffc7d175487.png)

### DECLARATIVE JENKINS PIPIELINE
![PIPDEEC2](https://user-images.githubusercontent.com/81867200/187087396-dc8c2b73-8538-43d2-bbe3-6131d86c0074.png)

![PIPDEEC3](https://user-images.githubusercontent.com/81867200/187087436-29b1dc9d-9230-4d17-83c9-a35eff718683.png)

## HATA YÖNETİMİ (ERROR)
### ERROR
#### Kendimiz hata uydurmak istersek error(mesajımız) fonksiyonunu kullanırız.
![ERROR](https://user-images.githubusercontent.com/81867200/187087487-63094f28-fd4f-415a-8d8a-90de9a7feb25.png)

### TRY - CATCH - FINALLY
![TRYCATCH](https://user-images.githubusercontent.com/81867200/187087524-ed2027d8-824e-44e9-a344-ec32dfdbee9d.png)

### RETRY(N)
![RETRY](https://user-images.githubusercontent.com/81867200/187087557-952f8e5d-8584-4360-8671-6cc4bd5757f3.png)

### CATCHERROR
#### Birden fazla projenin kullandığı ortak kütüphanede mi değişiklik yaparak hepsini etkilemek istersiniz yoksa tek tek her projeye gidip değişiklik mi yapmak istersiniz?

## SHARED LIBRARY

### NEDEN SHARED LIBRARY
#### Paylaşılan kitaplık deposu klasör yapısına sahiptir.
![SHARED](https://user-images.githubusercontent.com/81867200/187087619-293e9bf3-850f-41e9-a626-0718b473a344.png)






































 





 












 



 

































