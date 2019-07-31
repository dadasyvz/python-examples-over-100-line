import random
import time

tahta =  ["1", "2", "3",
          "4", "5", "6",
          "7", "8", "9"]

def yazdir():
    print(tahta[0]+" "+tahta[1]+" "+tahta[2]+"\n"+
          tahta[3]+" "+tahta[4]+" "+tahta[5]+"\n"+
          tahta[6]+" "+tahta[7]+" "+tahta[8])

kazanim_ihtimalleri = []
engelleme_ihtimalleri = []
yazdir()

while True:

    secim = input("secim=")
    if secim == "X" or secim == "O":
        continue
    tahta[tahta.index(secim)] = "X"
    time.sleep(1)
    yazdir()

    a = 0
    for i in tahta:                         #bu dongu ile tahta uzerinde ki sayilardan
        if i.isdigit() == False:            # 9 tanesinin de x veya o olma durumu kontrol ediliyor
            a += 1                          # 9 taneside x veya o olmussa oyunun berabere kaldigi anlasilmaktadir
            if a == 9:
                print("berabere kaldiniz...")
                yazdir()
                quit()

    while True:
        bilgisayar = random.choice(tahta)
        basari = [[tahta[0] + tahta[1] + tahta[2]],
                  [tahta[3] + tahta[4] + tahta[5]],
                  [tahta[6] + tahta[7] + tahta[8]],
                  [tahta[0] + tahta[3] + tahta[6]],
                  [tahta[1] + tahta[4] + tahta[7]],
                  [tahta[2] + tahta[5] + tahta[8]],
                  [tahta[0] + tahta[4] + tahta[8]],
                  [tahta[2] + tahta[4] + tahta[6]]]

        for i in basari:
            if i[0][0] == "O" and i[0][1] == "O":
                if i[0][2] == "X":
                    continue
                else:
                    kazanim_ihtimalleri.append(i[0][2])
            elif i[0][0] == "O" and i[0][2] == "O":                 #buradaki dongude bilgisayarin 3 lu kazanma ihtimalleri icerisinde
                if i[0][1] == "X":                                  # iki olasiligin gerceklesmesi durumunda tamamlayici 3. durum
                    continue                                        #kazanma ihtimalleri listesine ekleniyor
                else:
                    kazanim_ihtimalleri.append(i[0][1])
            elif i[0][1] == "O" and i[0][2] == "O":
                if i[0][0] == "X":
                    continue
                else:
                    kazanim_ihtimalleri.append(i[0][0])

        for i in basari:
            if i[0][0] == "X" and i[0][1] == "X":
                if i[0][2] == "O":
                    continue
                else:
                    engelleme_ihtimalleri.append(i[0][2])
            elif i[0][0] == "X" and i[0][2] == "X":             #buradaki dongude oyuncunun 3 lu kazanma ihtimalleri icerisinde
                if i[0][1] == "O":                              #iki olasiligin gerceklesmesi durumunda tamamlayici 3.durum
                    continue                                    #engellenmek uzere engelleme ihtimalleri listesi icerisine ekleniyor
                else:
                    engelleme_ihtimalleri.append(i[0][1])
            elif i[0][1] == "X" and i[0][2] == "X":
                if i[0][0] == "O":
                    continue
                else:
                    engelleme_ihtimalleri.append(i[0][0])

        if kazanim_ihtimalleri != []:
            bilgisayar = random.choice(kazanim_ihtimalleri)
            tahta[tahta.index(bilgisayar)] = "O"
            time.sleep(1)
            print("bilgisayar kazandi")                     #kazanma ihtimallerinde eleman olmasi durumunda ilk olarak bilgisayar
            yazdir()                                        #kazanabilecegi ihtimali secip kazanip oyunu bitiriyor
            time.sleep(1)
            quit()

        if engelleme_ihtimalleri != []:
            bilgisayar = random.choice(engelleme_ihtimalleri)
            tahta[tahta.index(bilgisayar)] = "O"
            time.sleep(1)
            print("bilgisayar oynuyor...")                  #kazanma ihtimali olmadiginda engelleme listesi kontrol edilerek
            yazdir()
            engelleme_ihtimalleri=[]                       #oyuncunun kazanmasi engellenmeye calisiliyor ve oyuncunun oynamasi
            break                                           #amaciyla dongu basina donduruluyor

        while True:
            bilgisayar = random.choice(tahta)

            if bilgisayar == "X" or bilgisayar == "O":
                continue
            else:                                            #kazanim ihtimali yada engelleme ihtimali olmadigi durumda tahta icerisinden
                tahta[tahta.index(bilgisayar)] = "O"         #random eleman secilip tahtada yer degistirilip devam ediliyor
                print("bilgisayar oynuyor...")
                time.sleep(1)
                yazdir()
                break



        for i in basari:
            if i[0][0] == "X" and i[0][1] == "X" and i[0][2] == "X":
                print("siz kazandiniz...")                          #burada bilgisayar veya oyunucunu oyunu kazanma durumu kontrol ediliyor
                yazdir()
                quit()
        for i in basari:
            if  i[0][0]=="O" and i[0][1]=="O" and i[0][2]=="O":
                print("bilgisayar kazandi...")
                yazdir()
                quit()
        break
