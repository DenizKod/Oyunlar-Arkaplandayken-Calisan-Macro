# BU MACRO NE İŞE YARIYOR?

<p>- Bu Macro sizin önceden seçtiğiniz bir oyunu yada uygulamanızı arka plana atsanız bile sadece oyuna yada uygulamaya etki edecek şekilde tuş komutları gönderir. böylelikle siz ön planda eşzamanlı olarak websitelerinde surf yapabilir yada işleriniz halledebilirsiniz.


# BAŞLAYALIM

- Not Defterini Macro olarak kullanmak için tıpkı winrar gibi basit bir eklenti kurmanız gerek
- Google git > AutoHotKey > AutoHotKey 2.0 İndir

![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/1f59df65-1711-46ee-9839-70a60de5b7d0)

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/a8120c26-6290-4c18-a8ba-77bc2fcefdab)

![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/cec10703-9864-43d0-9b38-0ca4dc5a58af)

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/7e3297c2-1b29-4903-bfad-13e746833512)

![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/98d9c31d-f1cb-4979-b6d3-483bf589c94f)

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/54f0b575-8eda-4441-9886-d201f6321d5f)

![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/b18ab5a4-081c-48ce-8df6-ef5da03d94b4)

# AŞAĞIDA KODU NOT DEFTERİNE YAPIŞTIR VE KAYDET

```
#Persistent
#NoEnv
SetTitleMatchMode, 2

windowTitle := "OYUN PENCERESİNİN İSMİNİ PARANTEZİN İÇİNE YAZIN"
loopActive := false
isPaused := false

; Macro
LoadScript() {
    Reload
    SetTimer, RunMacro, Off
    loopActive := false
    isPaused := false
    MsgBox, Macro
}

F2::
loopActive := true
isPaused := false
SetTimer, RunMacro, 10
return

F3::
isPaused := true
SetTimer, RunMacro, Off
ControlSend,, {x up}{a up}{w up}{d up}, %windowTitle%
return

F4:: ; Macroyu tazele
LoadScript()
return

RunMacro:
if (loopActive && !isPaused) {
    ControlSend,, {x down}, %windowTitle%
    Sleep, 5
    ControlSend,, {a down}, %windowTitle%
    Sleep, 26850
    ControlSend,, {a up}, %windowTitle%
    Sleep, 5
    ControlSend,, {w down}, %windowTitle%
    Sleep, 450
    ControlSend,, {w up}, %windowTitle%
    Sleep, 5
    ControlSend,, {d down}, %windowTitle%
    Sleep, 26850
    ControlSend,, {d up}, %windowTitle%
    Sleep, 5
    ControlSend,, {w down}, %windowTitle%
    Sleep, 450
    ControlSend,, {w up}, %windowTitle%
    ControlSend,, {x up}, %windowTitle%
}
if (loopActive && !isPaused) {
    SetTimer, RunMacro, 10
}
return
```

# NASIL ÇALIŞIR?

<p>- F2 (MACROYU BAŞLATIR)
<p>- F3 (MACROYU DURDURUR)
<p>- F4 (MACROYA RELOAD) F3 BASMADAN BUNA BASMAYIN ÇÜNKÜ MACRO DURMAZ

# KENDİ TUŞ TAKIMLARINI NASIL OLUŞTURURSUN?

<p> Öncelikle aşağıdaki kod fark ettiyseniz "a tuşuna 26850 milisaniye bas" gibi kodlar içeriyor. Eğer kendi oyununuza özel bir tuş komutları oluşturmak istiyorsanız ama "ben bu işlerden hiç anlamam" diyorsanız; Yukarıdaki kodun tam halini CHATGPT'ye gönderin ve basmak istediğiniz tuşların milisaniyelerini ve sırasını yapay zekaya insana anlatır gibi anlatın. Ardından yapay zekaya kodun size düzeltmiş halini tam haliyle geri vermesini isteyin. 

(DİKKAT EDİN ! Yapay Zeka sadece tuş komutlarını bölümünü değiştirsin ve kodların ControlSend,, komutu içerdiğine dikkat edin. ÇÜNKÜ ! kodun içerisindeki ControlSend,, komutu sayesinde oyun arkaplandayken tuş komutları gönderebiliyorsunuz.)

```
RunMacro:
if (loopActive && !isPaused) {
    ControlSend,, {x down}, %windowTitle%
    Sleep, 5
    ControlSend,, {a down}, %windowTitle%
    Sleep, 26850
    ControlSend,, {a up}, %windowTitle%
    Sleep, 5
    ControlSend,, {w down}, %windowTitle%
    Sleep, 450
    ControlSend,, {w up}, %windowTitle%
    Sleep, 5
    ControlSend,, {d down}, %windowTitle%
    Sleep, 26850
    ControlSend,, {d up}, %windowTitle%
    Sleep, 5
    ControlSend,, {w down}, %windowTitle%
    Sleep, 450
    ControlSend,, {w up}, %windowTitle%
    ControlSend,, {x up}, %windowTitle%
}
if (loopActive && !isPaused) {
    SetTimer, RunMacro, 10
}
return
```

### YUKARDAKİ KOD TAM OLARAK NE YAPIYOR?
<p>- x tuşuna basılı tut
<p>- a tuşuna basılı tut 26850 saniye
<p>- a tuşuna basmayı bırak
<p>- w tuşuna 450 milisaniye bas
<p>- w tuşuna basmayı bırak
<p>- d tuşuna basılı tut 26850 saniye
<p>- d tuşuna basmayı bırak
<p>- w tuşuna 450 milisaniye bas
<p>- w tuşuna basmayı bırak
<p>- x tuşuna basmayı bırak

<p>- Fark ettiyseniz ControlSend,, {x up}, kodunu en alt kısma koyduğum için tüm bu tuşlara basma sırasında x tuşuna hep basılı tutarak yaptı

# KRİTİK TAVSİYELER (OKUMADAN SAYFAYI KAPATMA)

<p>- Controlsend,, özelliğinde mouse tuşları etkisiz olduğu için mouse kontrolünün arka plandayken çalışması mümkün değildir. eğer oynadığınız oyunun Ayarlar kısmından "mouse1, mouse2" gibi tuşlara klavye tuşu atayabiliyorsanız lütfen klavyeden bir tuş ayarlayın.
<p>- oynadığınız oyunu pencere moduna alın böylelikle oyunu 2. monitörde yada daha ufak bir pencere yaparsanız daha kolay takip edebilirsiniz.
<p>- Takıldığınız yada kodlara güncelleme yapmak için ChatGPT kullanın. çok güzel şeyler ekleyebilir kodunuza.


# MİNECRAFT MACROSU YAPACAKLAR BURAYI KESİN OKUSUN

<p> Minecraft'da eğer oyun penceresi seçili değilse Pause ekranı açılır. bunun olmasını engellemek için aşağıdaki adımları uygula

1 - C:\Users\bilgisayar kullanıcı adını yaz\AppData\Roaming\.minecraft ve Minecraft klasörüne git

2 - Options'u txt olarak aç

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/77195dc9-0a7b-4da4-a875-c426e143f92e)

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/aab94cb2-89ef-4ca5-9ca6-63576bd4cb66)

### ARTIK OYUN ARKA PLANA ATILDIĞINDA PAUSE OLMAYACAK

