## Optimization

```{r, echo = FALSE, eval=TRUE}
library(nleqslv)
library(optimx)
```

```{r, echo=FALSE, eval=TRUE}
szescienne1<-function(a,b,c,d){
  h<-as.complex(as.complex(27*(a^2)*(d^2) + (4*(b^3) - (18*a*b*c))*d + (4*a*(c^3)) - (b^2 * c^2))^(1/2))
  i<-(2*3^(3/2))*a^2
  j<-27*(a^2)*d - (9*a*b*c) + 2*(b^3)
  k<-54*a^3
  e<-as.complex(h/i - j/k)
  f<-(3*a*c - b^2)
  g<-(9*a^2)*((h/i - j/k)^(1/3))
  return( e^(1/3) - f/g - b/(3*a) )
}


glowna<-function(arg){

wyniki<-0*c(1:21)  

################################################################
#Deklaracje wartości parametrów i startowych poziomów zmiennych#
################################################################

alpha<-0.4
beta<-0.1   
gamma<-arg[1]
delta<-arg[2]
theta<-arg[3]
r<-arg[4]
chi<-arg[5] 
y1<-1
y2<-y1*(1+gamma)
y3<-y2*(1+gamma)
y4<-y3*(1+gamma)
y5<-y4*(1+gamma)
b1<-arg[6]*y1
b2<-arg[6]*y2
b3<-arg[6]*y3
c1<-arg[7]*y1
c2<-arg[7]*y2
k3<-arg[8]*y3
upsilon<-arg[9]

u1<-upsilon*y1
U1<-upsilon*y1
u2<-upsilon*y2
U2<-upsilon*y2
u3<-upsilon*y3
U3<-upsilon*y3
u4<-upsilon*y4
U4<-upsilon*y4
u5<-upsilon*y5
U5<-upsilon*y5

############################################
# Rozwiązanie metodą Karusha-Kuhna-Tuckera #
############################################

phi0<-(-1-r)
phi1<-(-(y5+u5)/((chi+r)*3*(y3+u3)) -(1+r))
phi2<-((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3-r*b3)/(y3+u3)) - (1+r)*(b3+ theta*u3+r*b3-y3) + y4)
phi3<-(-3*(y3+u3)*(chi+r)/(1+3*(y3+u3)*(chi+r)/(y4+u4))/(y4+u4))
phi4<-(
  -3*(y3+u3)/(1+3*(y3+u3)*(chi+r)/(y4+u4))
  *(((chi+r)*(b3+ theta*u3 + r*b3 - y3))/(y4+u4) 
    - 1/3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2)) - 1/3*(y3-r*b3)/(y3+u3))
)
phi5<-(alpha*(((y4+u4)*(3*(y3+u3)))/((chi+r)*(3*(y3+u3))+y4+u4)))
phi6<-(alpha*beta*
         ((((-(y5+u5)/(chi+r)/3*(1/(y3+u3) + r/(y4+u4))) - (1+r))*(((y4+u4)*(3*(y3+u3)))/((chi+r)*(3*(y3+u3))+y4+u4))) - (-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta - r)*((y4+u4)/(chi+r))))
phi7<-((-delta-r) - ((y5+u5)/(chi+r)/3*(phi3/(y3+u3) + r*(1+phi3)/(y4+U4))) - (1+r)*phi3)
phi8<-(
  ((y5+u5)/(chi+r)/3)
  * ((y3-phi4-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4 - r*(b3 + theta*u3 + phi4 + r*b3 - y3))/(y4+u4)))
  -(((1+r)*(b3+theta*u3 + phi4 + r*b3 - y3)))
  +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3) + u4)
)
phi9<-(
  beta*(1-alpha)*(1-alpha)*(((-(y5+u5)/(chi+r)/3*(1/(y3+u3) + r/(y4+u4))-(1+r)))*(((y4+u4)*(3*(y3+u3)))/((chi+r)*(3*(y3+u3))+y4+u4)) - (-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta-r)*((y4+u4)/(chi+r)))
)
phi10<-((1-delta)*(1-alpha)) + (1-alpha)*(phi0 + phi3*phi1) - r*(1+phi3)*(1-alpha)*((y5+u5)/(chi+r)/3)/(y4+u4)
phi11<-(
  (1-delta)*((1-delta)*k3 + (1+theta)*u3)
  +((1-alpha)*(phi4*phi1 + phi2 + (y5+u5)*(y4-r*(b3 + theta*u3 + phi4 +r*b3 - y3))/(chi+r)/3/(y4+u4)) 
    - alpha*(1-delta)*((1-delta)*k3 + (1+theta)*u3) - (theta+alpha)*u4) 
  + (1+theta)*u4
)
phi12<-((1-alpha)*((y4+u4)/(chi+r)))
phi13<-((1-delta)*k3 + (1+theta)*u3)

par_a<-(
  (phi5*phi7+phi3*phi6)*phi10 +
    (phi9 - phi10*phi12)*phi3*phi7
)
par_b<-(
  (phi5*phi8 + phi4*phi6)*phi10 +
    (phi5*phi7+phi3*phi6)*(phi10*phi13 + phi11) +
    (phi9*phi13 - phi11*phi12)*phi3*phi7 +
    (phi9 - phi10*phi12)*(phi3*phi8 + phi4*phi7) 
)
par_c<-(
  (phi5*phi8 + phi4*phi6)*(phi10*phi13 + phi11) +
    (phi9*phi13 - phi11*phi12)*(phi3*phi8 + phi4*phi7) +
    (phi9 - phi10*phi12)*phi4*phi8 +
    (phi5*phi7+phi3*phi6)*phi11*phi13
)
par_d<-(
  (phi5*phi8 + phi4*phi6)*phi11*phi13 +
    (phi9*phi13 - phi11*phi12)*phi4*phi8
)

############################################
#   Rozwiązanie  poprawne                  #
############################################


x<-szescienne1(par_a, par_b, par_c, par_d)
#x

i3<-as.numeric(x)
u3<-U3
u4<-U4


############################################
# Znając i3 oraz napięty IWZ, szukamy c3   #
############################################

rozw_c<-function(rozw2){
  return( ((y4+u4)/(chi+r)/
             3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2) + (y3-rozw2-r*b3)/(y3+u3)))
          - b3 - (1+theta)*u3 - i3 - r*b3 + u3 + y3 - rozw2)
}

c3<-c(nleqslv(c(0.5), rozw_c)$x)
z3<-(1+theta)*u3 + i3 + c3 + r*b3 - u3 - y3
b4<-b3+z3

c4<-(
  (((alpha*(y5+u5)/(chi+r)*1/3)
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
   *(y3-c3 - r*b3)/(y3+u3))
  +(((alpha*(y5+u5)/(chi+r)*1/3)
     /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
    *(((y2-c2 - r*b2)/(y2+u2))+((y4 - r*(b3 + theta*u3 + i3 + c3 + r*b3 - y3))/(y4+u4))))
  -(alpha*((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3))
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
  +(alpha*(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
)

#c4<-(
#alpha*(phi +(y5+u5)/(chi+r)*1/3*((y4 - r*(b3 + theta*u3 + i3 + c3 + r*b3 - y3))/(y4+u4)) + (1-delta)*k4 + u4 )
#/(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4))
#  )

k4<-(1-delta)*k3+(1+theta)*u3+i3
k5<-(
  (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 + 
    (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4)) 
               -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
)
i4<-k5-(1-delta)*k4-(1+theta)*u4

# cat(c3, u3, i3)
# cat(c4, u4, i4)

######################################################
#   Sprawdzenie                                      #
######################################################

 phi5/(i3*phi3 + phi4) + phi6/(i3*phi7 + phi8) + phi9/(i3*phi10 + phi11) - phi12/(i3 + phi13)


############################################
# Sprawdzenie z warunkami I rzędu          #
############################################

lewa<-(
  +(alpha/c3) 
  +(alpha*beta*
      ((-(y5+u5)/(chi+r)/3*(1/(y3+u3) + r/(y4+u4))) - (1+r))
    /(
      ((y5+u5)/(chi+r)/3)
      * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
      -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
      +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    )
  ) 
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*((1/(y3+u3)) + (r/(y4+u4)))-(1+r))/k5
)  

prawa<-(
  +(1-alpha)/k4 
  +(beta*alpha*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta - r))
  /(
    ((y5+u5)/(chi+r)/3)
    * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
    -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
    +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
  )
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta -r)/k5
)
pomo<-(
  -lewa/((chi+r)/(y4+u4) + 1/(3*(y3+u3)))
  +prawa/((chi+r)/(y4+u4))
)

pomo

############################################
# Deklaracja funkcji użyteczności          #
############################################

uzyt<-function(p){
  c3<-p[1]
  u3<-p[2]
  i3<-p[3]

  z3<-(1+theta)*u3 + i3 + c3 + r*b3 - u3 - y3
  b4<-b3+z3
  k4<-(1-delta)*k3+(1+theta)*u3+i3

  u4<-U4
  c4<-(
    (((alpha*(y5+u5)/(chi+r)*1/3)
      /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
     *(y3-c3 - r*b3)/(y3+u3))
    +(((alpha*(y5+u5)/(chi+r)*1/3)
       /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
      *(((y2-c2 - r*b2)/(y2+u2))+((y4 - r*b4)/(y4+u4))))
    -(alpha*((1+r)*b4)
      /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
    +(alpha*(y4 + (1-delta)*k4 + u4)
      /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
  )
  k5<-(
    (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 +
      (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4))
                 -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
  )
  i4<-k5-(1-delta)*k4-(1+theta)*u4

  kara<-0*c(1:6)
  kara[1]<-(c3<0)*9999 + (c4<0)*9999
  kara[2]<-(i3<0)*9999 + (i4<0)*9999
  kara[3]<-(u3<0)*9999 + (u3>U3)*9999
  kara[4]<-((c3+r*b3)>y3)*9999
  kara[5]<-(((chi+r)*b4)/(y4+u4) > 1/3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2) + (y3-c3-r*b3)/(y3+u3)))*9999
  kara[6]<-((c4+r*b4)>y4)*9999
  return(-(- abs(sum(kara)*which.max(abs(c(c3,c4,u3,i3,i4))))
           + alpha*log(c3) + (1-alpha)*log(k4) + beta*alpha*log(c4)
           + beta*(1-alpha)*log(k5)))
}


####################################################
# Podsumowanie rozwiązania z równania sześciennego #          
####################################################
# 
# cat(c3, u3, i3)
# cat(c4, u4, i4)
# uzyt(c(c3-0.000001,u3,i3))
# 

 wyniki[1:7]<-c(c3, u3, i3, c4, u4, i4, uzyt(c(c3-0.000001,u3,i3)))


############################################
# Rozwiązanie metodami iteracyjnymi        #
############################################

metody<-c("BFGS", "CG", "Nelder-Mead", "L-BFGS-B", "nlm", "nlminb", "spg", "ucminf", "newuoa", "bobyqa", "nmkb", "hjkb")

uz<-0*c(1:12)

roz<-function(rozw){
  wsp<-as.matrix(coef(optimx (rozw, uzyt, method=metody)))
  uz<-apply(wsp, 1, uzyt)
  rozw2<-wsp[which.min(uz),]
  #print(summary(optimx (rozw, uzyt, method=metody)))
  return(as.vector(rozw2))
}

konw<-function(rozw){
  maks<-uzyt(rozw)
  rozw2<-rozw
  zatrzymaj<-0
  while (zatrzymaj==0){
    rozw2<-roz(rozw2)
    if ((uzyt(rozw2) - maks)>-0.0001){
      zatrzymaj<-1
      #print(summary(optimx (rozw2, uzyt, method=metody)))
    }
    maks<-uzyt(rozw2)
  }
  return(roz(rozw2))
}

p<-0*c(1:3)
rozw<-c(0.6, 0.1, 0.1)
p<-konw(rozw)

p[1]->c3
p[2]->u3
p[3]->i3

u4<-U4
c4<-(
  (((alpha*(y5+u5)/(chi+r)*1/3)
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
   *(y3-c3 - r*b3)/(y3+u3))
  +(((alpha*(y5+u5)/(chi+r)*1/3)
     /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
    *(((y2-c2 - r*b2)/(y2+u2))+((y4 - r*(b3 + theta*u3 + i3 + c3 + r*b3 - y3))/(y4+u4))))
  -(alpha*((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3))
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
  +(alpha*(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
)
k4<-(1-delta)*k3+(1+theta)*u3+i3
k5<-(
  (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 + 
    (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4)) 
               -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
)
i4<-k5-(1-delta)*k4-(1+theta)*u4
z3<-(1+theta)*u3 + i3 + c3 + r*b3 - u3 - y3
b4<-b3+z3

############################################
# Sprawdzenie z warunkami I rzędu          #
############################################

lew<-(
  +(alpha/c3) 
  +(alpha*beta*
      ((-(y5+u5)/(chi+r)/3*(1/(y3+u3)+r/(y4+u4))) - (1+r))
    /(
      ((y5+u5)/(chi+r)/3)
      * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
      -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
      +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    )
  ) 
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*((1/(y3+u3))+(r/(y4+u4)))-(1+r))/k5
)  

praw<-(
  +(1-alpha)/k4 
  +(beta*alpha*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta - r))
  /(
    ((y5+u5)/(chi+r)/3)
    * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
    -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
    +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
  )
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta -r)/k5
)

spr<-(
  -lew/((chi+r)/(y4+u4) + 1/(3*(y3+u3)))
  +praw/((chi+r)/(y4+u4))
)
spr

####################################################
# Podsumowanie rozwiązania metodami iteracyjnymi   #          
####################################################

# cat(c3, u3, i3)
# cat(c4, u4, i4)
# uzyt(c(c3-0.00000001,u3,i3))

wyniki[8:14]<-c(c3, u3, i3, c4, u4, i4, uzyt(c(c3-0.000001,u3,i3)))

spr3<-function(pomoc){
  c3<-pomoc
  u3<-U3
  u4<-U4
  b4<-(y4+u4)/(chi+r)/3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2) + (y3-c3-r*b3)/(y3+u3))
  z3<-b4-b3
  i3<- z3 - (1+theta)*u3 - c3 - r*b3 + u3 + y3
  c4<-(
    (((alpha*(y5+u5)/(chi+r)*1/3)
      /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
     *(y3-c3 - r*b3)/(y3+u3))
    +(((alpha*(y5+u5)/(chi+r)*1/3)
       /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
      *(((y2-c2 - r*b2)/(y2+u2))+((y4 - r*(b3 + theta*u3 + i3 + c3 + r*b3 - y3))/(y4+u4))))
    -(alpha*((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3))
      /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
    +(alpha*(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
      /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
  )
  k4<-(1-delta)*k3+(1+theta)*u3+i3
  k5<-(
    (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 +
      (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4))
                 -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
  )
  i4<-k5-(1-delta)*k4-(1+theta)*u4

  lewa<-(
    +(alpha/c3)
    +(alpha*beta*
        ((-(y5+u5)/(chi+r)/3*(1/(y3+u3)+r/(y4+u4))) - (1+r))
      /(
        ((y5+u5)/(chi+r)/3)
        * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
        -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
        +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
      )
    )
    +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*((1/(y3+u3))+(r/(y4+u4)))-(1+r))/k5
  )

  prawa<-(
    +(1-alpha)/k4
    +(beta*alpha*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta - r))
    /(
      ((y5+u5)/(chi+r)/3)
      * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
      -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
      +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    )
    +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta -r)/k5
  )
  pomo<-(
    -lewa/((chi+r)/(y4+u4) + 1/(3*(y3+u3)))
    +prawa/((chi+r)/(y4+u4))
  )
  return(c(pomo))
}


##############################################
# Rozwiązanie bazujące na warunkach I rzędu  #  
##############################################



rozw<-c(nleqslv(c(0.5), spr3)$x)
rozw[]<-rozw[]
b4<-(y4+u4)/(chi+r)/3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2) + (y3-rozw-r*b3)/(y3+u3))

z3<-b4-b3
i3<-( z3 - (1+theta)*u3 - rozw - r*b3 + u3 + y3)
p<-c(rozw-0.000001, u3, i3)

c3<-p[1]
u3<-p[2]
i3<-p[3]

u4<-U4
c4<-(
  (((alpha*(y5+u5)/(chi+r)*1/3)
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
   *(y3-c3 - r*b3)/(y3+u3))
  +(((alpha*(y5+u5)/(chi+r)*1/3)
     /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
    *(((y2-c2 - r*b2)/(y2+u2))+((y4 - r*(b3 + theta*u3 + i3 + c3 + r*b3 - y3))/(y4+u4))))
  -(alpha*((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3))
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
  +(alpha*(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
)
k4<-(1-delta)*k3+(1+theta)*u3+i3
k5<-(
  (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 + 
    (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4)) 
               -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
)
i4<-k5-(1-delta)*k4-(1+theta)*u4


####################################################
# Sprawdzenie                                      #          
####################################################

lewa<-(
  +(alpha/c3) 
  +(alpha*beta*
      ((-(y5+u5)/(chi+r)/3*(1/(y3+u3)+r/(y4+u4))) - (1+r))
    /(
      ((y5+u5)/(chi+r)/3)
      * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
      -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
      +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    )
  ) 
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*((1/(y3+u3))+(r/(y4+u4)))-(1+r))/k5
)  

prawa<-(
  +(1-alpha)/k4 
  +(beta*alpha*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta - r))
  /(
    ((y5+u5)/(chi+r)/3)
    * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
    -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
    +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
  )
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta -r)/k5
)
pomo<-(
  -lewa/((chi+r)/(y4+u4) + 1/(3*(y3+u3)))
  +prawa/((chi+r)/(y4+u4))
)
pomo

####################################################
# Podsumowanie rozwiązania z warunków I rzędu      #          
####################################################

# cat(c3, u3, i3)
# cat(c4, u4, i4)
# uzyt(c(c3-0.00000001,u3,i3))
# uzyt(c(c3,u3,i3))

wyniki[15:21]<-c(c3, u3, i3, c4, u4, i4, uzyt(c(c3-0.000001,u3,i3)))

return(wyniki)}


######################################################
# Analiza wyników                                    #
######################################################

macierz<-matrix(0*c(1:(23*10)), nrow=100, ncol=23)

wektor<-0*c(1:100)
for (iter1 in 1:10){
  for (iter2 in 1:10){
    wektor[iter2+ (iter1-1)*10]<-(0.02*iter1+0.28)    
  }
}

macierz[,1]<-as.vector(wektor)
macierz[,2]<-0.05*c(1:10)
macierz

for (iter2 in 1:100){
 macierz[iter2,3:23]<-glowna(macierz[iter2,1], macierz[iter2,2])  
 print(iter2)
}
macierz
View(macierz)
setwd("C:\\Dysk\\Nowe\\JST\\Skrypty w R")
write.csv(macierz, "macierz2.csv")

######################################################
# Analiza wrażliwości                                #
######################################################

gamma_arg<-0.043
delta_arg<-0.049
theta_arg<-0.62
r_arg<-0.038
chi_arg<-0.2
b_arg<-0.32
c_arg<-0.92
k_arg<-2.06
upsilon_arg<-0.25

library(triangle)

# rlnorm(1, f.ln.m, f.ln.sd)
# rgamma(1, f.g.s, f.g.r)
# rchisq(1, f.chi.df)
# rt(1, df)*sc + loc
# rnorm(1, f.mean, f.sd)
# rtriangle(1, low,up,mean)


losowanie<-function(){
gamma_arg<-rt(1, 2.919)*0.039 + 0.044
delta_arg<-(-0.15 + rgamma(1, 4.76, 21.213))
theta_arg<-rtriangle(1, 0.43, 1, 0.62)
r_arg<-rgamma(1, 6.417, 152.5)
chi_arg<-rgamma(1, 2.325, 9.608)
if (runif(1)<0.038){
  b_arg<-0}else{
  b_arg<-rgamma(1, 2.405, 6.984)
}
c_arg<-rt(1, 4.52)*0.045 + 0.9
k_arg<-rt(1, 6.58)*0.36 + 2.06
upsilon_arg<-rtriangle(1, 0.2, 0.35, 0.25)

arg_arg<-c(gamma_arg, delta_arg, theta_arg, r_arg, chi_arg, b_arg, c_arg, k_arg, upsilon_arg)
return(arg_arg)
}

n_iter<-400
macierz<-matrix(0*c(1:30), nrow=n_iter, ncol=30)

for (iter in 1:n_iter){
  losowanko<-losowanie()
  macierz[iter,1:9]<-losowanko
  macierz[iter,10:30]<-glowna(losowanko)  
  print(iter)
}
setwd("C:\\Dysk\\Nowe\\JST\\Skrypty w R\\Wyniki październik 2017")
write.csv(macierz, "wyniki9.csv")
```
