# ATM

package atm;

import java.util.Scanner;

public class main {

	public static void main(String[] args) {
		
		String kullaniciAdi, sifre; 
		
		Scanner input = new Scanner(System.in);
		int girisHakki = 3;
		int bakiye = 1500;
		int secim, miktar;
		
		while (girisHakki > 0) {
			System.out.println("Kullanici adiniz:");
			kullaniciAdi = input.nextLine();
			System.out.println("Sifreniz:");
			sifre = input.nextLine();
			
			if (kullaniciAdi.equals("gamzedelil") && sifre.equals("gamze123")) {
				System.out.println("X Bankasina Hosgeldiniz!");
				System.out.println("1-Para Yatirma\n"
						+ "2-Para Cekme\n"
						+ "3-Bakiye Sorgulama\n"
						+ "4-Cikis Yap");
				System.out.println("Yapmak istediginiz islemi secin:");
				secim = input.nextInt();
					
				switch (secim) {
				case 1: 
					System.out.println("Yatirmak istediginiz miktar:");
					miktar = input.nextInt();
					bakiye += miktar;
					System.out.println("Yeni bakiye:" +bakiye);
					break;
					
				case 2: 
					System.out.println("Cekmek istediginiz miktar:");
					miktar = input.nextInt();
					if(miktar>bakiye) {
						System.out.println("Bakiye yetersiz.");
					}
					else {
						bakiye -= miktar;
					}
					System.out.println("Yeni bakiye:" +bakiye);
					break;
					
				case 3: 
					System.out.println("Bakiyeniz:" +bakiye);
					break;
				
					
				case 4: 
					System.out.println("Cikis Yaptiniz.");
					break;		
		}	
			break;	
	  }
			else { 
				girisHakki--;
				System.out.println("Kullanici adiniz veya sifreniz hatali. Lutfen tekrar deneyiniz. Kalan giris hakkiniz:" +girisHakki);
			
			}
			
    }
		if(girisHakki == 0) { 
			System.out.println("Hesabiniz bloke olmustur. Bankayla iletisime geciniz.");
		}
  }	
}
