# hazirlik-sinavi-chatbot
FL3 kurundaki öğrenciler için hazırlık sınavı hakkında bilgi veren küçük RAG tabanlı chatbot
# 🧠 Hazırlık Sınavı Chatbot (FL3 Kuru)

Bu proje, Hacettepe Üniversitesi **Hazırlık Sınavı** hakkında bilgi verebilen küçük bir chatbot uygulamasıdır.  
Chatbot, **FL3 kurundaki öğrenciler** için hazırlanmıştır ve sınav tarihi, süresi, yeri, içerik, soru türleri ve çalışma kaynakları hakkında bilgi sağlar.  

---

## 🎯 Proje Amacı
Bu projenin amacı, öğrencilerin sınav öncesi ihtiyaç duyduğu bilgilere hızlı ve doğru şekilde ulaşmasını sağlamaktır.  
Sistem, **metin verileri** üzerinden arama (retrieval) yaparak kullanıcı sorularına uygun yanıtlar döndürür.

---

## 📚 Veri Seti
Veri seti, Hacettepe Üniversitesi Yabancı Diller Yüksekokulu tarafından düzenlenen FL3 kur sınavına ait bilgilerden oluşturulmuştur.  
Ek olarak aşağıdaki bilgiler eklenmiştir:

- 📅 **Sınav tarihi ve saati:** 23.10.2025 – 10:00–12:40  
- 📍 **Sınav yeri:** Hacettepe Üniversitesi Beytepe Kampüsü YDYO binası 
- 🧠 **Bölümler:** Writing, Listening, Reading  
- 📝 **Soru türleri:** Çoktan seçmeli, boşluk doldurma, eşleştirme  
- 🎯 **Kapsam:** FL3 kurundaki öğrenciler  
- 📚 **Hazırlık kaynakları:** Language Hub kitabı ve Writer 2 kitabındaki örnek sorular  

Veriler doğrudan kullanıcı tarafından girilmiş ve küçük bir **knowledge base (bilgi tabanı)** oluşturulmuştur.

---

## ⚙️ Kullanılan Teknolojiler
- **Python**
- **Google Colab**
- **Sentence Transformers** – metin embedding modeli (`all-MiniLM-L6-v2`)
- **ChromaDB** – vektör veritabanı (retrieval için)
- **Gradio** – web arayüzü oluşturma

---
- ÇÖZÜM MİMARİSİ


```markdown
Bu mimaride sistem şu şekilde çalışmaktadır:

1. **Kullanıcı Sorgusu (User Query):**  
   Kullanıcı Gradio arayüzüne sınavla ilgili bir soru yazar.

2. **Embedding Aşaması:**  
   `sentence-transformers/all-MiniLM-L6-v2` modeli, hem veri setindeki tüm dokümanları hem de kullanıcının sorusunu vektör (sayısal temsil) haline getirir.

3. **Retrieval (Bilgi Arama):**  
   ChromaDB, sorunun embedding vektörünü veri tabanındaki dokümanlarla karşılaştırır ve en benzer 3–5 sonucu döndürür.

4. **Cevap Üretimi (Rule-based):**  
   Sistemde OpenAI kullanılmadığı için, en yakın dokümandan alınan metin doğrudan cevap olarak gösterilir.

5. **Web Arayüzü (Gradio):**  
   Kullanıcı dostu bir arayüzde, soru kutusuna yazılan her şey anında işlenir ve sonuç ekranda gösterilir.

---

## 📘 Proje Akışı

1. Gerekli kütüphaneler yüklenir (`sentence-transformers`, `chromadb`, `gradio`).
2. PDF veya manuel girilen bilgilerden küçük bir veri seti oluşturulur.
3. Her doküman embedding haline getirilip Chroma veritabanına kaydedilir.
4. Kullanıcı bir soru sorar → sistem en benzer bilgiyi bulur → cevap üretir.
5. Gradio arayüzü üzerinden chatbot olarak kullanılır.

---

## 🚀 Projenin Kapsamı

Bu proje, Hacettepe Üniversitesi **FL3 kurundaki** öğrenciler için hazırlanmış sınav hakkında bilgi sunar:

- 📅 Tarih ve saat  
- 📍 Sınav yeri (Hacettepe Beytepe YDYO)  
- 🧠 Bölümler (Writing, Listening, Reading)  
- 📝 Soru tipleri (çoktan seçmeli, boşluk doldurma, eşleştirme)  
- 📚 Kaynaklar (Language Hub & Writer 2)  

---

## 🧭 Sonuç

Bu proje, küçük bir RAG mimarisi ile bilgi arama ve yanıt üretme prensibini gösterir.  
Ek veri eklenerek daha gelişmiş bir bilgi tabanı oluşturulabilir.  
Basit, hızlı ve öğretici bir chatbot örneğidir.

---
## 🌐 Web Arayüzü Linki
Chatbot’a buradan ulaşabilirsiniz:  
👉 https://ccd9184a6caf2ed4f2.gradio.live/
https://92e113b5144de88697.gradio.live



## 🧩 Çözüm Mimarisi

