# Gemini

Google DeepMind tarafından geliştirilmiş bir üretken yapay zeka modeli ailesidir.
Çok modlu kullanım senaryoları için tasarlanmıştır.

#Gemini'den Fonksiyon Çağırma (Function Calling)

Geliştiricilerin kodlarında bir fonksiyonun tanımını oluşturmasına ve bu tanımı bir istekte bir dil modeline iletmesine olanak tanır.
Modelin yanıtı, açıklamaya uyan bir fonksiyonun adını ve istenen argümanları içerir.

# Neden Fonksiyon Çağırma?

Birine bir form veya yapılandırma kılavuzu vermeden önemli bilgileri yazmasını istemek gibi, yapılandırılmış verileri doğrudan bir üretken metin modelinden almak da zor olabilir.
Fonksiyon çağırma, belirli parametreler ve veri türlerine sahip net işlevler tanımlayarak bu sorunu çözer.
Bu fonksiyon bildirimleri, Gemini modelini çıktısını öngörülebilir ve kullanılabilir bir şekilde yapılandırması için yönlendirir.
Artık önemli bilgiler için metin yanıtlarını ayrıştırmaya gerek kalmaz.


<img width="1346" alt="Screenshot 2024-09-22 at 15 30 28" src="https://github.com/user-attachments/assets/bbf2ebf7-471f-47c5-a88a-c3d6e06e4b38">


https://www.googlecloudcommunity.com/gc/Community-Blogs/Function-calling-A-native-framework-to-connect-Gemini-to/ba-p/713612

    # Açıklama:

Kullanıcı İsteği: Kullanıcı, Gemini modeline bir istek gönderir (örneğin, "Bana İstanbul'daki hava durumunu söyle").

Fonksiyon Çağrısı Oluşturma: Gemini, isteği analiz eder ve uygun bir fonksiyon çağrısı oluşturur. Bu çağrı, kullanıcının isteğini yerine getirmek için hangi işlevin çağrılacağını ve hangi parametrelerin kullanılacağını belirtir.

API Çağrısı: Oluşturulan fonksiyon çağrısı, harici bir API'ye (örneğin, bir hava durumu API'si) gönderilir.

API Yanıtı: API, fonksiyon çağrısına yanıt olarak istenen verileri (örneğin, İstanbul'daki hava durumu bilgisi) döndürür.

Yanıt İşleme: Gemini, API'den alınan yanıtı işler ve kullanıcıya anlamlı bir yanıt oluşturur.

Kullanıcıya Yanıt: Gemini, oluşturulan yanıtı kullanıcıya sunar (örneğin, "İstanbul'da şu anda hava durumu güneşli ve sıcaklık 25°C").

Bu grafik, Gemini'nin fonksiyon çağırma özelliğini kullanarak nasıl harici API'lerle etkileşim kurduğunu ve kullanıcı isteklerini nasıl yerine getirdiğini göstermektedir.

# Fonksiyon Çağırmanın Avantajları

Gemini'ye uygulamalarınızın dilini konuşmayı öğretmek gibidir.
Veritabanından bilgi almak için search_db işlevi tanımlayabilirsiniz.
Bir hava durumu API'si ile entegre olmak için konum girişini alan bir get_weather fonksiyonu oluşturabilirsiniz.
Fonksiyon çağırma, insan dili ile harici sistemlerle etkileşim kurmak için gereken yapılandırılmış veriler arasındaki boşluğu doldurur.

# Hedefler


Python için Vertex AI SDK'sını yükleme
Gemini 1.5 Flash (gemini-1.5-flash) modeliyle etkileşim kurmak için Vertex AI Gemini API'sini kullanma

# Özetle:

Gemini'de fonksiyon çağırmanın nasıl kullanılacağını ve üretken yapay zeka uygulamalarının yeteneklerini nasıl genişletebileceğini göstermektedir.

#AISprint

“Google Cloud credits are provided for this project.”







