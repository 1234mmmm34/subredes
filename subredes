/*PROGRAMA QUE CALCULA SUBREDES Y SU MÃSCARA, SEGÚN IP Y HOST/SUBREDES DESEADOS
Urquidy Galaviz Mariana Joseline, 4to semestre.
*/     //cin.ignore().get();
#include<iostream>
#include<math.h>
#include<bitset>
#include<fstream>
using namespace std;

int main(){
	ios_base::sync_with_stdio(false); 
	int oc2=0,oc3=0,oc4=0,oc1=0,p=0,occ=0,var2=0,var3=0,var4=0,clase=0,vec[4],k=1,var=7;
    long int host=0,sub=0;
    vec[0]=0; vec[1]=0; vec[2]=0; vec[3]=0;
    
    //ABRIMOS ARCHIVO TXT
    ofstream file;
    file.open("C:/nose/ARCHIVO.txt");
    
	cout<<"proporcione ip: "<<"\n";
	cin>>oc1; cin.ignore(1); cin>>oc2; cin.ignore(1); cin>>oc3; cin.ignore(1); cin>>oc4;
	cout<<"CALCULAR POR MEDIO DE: "<<"\n";
	cout<<"<1> # de HOST "<<"\n";
	cout<<"<2> # de SUBREDES "<<"\n";
	cin>>var3;
	switch(var3){
		case 1:	cout<<"proporcione numero de host: \n"; break;
		case 2:	cout<<"proporcione numero de subredes: \n"; break; }
	cin>>host; cout<<"\n";
	
    occ=oc1;
    
	if(oc1>=0 && oc1<=127){oc1=24; clase=1; }
    else if(oc1>=128 && oc1<=191){oc1=16; clase=2; }
	else{oc1=8; clase=3; }

	while(pow(2,p)<host){ p++; }
    
    //guarda el nÃºmero de subredes
	sub=pow(2,(oc1-p));
	//guarda el nÃºmero de host x subred
	host=pow(2,p);
	
    if(var3==2){ var2=host; host=sub; sub=var2; p=oc1-p; }
	
	var3=0; var2=0;

	//CÃLCULO DE LA MASCARA DE SUBRED
	for(int j=1;j<=(24-p);j++){ vec[k]+=pow(2,var); var--; if(var==-1){ var=7; k++;} }
	cout<<"MASCARA DE SUBRED: 255."<<vec[1]<<"."<<vec[2]<<"."<<vec[3]<<"/"<<32-p<<"\n";
	
	cout<<"MASCARA DE SUBRED (BINARIO): 11111111";
	for(int j=1;j<=3;j++){bitset<8> var(vec[j]); cout<<"."<<var;} cout<<"\n";
    
    var4=host-1;
    
    //CÃLCULO DE RANGOS
    if(host>256){var3=((host-1)/256); var4=255;}
    if(var3>256){var3=var3/256; var2=var3; var3=255;}
	
	cout<<"CANTIDAD DE SUBREDES: "<<sub<<"\n";	
	cout<<"CANTIDAD DE HOST: "<<host<<"\n";
	
     oc1=occ; oc4=-1; vec[0]=1; 
     if(host<3){vec[0]=0;}
     host=1;
	//+++++++++++++++++++++++IMPRESIÓN Y CÁLCULO DE SUBREDES+++++++++++++++++++++++++++++++++++
	for(int i=0;i<sub;i++){

    cout<<i+1<<"  "<<oc1<<"."<<oc2<<"."<<oc3<<"."<<oc4+host<<"     "; 
    cout<<oc1<<"."<<oc2<<"."<<oc3<<"."<<oc4+host+vec[0]<<" -- ";
    
    oc4+=var4+1; //if(oc4>255){  oc4=var4; } 
	if(oc4==255 && clase<3){ oc3+=var3; }
    if(oc3==255 && clase<2){ oc2+=var2; } 
	
    cout<<oc1<<"."<<oc2<<"."<<oc3<<"."<<oc4-vec[0]<<"     ";
	cout<<oc1<<"."<<oc2<<"."<<oc3<<"."<<oc4<<"\n"; 
	
    if(oc4==255 && clase<3){oc4=-1; oc3++;}
    if(oc3>255 && clase<3){/*oc4=-1;*/ oc3=0; oc2++; }
    
	} return 0; }
