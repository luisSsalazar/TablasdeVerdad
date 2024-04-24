#include <iostream>
#include <cmath>
using namespace std;
int  menu(){
    int opcion;
    cout<<"Bienvenido al generador de tablas de verdad!\nQue desea hacer?:\n"<<endl;
    cout<<"1. Negacion\n2.Interseccion\n3.Disyuncion\n4.Condicional\n5. Bicondicional"<<endl;
    cin>>opcion;
    return opcion;}

int prop(){
    int prop[100][100];
    int a,b,c,d,e,f,n;
    cout<<"Cuantas proposiciones posee su analisis?"<<endl;
    cin>>a;
        /*do{cout<<"Ingrese un numero de proposiciones valido (0-4)";
                cin>>a;
                }while(((a>1)&&(a<4)));*/
    //Estableciendo la cantidad de ceros y unos a generarse
    b=pow(2,a);
    c=b/2;
    d=c/2;
    e=c+d;
    f=d/2;
    //creando la matriz que contiene a las proposiciones
    for(int i=0;i<b;i++){
        for(int j=0;j<100;j++){
            //crenaod la primera proposicion
            for(int i=0;i<c;i++){
                prop[i][0]=true;}
                for(int i=c;i<b;i++){
                    prop[i][0]=false;}
        //creando la segunda proposicion
            for(int i=0;i<d;i++){
                prop[i][1]=true;}
                for (int i=d;i<c;i++){
                    prop [i][1]=false;}
                    for(int i=c;i<e;i++){
                        prop[i][1]=true;}
                        for(int i=e;i<b;i++){
                            prop[i][1]=false;}
        //creando la tercera proposicion OJOOOOO= funciona con 4 propociosiones, no con 3
            for (int i=0;i<f;i++){
                prop [i][2]=true;}
                for(int i=f;i<d;i++){
                    prop [i][2]=false;}
                    for(int i=d;i<(d+f);i++){
                         prop [i][2]=true;}
                         for(int i=(d+f);i<c;i++){
                             prop [i][2]=false;}
                             for(int i=c;i<(c+f);i++){
                                 prop [i][2]=true;}
                                 for(int i=(c+f);i<(c+f+f);i++){
                                     prop [i][2]=false;}
                                     for(int i=(c+f+f);i<(c+d+f);i++){
                                         prop [i][2]=true;}
                                         for(int i=(c+d+f);i<b;i++){
                                             prop [i][2]=false;}
        //creando la ultima proposicion
            for(int i=0;i<b;i=i+2){
                 prop [i][3]=true;}
                 for(int i=1;i<b;i=i+2){
                    prop [i][3]=false;}
            }
}

  //imprimiendo en pantalla la matriz que contiene las proposiciones
        for(int i=0;i<b;i++){
            for(int j=0;j<a+1;j++){
                cout<<prop[i][j];
                cout<<" ";}
                cout<<endl;}
                cout<<"p q r s";
}

int main (){
    menu();
    prop();
    return 0;
}
