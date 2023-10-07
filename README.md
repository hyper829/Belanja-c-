#include <iostream>

using namespace std;

int main(int argc, char** argv) {
	
	double b,a,diskon,kembalian;
    
	
		cout<<"Masukan Harga Total Belanja :";
		cin >> a;
		
		if(a>499999){
		   diskon = a-(a*0.10);
		   cout<<"Anda Mendapatkan Diskon :"<< diskon <<endl;
		   cout<<"Uang Di Terima :"<<endl;
		   cin>>b;
		   kembalian =diskon-b;
		   cout<<"Uang Kembalian :"<<kembalian<<endl;
	    }
     

	return 0;
}
