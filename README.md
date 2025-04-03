# 🧰Google Sheets Useful Tools

All sheets are shared for fee.

---

# All flags of all countries by ISO code

Both Emoji and PNG HD flag.
Domain names.
Phone prefixes.

https://docs.google.com/spreadsheets/d/1uazDIHQxew4WJWd_lhYgIPeBIvMke89q6384BCxpJjg/

![image](https://github.com/user-attachments/assets/f9f4566a-8bc1-48b6-a321-7b86fb5c1c83)

---

# ₿ Shortest formula to compute the total supply of Bitcoin

<img width="207" alt="image" src="https://github.com/VincentBounce/Excel-Google-Sheet-formulas/assets/64386272/006322f4-8bb5-4204-8e03-fca0ada8a4df">

## First formula draft

`=SERIESSUM(2,0,-1,{210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50,210000*50})`

## Best optimization after some iterations 💚
```
=SERIESSUM(2,0,-1,SEQUENCE(33, 1, 210000*50, 0))
```
Output = 20,999,999.9975553 | to get this ouput, need to display 7 digits after the decimal point on Excel/GoogleSheets

---

# ⤴️URL on Google Sheets

## To encode a URL

B1: `="https://fr.wikipedia.org/wiki/"&ENCODEURL("Indiana Jones et le Royaume du crâne de cristal")`

Output B1: `https://fr.wikipedia.org/wiki/Indiana%20Jones%20et%20le%20Royaume%20du%20cr%C3%A2ne%20de%20cristal`

## To decode a URL

B2: `https://fr.wikipedia.org/wiki/Indiana_Jones_et_le_Royaume_du_cr%C3%A2ne_de_cristal`

C2:
```
=SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(B2,"%3F","?"),"%20"," "),"%25", "%"),"%26","&"),"%27","'"),"%2B","+"),"%2C",","),"%2D","-"),"%2E","."),"%3D","="),"%7B","{"),"%7D","}"),"%5B","["),"%5D","]"),"%5F","_"),"%3A",":"),"%22",""""),"%C3%80","À"),"%C3%81","Á"),"%C3%82","Â"),"%C3%83","Ã"),"%C3%84","Ä"),"%C3%85","Å"),"%C3%86","Æ"),"%C3%87","Ç"),"%C3%88","È"),"%C3%89","É"),"%C3%8A","Ê"),"%C3%8B","Ë"),"%C3%8C","Ì"),"%C3%8D","Í"),"%C3%8E","Î"),"%C3%8F","Ï"),"%C3%91","Ñ"),"%C3%92","Ò"),"%C3%93","Ó"),"%C3%94","Ô"),"%C3%95","Õ"),"%C3%96","Ö"),"%C3%99","Ù"),"%C3%9A","Ú"),"%C3%9B","Û"),"%C3%9C","Ü"),"%C3%A0","à"),"%C3%A1","á"),"%C3%A2","â"),"%C3%A3","ã"),"%C3%A4","ä"),"%C3%A5","å"),"%C3%A6","æ"),"%C3%A7","ç"),"%C3%A8","è"),"%C3%A9","é"),"%C3%AA","ê"),"%C3%AB","ë"),"%C3%AC","ì"),"%C3%AD","í"),"%C3%AE","î"),"%C3%AF","ï"),"%C3%B1","ñ"),"%C3%B2","ò"),"%C3%B3","ó"),"%C3%B4","ô"),"%C3%B5","õ"),"%C3%B6","ö"),"%C3%B9","ù"),"%C3%BA","ú"),"%C3%BB","û"),"%C3%BC","ü"),"%C5%93","œ"),"%E2%80%93","–")
```

Output C2 = `https://fr.wikipedia.org/wiki/Indiana_Jones_et_le_Royaume_du_crâne_de_cristal`

## To get a movie title from a Wikipedia link

D2:
```
=substitute(substitute(substitute(substitute(mid(C2,31,256),"_"," ")," film)",")"),"(film, ","(")," (film)","")
```

Output D2: `Indiana Jones et le Royaume du crâne de cristal`
