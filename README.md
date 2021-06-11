# Let your music paint the picture
Aplicatia are ca scop crearea unor vizualuri bazate pe proprietati ale fisierului muzical introdus. 

## (Instalare)
Pentru a putea rula atat aplicatia cat si interfata grafica este necesara instalarea aplicatiei TouchDesigner. 
! Pentru a putea fi utilizata la capacitate maxima este nevoie de un procesor destul de puternic. In caz contrar se vor intampina probleme la redarea sunetului/ crearea vizualurilor/ utilizarea butoanelor. 

## (Utilizare)
Aplicatia contine o interfata grafica ce permite utilizatorului sa:
        - aleaga un fisier audio de pe disc
        - sa vizualizeze unul din cele trei posibile vizualuri
        - sa porneasca/opreasca fisierul audio si implicit vizualurile
Obs: se poate vizualiza doar cate un outpu (in codul python care controleaza afisarea pentru fiecare Window, initial se inchid toate celalalte ferestre de redare).

## (Istoric)

1. Prima etapa reprezinta procesarea fisierului audio. Pentru acest lucru am folosit componenta builtin audioAnalysis care permite extragerea parametrilor: low, mid, high, spectral centroid, slow moving partials density, fast moving partials density, kick, snare, rythm. Toti acesti parametrii sunt extrasi individual in blocuri de tip Select si apoi scosi cu ajutorul componentelor Out pentru a putea fi procesati in exteriorul blocului de analiza al fisierului audio. 
2. A doua etapa o reprezinta crearea partii vizuale. Pentru acest lucru am utilizat ca baza componenta Noise. Pentru a da senzatia de miscare, parametrii de intrare pentru Noise variaza in functie de parametrii extrasi din fisierul audio. Din blocul Noise se despart trei ramuri, fiecare continand diferite efecte pentru imagini ale caror parametrii de intrare sunt modificati de parametrii de iesire ai fisierului sonor. 
3. Ultima etapa o reprezinta crearea interfetei grafice pentru utilizator. Desi TouchDesigner nu ofera posibilitatea crearii unui UI complex, ofera insa o multitudine de butoane care pot fi legate la diferitele componente ale fluxului. Interfata in sine este tinuta intr-o componenta de tip Container. Acesteia i-am asociat diferite butoane : buttonRocker(play/stop), fieldFileBrowser(alegerea fisierului de pe disc), toggleButton(pentru a selectia unul dintre cele trei posibile outputuri). Legatura dintre butoanele interfetei si actiunile celorlalte componente se face prin utilizrea unor componente de tip Constant. Acestea pot avea un numar dat de canale ce contin informatii legate de starea butoanelor. Cu ajutorul acestor canale am realizat trei scripturi scurte in Python pentru a putea controla parametrii de afisare/inchidere ale ferestrelor pentru vizualuri. Scripturile sunt create cu ajutorul componentei CHOP Execute.

       

## (Link-uri)
Proiectul este 100% creatie proprie insa m-am folosit de diferite tutoriale Youtube/documentatii de pe site-ul oficial/forumuri pentru a intelege ce se poate crea in aplicatie si cum. 
https://matthewragan.com/2013/10/10/sending-and-receiving-osc-values-with-touchdesigner/
https://docs.derivative.ca/Panel_Execute_DAT
https://docs.derivative.ca/OP_Execute_DAT
https://www.youtube.com/watch?v=4-oPy4RFZK0
https://www.youtube.com/watch?v=fgs6DVdUkM0
https://vimeo.com/376574533
https://www.youtube.com/watch?v=oviwpILXo5A&list=PLiLQehonm_r89FxLfu2dbxqeas5irwwZa&index=1
https://www.youtube.com/watch?v=gUELH_B2wsE&list=PLiLQehonm_r89FxLfu2dbxqeas5irwwZa&index=2
https://www.youtube.com/c/TheInteractiveImmersiveHQ
https://www.youtube.com/watch?v=Jh18yHfYT0I
https://www.youtube.com/watch?v=MZs7co3udO0&t=606s
https://www.youtube.com/watch?v=gUELH_B2wsE&t=65s
https://www.youtube.com/watch?v=oviwpILXo5A&t=5shttps://www.youtube.com/c/MatthewRaganMFA
https://www.youtube.com/watch?v=eozyY_lO9vM&t=323s
https://www.youtube.com/watch?v=B0lEnVglMkk
https://matthewragan.com/2016/07/06/python-in-touchdesigner-executes-touchdesigner/
https://matthewragan.com/2020/11/04/touchdesigner-the-big-bad-ass-lister-part-2-3/
https://matthewragan.com/2014/06/01/understanding-referencing-touchdesigner/
https://derivative.ca/community-post/tutorial/kinetic-typography-touchdesigner-part-2-ui-build
https://alltd.org/python-scripting-beginners-touchdesigner/

# Dezvoltarea proiectului


Pentru început:

1. Creează-ți cont pe Github
2. Download și install [Github Desktop](https://desktop.github.com/)
3. Citește [acest ghid](https://charlesmartin.com.au/blog/2020/08/09/student-project-repository) și ține la îndemână [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet).

Apoi, procesul este următorul (inspirat de [aici](https://cs.anu.edu.au/courses/comp1720/deliverables/05-major-project/#submission-process)):

1. *fork* al acestui template către propriul tău cont de Github

![](assets/fork.gif)

_(dacă preferi cumva ca repo-ul să nu fie vizibil de către public, îl poți seta ca Private din Settings - "Change visibility". Atunci trebuie să mă adaugi drept colaborator, ca eu să am acces.)_

2. *clone* al repo-ului din Github Desktop pentru a-l downloada local

![](assets/clone.gif)

3. *commit* și *push* pe măsură ce lucrezi la proiect. Ultima versiune push-ată pe server înainte de deadline va conta pentru evaluare.

![](assets/commit.gif)

## Elemente obligatorii

1. Acest readme completat. Titlu, descriere, mod de utilizare, istoric, link-uri utile.

   Poți include și imagini și chiar [gif-uri animate](https://www.screentogif.com/), sau link-uri către materiale audio/video.
   
   Vezi [aici](https://charlesmartin.com.au/blog/2020/08/09/student-project-repository) mai multe sugestii.

2. [Declarația de originalitate](statement-of-originality.yml) completată. Tot ce nu este inclus acolo va fi considerat 100% contribuție proprie.

    *(formatul este adaptat de [aici](https://gitlab.cecs.anu.edu.au/comp1720/2018/comp1720-2018-major-project/-/blob/master/statement-of-originality.yml). Da, este un pic ironic să refolosim un doc [de altundeva](https://cs.anu.edu.au/courses/comp1720/resources/faq/#how-do-i-fill-out-my-statement-of-originality), dar menționăm sursa deci nu este plagiat!)*

3. Proiectul în sine. Tot codul trebuie să fie prezent, proiectul trebuie să poată rula conform instrucțiunilor din readme. Dacă e nevoie de asset-uri mari (sunete, video etc), [folosește Git LFS](https://git-lfs.github.com/) sau include link de download în instrucțiunile de instalare.

