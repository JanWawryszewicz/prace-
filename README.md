from mingry import losowaniegracz,taktycznyatak,uderzenieog,arcyatak,niszczyciel,deszczpo,mieszankawy,atakpoz 
import random
name = input('Podaj imie twojego dowódcy: ')
nameod = input("Podaj przydomek swojej armii:")
lifea = 5
lifelj = 25
lifezwj = 100
pieniądze = 10000
print(f"{name} jest teraz dowódcą armii {nameod}")
pytanie2 = 0
wybor = 0
Listaatk = [taktycznyatak()]
listabot = [uderzenieog(),taktycznyatak(),niszczyciel()]

def bitawa(): 
       global lifezwj,lifelj,lifea,sk,dk,ak
       wk =random.randint(15,25) 
       kl = random.randint(2,8) 
       mk= random.randint(0,2) 
       pk= random.randint(10,20)
       ik= random.randint(1,5) 
       nk= random.randint(1,2) 
       print("Wybrałeś bitwę")
       print("Przeciwnik ma zwykłych jednostek:",sk) 
       print("Przeciwnik ma lepszych jednostek:",dk) 
       print("Przeciwnik ma artylerii:",ak) 
       print("czy chcesz podjąc walkę????")
       potw = input("Napisz tak lub nie:").lower()
       if potw =='nie':
          print("no trudno, może kiedy indziej")
       elif potw =='tak':
          print("zaczołeś bitwę co teraz:")
          while sk>0 or dk>0 or ak>0: 
          
            print(f"użyj ataków: {Listaatk}")
            ptw = input("Napisz nazwę ataku:")
            if ptw == 'taktyczny atak' and taktycznyatak() in Listaatk and lifezwj>=10 and lifelj>=1:
               print("użyłeś taktycznego ataku")
               X = random.randint(10,20)
               Z = random.randint(20,30)
               Y = random.randint(1,5)
               lifezwj -=X
               lifelj -= Y
               sk -= Z
               xzz =random.choice(listabot)
               if xzz == uderzenieog():
                  lifezwj-=wk
                  lifea-=mk
                  lifelj-=kl
                  print("przeciwnik użył uderzenia ognia")
               elif xzz == taktycznyatak():
                  lifezwj-=pk
                  lifelj-=ik
                  print("przeciwnik użył taktycznego ataku")
               elif xzz == niszczyciel():
                  lifezwj-=pk
                  lifelj-=ik
                  lifea-=nk
                  print("przeciwnik użyl niszczyciela")
               print(f"po ataku masz {lifezwj} zwykłych jednostek, {lifelj} lepszych jednostek i {lifea} artylerii, a przeciwnik ma {sk} zwyczajnych jednostek, {dk} lepszych jednostek i {ak} artylerii")
            elif ptw == 'uderzenie ognia' and uderzenieog() in Listaatk and lifea >=1:
               YX = random.randint(0,2)
               ZY = random.randint(25,30)
               XY = random.randint(10,20)
               sk -= ZY
               dk -= XY
               ak -= YX
               lifezwj -= XY
               xzz =random.choice(listabot)
               if xzz == uderzenieog():
                  lifezwj-=wk
                  lifea-=mk
                  lifelj-=kl
                  print("przeciwnik użył uderzenia ognia")
               elif xzz == taktycznyatak():
                  lifezwj-=pk
                  lifelj-=ik
                  print("przeciwnik użył taktycznego ataku")
               elif xzz == niszczyciel():
                  lifezwj-=pk
                  lifelj-=ik
                  lifea-=nk
                  print("przeciwnik użył niszczyciela")
               print(f"po ataku masz {lifezwj} zwykłych jednostek, {lifelj} lepszych jednosteki i {lifea} artylerii, a przeciwnik ma {sk} zwyczajnych jednostek, {dk} lepszych jednostek i {ak} artylerii")
            elif ptw == 'arcyatak' and arcyatak() in Listaatk and lifezwj >= 10 and lifelj >= 2:
               YX = random.randint(0,1)
               ZY = random.randint(25,30)
               XY = random.randint(10,15)
               XX = random.randint(2,8)
               sk -= ZY
               dk -= XY
               ak -= YX
               lifezwj -= XY
               lifelj -= XX
               xzz =random.choice(listabot)
               if xzz == uderzenieog():
                  lifezwj-=wk
                  lifea-=mk
                  lifelj-=kl
                  print("przeciwnik użył uderzenia ognia")
               elif xzz == taktycznyatak():
                  lifezwj-=pk
                  lifelj-=ik
                  print("przeciwnik użył taktycznego ataku")
               elif xzz == niszczyciel():
                  lifezwj-=pk
                  lifelj-=ik
                  lifea-=nk
                  print("przeciwnik użyl niszczyciela")
               print(f"po ataku masz {lifezwj} zwykłych jednostek, {lifelj} lepszych jednosteki i {lifea} artylerii, a przeciwnik ma {sk} zwyczajnych jednostek, {dk} lepszych jednostek i {ak} artylerii")
            elif ptw == 'niszczyciel' and niszczyciel() in Listaatk and lifezwj >=10:
               YX = random.randint(0,2)
               ZY = random.randint(25,30)
               XY = random.randint(10,20)
               sk -= ZY
               dk -= XY
               ak -= YX
               lifezwj -= XY
               xzz =random.choice(listabot)
               if xzz == uderzenieog():
                  lifezwj-=wk
                  lifea-=mk
                  lifelj-=kl
                  print("przeciwnik użył uderzenia ognia")
               elif xzz == taktycznyatak():
                  lifezwj-=pk
                  lifelj-=ik
                  print("przeciwnik użył taktycznego ataku")
               elif xzz == niszczyciel():
                  lifezwj-=pk
                  lifelj-=ik
                  lifea-=nk
                  print("przeciwnik użyl niszczyciela")
               print(f"po ataku masz {lifezwj} zwykłych jednostek, {lifelj} lepszych jednostek i {lifea} artylerii,a przeciwnik ma {sk} zwyczajnych jednostek, {dk} lepszych jednostek i {ak} artylerii")
            elif ptw == 'deszcz pociskow' and deszczpo() in Listaatk and lifezwj>= 5:
               KJ = random.randint(20,30)
               HJ = random.randint(5,10)
               sk-=KJ
               dk-=HJ
               lifezwj-=HJ
               xzz =random.choice(listabot)
               if xzz == uderzenieog():
                  lifezwj-=wk
                  lifea-=mk
                  lifelj-=kl
                  print("przeciwnik użył uderzenia ognia")
               elif xzz == taktycznyatak():
                  lifezwj-=pk
                  lifelj-=ik
                  print("przeciwnik użył taktycznego ataku")
               elif xzz == niszczyciel():
                  lifezwj-=pk
                  lifelj-=ik
                  lifea-=nk
                  print("przeciwnik użyl niszczyciela")
               print(f"po ataku masz {lifezwj} zwykłych jednostek, {lifelj} lepszych jednostek i {lifea} artylerii,a przeciwnik ma {sk} zwyczajnych jednostek, {dk} lepszych jednostek i {ak} artylerii")
            elif ptw == 'atak pozycyjny' and atakpoz() in Listaatk and lifezwj >=10 and lifelj >=1:
               KW = random.randint(0,1)
               HW = random.randint(10,15)
               LW= random.randint(2,5)
               sk -= HW
               dk -= LW
               ak -= KW
               lifezwj -= 10
               lifelj -= 1
               xzz =random.choice(listabot)
               if xzz == uderzenieog():
                  lifezwj-=wk
                  lifea-=mk
                  lifelj-=kl
                  print("przeciwnik użył uderzenia ognia")
               elif xzz == taktycznyatak():
                  lifezwj-=pk
                  lifelj-=ik
                  print("przeciwnik użył taktycznego ataku")
               elif xzz == niszczyciel():
                  lifezwj-=pk
                  lifelj-=ik
                  lifea-=nk
                  print("przeciwnik użyl niszczyciela")
               print(f"po ataku masz {lifezwj} zwykłych jednostek, {lifelj} lepszych jednostek i {lifea} artylerii,a przeciwnik ma {sk} zwyczajnych jednostek, {dk} lepszych jednostek i {ak} artylerii")
            elif ptw == 'mieszanka wybuchowa' and mieszankawy() in Listaatk:
               K = random.randint(1,3)
               H = random.randint(30,35)
               L= random.randint(10,20)
               sk -= H
               dk -= L
               ak -= K
               lifezwj -= L
               lifelj -= 3
               xzz =random.choice(listabot)
               if xzz == uderzenieog():
                  lifezwj-=wk
                  lifea-=mk
                  lifelj-=kl
                  print("przeciwnik użył uderzenia ognia")
               elif xzz == taktycznyatak():
                  lifezwj-=pk
                  lifelj-=ik
                  print("przeciwnik użył taktycznego ataku")
               elif xzz == niszczyciel():
                  lifezwj-=pk
                  lifelj-=ik
                  lifea-=nk
                  print("przeciwnik użyl niszczyciela")
               print(f"po ataku masz {lifezwj} zwykłych jednostek, {lifelj} lepszych jednostek i {lifea} artylerii, a przeciwnik ma {sk} zwyczajnych jednostek, {dk} lepszych jednostek i {ak} artylerii")  
               if sk <= 0 and dk <= 0 and ak <= 0:
                  break
while lifea>=0 and lifelj>=0 and lifezwj>=0 and pieniądze>0:

 if pieniądze < 0:
    print("jesteś zadłużony, lepiej szybko zarób pieniądze zanim będzie za późno")
 print(f"twoje saldo wynosi {pieniądze}, masz {lifezwj} zwyczajnych jednostek, masz {lifelj} lepszych jednostek, masz {lifea} artylerii")
 print("Co dalej dowódco?")
 print("wybierz odpowiednią liczbę:")      
 print("1.Zagraj w ruletkę, 2.Otwórz sklep, 3.Zacznij bitwę, 4.zamknij grę")
 pytanie = input()
 
 
 if pytanie == "2":
     print ("Wszedłeś do sklepu czego potrzebujesz")
     print("Wybierz odpowiednią opcję")
     print("1sklep. Kupno jednostek ")
     pytanie2 = input()
     if pytanie2 == "1sklep":
      print("wybierz jednostkę:")
      print("zwykłaj - 25, lepszaj - 50, artyleria - 200")
      pytaniej = input()
      if pytaniej == "zwykłaj" and pieniądze >= 25:
         print("ile chcesz jej kupić")
         opcje = int(input())
         lifezwj += opcje
         pieniądze -= 25 * opcje
      elif pytaniej == "lepszaj" and pieniądze >= 50:
         print("Ile chcesz jej kupić?")
         opcje = int(input())
         lifelj += opcje
         pieniądze -= 50 * opcje
      elif pytaniej == "artyleria" and pieniądze >= 200:
         print("Ile chcesz jej kupić?")
         opcje = int(input())
         lifea += opcje
         pieniądze -= 200 * opcje
      else:
         print("nie masz wystarczjących środków")
     
     if pytanie2 == '2sklep':
      print ("wybierz atak który chcesz kupić")
      pytaniew = input("możesz kupić:uderzenie ognia, arcyatak, niszczyciel, deszcz pociskow, atak pozycyjny, mieszanka wybuchowa:")
      if pytaniew == 'uderzenie ognia' and pieniądze >= 400:
         pieniądze -= 400
         Listaatk.append(uderzenieog())
         print("brawo kupiełś uderzenie ognia")
      elif pytaniew == 'arcyatak' and pieniądze >= 550:
         pieniądze -= 550
         Listaatk.append(arcyatak())
         print("brawo kupiłeś arcyatak")
      elif pytaniew == 'niszczyciel' and pieniądze >= 700:
         pieniądze -= 700
         Listaatk.append(niszczyciel())
         print("brawo kupiłeś niszczyciela")
      elif pytaniew == 'deszcz pociskow' and pieniądze >= 950:
         pieniądze-=950
         Listaatk.append(deszczpo())
         print("brawo kupiłes deszcz pociskow!!!")
      elif pytaniew == 'atak pozycyjny' and pieniądze >= 1000:
         pieniądze-=1000
         Listaatk.append(atakpoz())
         print("brawo kupiłes deszcz atak pozycyjny!!!")
      elif pytaniew == 'mieszanka wybuchowa' and pieniądze >= 1750:
         pieniądze-=1750
         Listaatk.append(mieszankawy())
         print("brawo kupiłes mieszankę wybuchową!!!")
      else:
         print("nie można kupić ataku lub taki atak nie istnieje")
 
 if pytanie == "1":
    print(losowaniegracz(wybor=['czerwony','czarny']))
    wybor = input().lower()
    opcje = ['czerwony','czarny']
    wynik = random.choice(opcje)
    if wybor == wynik:
      print("WYGRAŁEŚ")
      pieniądze+=pieniądze
    elif wybor != wynik:
      print("PRZEGRAŁES")
      pieniądze-=pieniądze/2
 else:
    ("nieprawdiłowe polecenie")
 
 
 if pytanie == "3":
    print("wszedłeś do bitwy!!!!!!!")
    print("Wybierz tryb bitwy")
    pytaniek = input().lower()
    if pytaniek == 'bitwa1':
       sk = random.randint(30,80)
       dk =  random.randint(10,30)
       ak = random.randint(1,5)  
       print(bitawa())
    elif pytaniek == 'bitwa2':
       sk = random.randint(80,150)
       dk =  random.randint(30,50)
       ak = random.randint(3,6)
       print(bitawa())          
 if pytanie == '4':
    break
