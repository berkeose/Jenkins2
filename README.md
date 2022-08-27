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

41!

























