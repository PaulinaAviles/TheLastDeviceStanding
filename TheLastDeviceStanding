import processing.sound.*;

PImage screen1;
PImage screen2;
PImage screen3;
PImage screen4;

SoundFile file1;
PFont font;
PFont font2;
PFont font3;


//variables globales
figura casete;
figura cd;
figura sd;
figura disqu;
figura nube;
figura usb;


int w=1000;
int h=600;


int pantalla=1;
int turno=1;
int personaje;
String s;
int cx1,cx2,cy1,cy2,f;
int slc=1;
int j1,j2;
int sz;
int attk1, attk2, life1, life2,l1,l2;
int win;
int b1=300;
int b2=300;


float[] px=new float[1000];
float[] py=new float[600];
float[] dx=new float[1000];
float[] dy=new float[600];

void settings(){
  size(w, h);
}

void setup(){
    background(9,22,34);
    file1 = new SoundFile(this, "music.mp3");
    file1.loop();
    
    
    font = loadFont("KomikaAxis-48.vlw");
    font2 = loadFont("Futura-Medium-48.vlw");
    font3 = loadFont("FuturaHand-48.vlw");
    
    screen1 = loadImage("img1.png");
    screen2 = loadImage("img2.png");
    screen3 = loadImage("img3.png");
    screen4 = loadImage("img4.png");
        //---
    casete= new figura(width/4,height/3,.4,10,60);
    sd=new figura(width/2, height/3, 1.5,12,84);
    nube=new figura(3*width/4, height/3, .3,20,76);
    cd=new figura(width/4, 3*height/4, .3,18,70);
    disqu=new figura(width/2, 3*height/4, .3, 6, 100);
    usb=new figura(3*width/4, 3*height/4, 1.4 ,15 , 90);
        //---
      
        for(int i=0; i<400; i++){
          px[i] = random(1000);
          py[i] = random(600);
          dx[i] = random(-1,1);
          dy[i] = random(-1,1);
        }//for 
}//setup

void draw(){
 
 if(pantalla==1){
   pantalla1();
 }   

 if(pantalla==2){
     if (slc==1){
       grande();
       selec1();
     }
     if (slc==2){
       selec2();
       grande();
     }   
 }//pant 2
 
 
 if(pantalla==3){
   fight();
   barra();
 }
 
 if(pantalla==4){ pantalla4();
 }
   
}//draw



//--------------------------
    void pantalla1(){
        image(screen1, 0, 0);
        
      //nombre
        textFont(font, 50);
        textAlign(CENTER,CENTER);
        String s1 = "The last device standing";
        fill(255);
        text(s1, width/2, height/3);  
      
      //intro
       textFont(font2, 20);
        s1 = "En medio de un mundo con miles de opciones, ellos se pelean por ser el dispositivo principal";
        fill(181,241,243);
        textAlign(CENTER);
        text(s1, width/2, 2*height/5); 
      
      //botón
        textAlign(CENTER,CENTER);
        noStroke();
        fill(195,232,250);
        rectMode(CENTER);
        rect(width/2, 4*height/5, 100,50,10);
      
      //texto botón
      textFont(font, 20);
        fill(21,66,108);
        text("JUGAR", width/2, 4*height/5); 
        
      //intro
        s1 = "Da click en el botón para comenzar";
        fill(255);
        textSize(12);
        textAlign(CENTER);
        //background(253,247,210);
        text(s1, width/2, 8*height/9); 
      
      
      //pantalla1-->pantalla2
         if(mousePressed & (mouseX >= width/2-50 & mouseX <= width/2+50)&(mouseY>= 4*height/5-25 & mouseY <= 4*height/5+25)){
           pantalla=2;
            mousePressed=false;
          } //if 
      }//void 1
      

   void pantalla2(){
       image(screen2, 0, 0);
       
        noStroke();
        fill(246,199,130);
        rectMode(CENTER);
        
       //rectangulo 1, back
        rect(width/4, height/3, 130,170,10);
        
       //rectangulo 2, back
        rect(width/2, height/3, 130,170,10);
        
       //rectangulo 3, back
        rect(3*width/4, height/3, 130,170,10);
      
      //rectangulo 4, back
        rect(width/4, 3*height/4, 130,170,10);
      
      //rectangulo 5, back
        noStroke();
        rect(width/2, 3*height/4, 130,170,10);
        
      //rectangulo 6, back
        rect(3*width/4, 3*height/4, 130,170,10);
        
         textAlign(CENTER);
         fill(90);
         textSize(20);
         
       //text p1
         text("Mix-killer-Tape", width/4, height/2+10);
         
       //text p2
         text("Scary Dude", width/2, height/2+10);  
         
       //text p3
         text("Cody lightfeet", 3*width/4, height/2+10); 
         
        //text p4
         text("Dick ChunkBlow", width/4, 2*height/2-40);
         
        //text p5
         text("Gostly Earl", width/2, 2*height/2-40);
         
        //text p6
         text("Universal crazy Bus", 3*width/4, 2*height/2-40); 
    }//void 2
    
    
    void grande(){//f= num de figura
        if (mouseX >=width/4-130/2 & mouseX <=width/4+130/2 & mouseY >= height/3-170/2 & mouseY <= height/3+170/2){casete.escala=1;}
          else{casete.escala=.4;}
          
         if (mouseX >=width/2-130/2 & mouseX <=width/2+130/2 & mouseY >= height/3-170/2 & mouseY <= height/3+170/2){sd.escala=1.5;}
          else{sd.escala=.5;}
          
         if (mouseX >= 3*width/4-130/2 & mouseX <= 3*width/4+130/2 & mouseY >= height/3-170/2 & mouseY <= height/3+170/2){nube.escala=1;}
          else{nube.escala=.4;}
          
         if (mouseX >=width/4-130/2 & mouseX <=width/4+130/2 & mouseY >= 3*height/4-170/2 & mouseY <= 3*height/4+170/2){cd.escala=.8;}
           else{cd.escala=.3;} 
           
         if (mouseX >=width/2-130/2 & mouseX <=width/2+130/2 & mouseY >= 3*height/4-170/2 & mouseY <= 3*height/4+170/2){disqu.escala=.8;}
           else{disqu.escala=.3;} 
           
        if (mouseX >=3*width/4-130/2 & mouseX <=3*width/4+130/2 & mouseY >= 3*height/4-170/2 & mouseY <= 3*height/4+170/2){usb.escala=1.4;}
           else{usb.escala=.5;} 
    }


   void selec1(){
        pantalla2();
        casete.casete1();
        sd.sd1();
        nube.nube1();
        cd.cd1();
        disqu.disqu1();
        usb.usb1();
        
           //texto "elegir"
               textAlign(CENTER);
               s = "Jugador 1. Elige tu personaje";
               fill(70);
               textSize(30);
               text(s, width/2, height/9);
               textSize(12);
               text("Usa tu mouse", width/2, height/9+25);
               
               
               
          if (mousePressed & (mouseX >=width/4-130/2 & mouseX <=width/4+130/2 & mouseY >= height/3-170/2 & mouseY <= height/3+170/2)){
              j1=1;
               attk1=casete.attk;
               life1=casete.life;
               l1=life1;
              slc=2;}
            
          if (mousePressed & (mouseX >=width/2-130/2 & mouseX <=width/2+130/2 & mouseY >= height/3-170/2 & mouseY <= height/3+170/2)){
              j1=2;
                attk1=sd.attk;
                life1=sd.life;
                l1=life1;
              slc=2;}
           
           if (mousePressed & (mouseX >= 3*width/4-130/2 & mouseX <= 3*width/4+130/2 & mouseY >= height/3-170/2 & mouseY <= height/3+170/2)){
              j1=3;
                attk1=nube.attk;
                life1=nube.life;
                l1=life1;
                slc=2;}
           
           if (mousePressed & (mouseX >=width/4-130/2 & mouseX <=width/4+130/2 & mouseY >= 3*height/4-170/2 & mouseY <= 3*height/4+170/2)){
              j1=4;
               attk1=cd.attk;
               life1=cd.life;
               l1=life1;
              slc=2;}
            
           if (mousePressed & (mouseX >=width/2-130/2 & mouseX <=width/2+130/2 & mouseY >= 3*height/4-170/2 & mouseY <= 3*height/4+170/2)){
              j1=5;
                attk1=disqu.attk;
                life1=disqu.life;
                l1=life1;
              slc=2;}
             
          if (mousePressed & (mouseX >=3*width/4-130/2 & mouseX <=3*width/4+130/2 & mouseY >= 3*height/4-170/2 & mouseY <= 3*height/4+170/2)){
                j1=6;
                  attk1=usb.attk;
                  life1=usb.life;
                  l1=life1;
                slc=2;}
      } //void  



void selec2(){
  
   pantalla2();
   
   //texto "elegir"
         textAlign(CENTER);
         s = "Jugador 2. Elige tu personaje";
         fill(70);
         textSize(30);
         text(s, width/2, height/9); 
         textSize(12);
         text("Usa tu mouse", width/2, height/9+25);

         if (j1!=1){casete.casete1();
             if (mousePressed & (mouseX >=width/4-130/2 & mouseX <=width/4+130/2 & mouseY >= height/3-170/2 & mouseY <= height/3+170/2)){
             j2=1;
              attk2=casete.attk;
              life2=casete.life;
              l2=life2;
             pantalla=3;}
         }
         if (j1!=2){sd.sd1();
             if (mousePressed & (mouseX >=width/2-130/2 & mouseX <=width/2+130/2 & mouseY >= height/3-170/2 & mouseY <= height/3+170/2)){
              j2=2;
              life2=sd.life;
              attk2=sd.attk;
              l2=life2;
              pantalla=3;}
         }       
         if (j1!=3){nube.nube1();
            if (mousePressed & (mouseX >= 3*width/4-130/2 & mouseX <= 3*width/4+130/2 & mouseY >= height/3-170/2 & mouseY <= height/3+170/2)){
            j2=3;
            life2=nube.life;
            attk2=nube.attk;
            l2=life2;
            pantalla=3;}
         }         
         if (j1!=4){cd.cd1();
            if (mousePressed & (mouseX >=width/4-130/2 & mouseX <=width/4+130/2 & mouseY >= 3*height/4-170/2 & mouseY <= 3*height/4+170/2)){
            j2=4;
            life2=cd.life;
            l2=life2;
            attk2=cd.attk;
            pantalla=3;}
         }
         if (j1!=5){disqu.disqu1();
            if (mousePressed & (mouseX >=width/2-130/2 & mouseX <=width/2+130/2 & mouseY >= 3*height/4-170/2 & mouseY <= 3*height/4+170/2)){
            j2=5;
            life2=disqu.life;
            attk2=disqu.attk;
              l2=life2;
            pantalla=3;}
         }
         if (j1!=6){usb.usb1();
            if (mousePressed & (mouseX >=3*width/4-130/2 & mouseX <=3*width/4+130/2 & mouseY >= 3*height/4-170/2 & mouseY <= 3*height/4+170/2)){
            j2=6;
            life2=usb.life;
            attk2=usb.attk;
            l2=life2;
            pantalla=3;}
         }
         
         
    }   

void pantalla3(){
  image(screen3, 0, 0);
  
  b1=(life1*300)/l1;
  b2=(life2*300)/l2;
  
  rectMode(CENTER);
  noStroke();
  
  fill(220,90);
  rect(2*width/7,height/2,400,400,30);
  rect(5*width/7,height/2,400,400,30);
  textFont(font,20);
  fill(255);
  textAlign(CENTER);
  
        if (j1==1){
        casete.x= 2*width/7;
        casete.y= height/2;
        casete.escala=1.5;
        casete.casete1();
        fill(255);
        text("Mix-the killer-Tape", 2*width/7, height/6);
        }
        if (j1==2){
        sd.x= 2*width/7;
        sd.y= height/2;
        sd.sd1();
        sd.escala=2;
        fill(255);
        text("Scary Dude", 2*width/7, height/6);  
        }
        if (j1==3){
        nube.x= 2*width/7;
        nube.y= height/2;
        nube.escala=1;
        nube.nube1();
        fill(255);
         text("Cloudy lightfeet", 2*width/7, height/6); 
        }
        if (j1==4){
        cd.x= 2*width/7;
        cd.y= height/2;
        cd.escala=1.3;
        cd.cd1();
        fill(255);
        text("Dick ChunkBlow", 2*width/7, height/6);
        }
        if (j1==5){
        disqu.x= 2*width/7;
        disqu.y= height/2;
        disqu.escala=1;
        disqu.disqu1();
        fill(255);
         text("Gostly Earl", 2*width/7, height/6);
        }
        if (j1==6){
        usb.x= 2*width/7;
        usb.y= height/2+height/15;
        usb.escala=2;
        usb.usb1();
        fill(255);
        text("Universal crazy Fred", 2*width/7, height/6); 
        }
        
  //-------
        if (j2==1){
        casete.x= 5*width/7;
        casete.y= height/2;
        casete.escala=1.5;
        casete.casete1();
        fill(255);
        text("Mix-the killer-Tape", 5*width/7, height/6);
        }
        
        if (j2==2){
        sd.x= 5*width/7;
        sd.y= height/2;
        sd.escala=2;
        sd.sd1();
        fill(255);
        text("Scary Dude", 5*width/7, height/6);  
        }
        if (j2==3){
        nube.x= 5*width/7;
        nube.y= height/2;
        nube.escala=1;
        nube.nube1();
        fill(255);
        text("Cloudy lightfeet", 5*width/7, height/6); 
        }
        if (j2==4){
        cd.x= 5*width/7;
        cd.y= height/2;
        cd.escala=1.3;
        cd.cd1();
        fill(255);
        text("Dick ChunkBlow", 5*width/7, height/6);
        }
        if (j2==5){
        disqu.x= 5*width/7;
        disqu.y= height/2;
        disqu.escala=1;
        disqu.disqu1();fill(255);
        text("Gostly Earl", 5*width/7, height/6);
        }
        if (j2==6){
        usb.x= 5*width/7;
        usb.y= height/2+height/15;
        usb.escala=2;
        usb.usb1();
        fill(255);
        text("Universal crazy Fred", 5*width/7, height/6); 
        }
}//pant 3




  void fight(){
           keyCode=0;
           
       if (turno==1){
             pantalla3();
            
              textAlign(CENTER);
              fill(239,237,158);
              textSize(35);
              text("Jugador 1 ", 2*width/7, 11*height/12);
              fill(200);
              textFont(font2, 20);
              text("presiona la tecla F para atacar", 2*width/7, 6*height/7); 
            if(keyPressed && (key=='f'||key=='F') && life2>0){
                keyCode=0;
                if(life2>0)
                {
                life2-=attk1;
                b2-=(life2*300)/l2;
                //println("vida 1 :"+life1+"   vida 2 :"+life2);
                turno=2;
               }
               if(life2<=0){
               turno=3;
               b2=0;}
              }   
      }//if turno1
          
          
       if(turno==2){
                  pantalla3();
                 
                  textAlign(CENTER);
                  fill(239,237,158);
                  textFont(font, 35);
                  text("Jugador 2 ", 5*width/7, 11*height/12);
                  fill(200);
                  textFont(font2, 20);
                  text("presiona K para atacar", 5*width/7, 6*height/7); 
                  
                 if(keyPressed && (key=='k'||key=='K' )) {
                       keyCode=0;
                       if(life1>0){
                          life1-=attk2;
                          b1-=(life1*300)/l1;
                          //println("vida 1 :"+life1+"   vida 2 :"+life2);
                          turno=1;
                       }
                       if(life1<=0){
                           turno=3;
                           b1=0;}
                       }  
               }//if turno 2
       
        if (turno==3){
               if(life1>0 ){win=j1;}
               if(life2>0){win=j2;}
              pantalla=4;
              //println(life1,',',life2,',',win);
        }//turno 3
  }//fight
  
    
 void barra(){
         rectMode(CORNER);
         noStroke();
         fill(10,40);
         rect(width/25, height/7,20,300,10);
         rect(17*width/18, height/7,20,300,10);
         if(b1>=0){
         fill(216,236,255);
         rect(width/25, (height/7)+300, 20, -b1,10);}
         if (b2>=0){
         fill(230,243,144);
         rect(17*width/18, (height/7)+300, 20,-b2,10);}
  }
  
  
          
 void pantalla4(){
       image(screen4, 0, 0);
 
             for(int i=0; i<400; i++){
             fill(random(255),random(200),random(200));
             
                    if(px[i]>1000||px[i]<0){
                    dx[i]*=-1;}
                    
                    if(py[i]>=600||py[i]<=0){
                     dy[i]*=-1; }
                     
                     px[i]+=dx[i];
                     py[i]+=dy[i];
                    ellipse(px[i],py[i],10,10);
               }//FOR
               
               
            
       
             textAlign(CENTER);
             fill(0);
             textFont(font3,80);
             
           if(win==1){
             text("Mix-killer-Tape", 3*width/4, height/2+10);
             casete.x=width/2;
             casete.y=height/2;
             casete.escala=1.5;
             casete.casete1();}
           if( win== 2){
             text("Scary Dude", width/4, height/2+10);
             sd.x=width/2;
             sd.y=height/2;
             sd.escala=2;
             sd.sd1();}
           if( win==3){
             text("Cloudy lightfeet", 3*width/4, height/2+10);
             nube.x=width/2;
             nube.y=height/2;
             nube.escala=1;
             nube.nube1();}
           if (win==4){
             text("Dick ChunkBlow", width/4, 2*height);
             cd.x=width/2;
             cd.y=4*height/9;
             cd.escala=1.2;
             cd.cd1();}
           if (win==5){
              text("Gostly Earl", width/4, 2*height/2-40);
             disqu.x=width/2;
             disqu.y=height/2;
             disqu.escala=1;
             disqu.disqu1();}
           if(win==6){
             text("Universal crazy Bus", 3*width/4, 2*height/2-40);
             usb.x=width/2;
             usb.y=5*height/9;
             usb.escala=2;
             usb.usb1(); }
       
       //"ganador"
       fill(40,36,78);
       textAlign(CENTER,CENTER);
       textFont(font,50);
       text("FELICIDADES",width/2,height/10);
       
       fill(77,143,193);
       textSize(20);
       text("HAS GANADO",width/2,height/6);
       
       //Botón
       rectMode(CENTER);
       noStroke();
       fill(220,128,128,96);
       rect(width/2,9*height/10,100,40,10);
       
       textFont(font2,20);
       fill(104,62,62);
       textAlign(CENTER,CENTER);
       text("INICIO",width/2,9*height/10);
       
       
       //pantalla1-->pantalla2
         if(mousePressed & (mouseX >= width/2-50 & mouseX <= width/2+50)&(mouseY>= 9*height/10-20 & mouseY <= 9*height/10+20)){
           pantalla=1;
           reset();
          } //if 
 }    //pantalla4    
         
    void reset(){
      background(9,22,34);
       keyCode=0;
           pantalla=1;
            turno=1;
            personaje=0;
            cx1=0;
            cx2=0;
            cy1=0;
            cy2=0;
            f=0;
            slc=1;
            j1=0;
            j2=0;
            sz=0;
            attk1=0;
            attk2=0;
            life1=0;
            life2=0;
            l1=0;
            l2=0;
            win=0;
            b1=300;
            b2=300;
                  
             casete.x= width/4;
             casete.y= height/3;
             casete.escala=.4;
              
             sd.x=width/2;
             sd.y=height/3;
             sd.escala=1.5;
           
             nube.x=3*width/4;
             nube.y=height/3;
             nube.escala=.3;
             
             cd.x=width/4;
             cd.y=3*height/4;
             cd.escala=.3;
             
             disqu.x=width/2;
             disqu.y=3*height/4;
             disqu.escala=.3;
             
             usb.x=3*width/4;
             usb.y=3*height/4;
             usb.escala=1.4;
    }
