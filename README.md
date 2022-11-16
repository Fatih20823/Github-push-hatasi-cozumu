<h1> GitHub Push hatası:
 
* "git push -u origin master" komutunu girdiğimde

* To '[repository url]'
! [rejected] master -> master (fetch first)
error: failed to push some refs to '[repository url]'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first merge the remote changes (e.g.,
hint: 'git pull') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
BOYLE BİR HATA ALIYORSAN
<h1> Çözümü
 
# git push -f komutunu çok zorda kalmadığınız zaman (ki neredeyse hiçbir zaman bu durum görülmez) kullanmayın. -f flag'ı
# force anlamına gelir ve sizin local repository de bulunan dosyaları remote repository'e push yapmaya zorlar. Genelde github'ı kullanmaya yeni başlayan kişiler bu hatayı alır. Çünkü yeni repository oluşturdukları zaman "create Readme file" seçeneğine tıklarlar ve bu da remote repository'de readme.md dosyası oluşturur. İşte sorun tam olarak burdadır. Local repository'de readme.md dosyası yokken remote repository'de böyle bir dosya olması git'te kafa karışıklığına sebep olur. Bu durumu çözmek için önce remote repository'de ki dosyaları pull etmek gerekir. "git pull origin master --allow-unrelated-histories" komutunu kullanarak önce pull edip ardından git push -u origin master komutu ile herhangi bir zorlama işlemi yapmadan push yapabilirsiniz.

# Push yapmak için -f flagini kullanmak tek başınıza yaptığınız projeler için problem teşkil etmeyebilir. Ancak ortak çalıştığınız
# projelerde bir faciaya neden olabilirsiniz.
