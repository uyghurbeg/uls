# uls

![alt text](https://github.com/uyghurbeg/uls/blob/master/demo.png)

A Wordpress Plugin to convert UEY to ULY/USY

Wordpress Uchun Uyghurche Yeziqlarni almashturush qisturmisi


Salam. Mezkur qisturma G.Toxti Kenji ependi teripidin yasalghan bolup, uning ruxsiti bilen, githubgha quyuldi. Kodning barliq hoquqi G.Toxti Kenji'ge mensuptur.

Ishlitish Usuli:
1. Hojjetlerni Wordpress qachilanghan bash munderijige quyung
2. www.yourdomain.xxx(sizning bekitigizning adresini)/yengila.php ni eching

shuning bilen qisturma utuqluq halda qachilinidu.

Unumini korush:

Ortaq Turk yeziqi uchun:
www.yourdomain.xxx/?uls=ut

Uyghur Latin yeziqi uchun:
www.yourdomain.xxx/?uls=ul

Uyghur Kiril/Slawiyan yeziqi uchun:
www.yourdomain.xxx/?uls=us

Uyghur Ereb yeziqigha qaytish uchun:
www.yourdomain.xxx/?uls=uu

Bashqa tengshekler:
!. Bezi uslublarda ishlimesliki mumkin;

!!. Yeziq almashturush uchun herbir herpni tekshuridighan bolghachqa, bezi uzun tekst bar betlerni almashturushqa ketidighan waqit uzaq bolup ketishi mumkin, hetta betler echilmay aq bolup qelishi mumkin, bu chaghda Uyghur Ereb yeziqigha qaytish ulinishini besiwetsigiz bolidu;

!!!. Torbiket eslidin Uyghur Ereb yeziqida putken bolushi we putunley Uyghurchigha maslashturulghan bolsa unumi teximu yaxshi;

!!!!. Qisturmini qachilap bolup, Wordpress'ning neshiri yengilash meshghulati qilsigiz qisturma ishlimesliki mumkin, bu chaghda http://www.yourdomain.xxx/yengila.php ni besiwetsigiz ongshilidu.


1.Ereb yeziqidin Latin/Kril yeziqigha almashqanda, herpler soldin onggha ozgirishi kirek, buning uchun soldin bashlanghan yeziqqa maslashturup bir css hojjti teyyarlang, andin uni uls.php ichige rtl.css larni quyung
Ornek:
```
function ayladur($out)
{
    if($_SESSION['uls'] == "ul")
    {
		$out=U2L($out);
		$out=str_replace("style.css", "ltr.css", $out);
		$out=str_replace("bootstrap.min.css", "bootstrap.min.ltr.css", $out);
    }
    else if($_SESSION['uls'] == "us")
    {
		$out=U2S($out);
		$out=str_replace("style.css", "ltr.css", $out);
		$out=str_replace("bootstrap.min.css", "bootstrap.min.ltr.css", $out);
    }
    else if($_SESSION['uls'] == "ut")
    {
		$out=U2T($out);
		$out=str_replace("style.css", "ltr.css", $out);
		$out=str_replace("bootstrap.min.css", "bootstrap.min.ltr.css", $out);
    }
    return $out;
}
```
2. Tillarning yeziqini ulinishqa qoshqanda towendiki buyiche qushung:

ئۇيغۇرچە(Ereb yeziqidiki isim uchun):
```
&#1574;&#1735;&#1610;&#1594;&#1735;&#1585;&#1670;&#1749;
```
УЙҒУРЧӘ(Kril yeziqidiki isim uchun):
```
&#1059;&#1081;&#1171;&#1091;&#1088;&#1095;&#1241
```
Uyghurche(Latin yeziqidiki isim uchun):
```
&#85;&#121;&#103;&#104;&#117;&#114;&#99;&#104;&#101;
```
Uyğurçe(Ortaq Turk yeziqidiki isim uchun):
```
Uyğurçe
```

Ornek:
```
<div style="direction: ltr; float: right; padding-right: 60px; padding-top: 6px; text-transform: capitalize;"> <a href="?uls=us">&#1059;&#1081;&#1171;&#1091;&#1088;&#1095;&#1241;</a> | <a href="?uls=ul">&#85;&#121;&#103;&#104;&#117;&#114;&#99;&#104;&#101;</a> | <a href="?uls=ut">uyğurçe</a> | <a href="?uls=uu">&#1574;&#1735;&#1610;&#1594;&#1735;&#1585;&#1670;&#1749;</a> </div>
```
