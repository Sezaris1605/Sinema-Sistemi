import java.util.Scanner;

public class SinemaSistemi {
    static String[] filmler = new String[10];
    static String[] filmTurleri = new String[10];
    static int[] filmSureleri = new int[10];
    static int filmSayisi = 0;

    static String[] musteriler = new String[20];
    static String[] musterilerEmail = new String[20];
    static int musteriSayisi = 0;

    static int[][] biletler = new int[20][10]; // biletler[musteri][film] = 1 ise bilet alinmis

    static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int secim;
        do {
            System.out.println("\n--- SINEMA MUSTERI KAYIT SISTEMI ---");
            System.out.println("1. Film Ekle");
            System.out.println("2. Musteri Ekle");
            System.out.println("3. Bilet Olustur");
            System.out.println("4. Filmleri Listele");
            System.out.println("5. Musterileri Listele");
            System.out.println("6. Biletleri Listele");
            System.out.println("0. Cikis");
            System.out.print("Seciminiz: ");
            secim = scanner.nextInt();
            scanner.nextLine(); // dummy read

            switch (secim) {
                case 1 -> filmEkle();
                case 2 -> musteriEkle();
                case 3 -> biletOlustur();
                case 4 -> filmleriListele();
                case 5 -> musterileriListele();
                case 6 -> biletleriListele();
                case 0 -> System.out.println("Cikiliyor...");
                default -> System.out.println("Gecersiz secim. Tekrar deneyin.");
            }
        } while (secim != 0);
    }

    static void filmEkle() {
        if (filmSayisi >= 10) {
            System.out.println("Maksimum film sayisina ulasildi.");
            return;
        }
        System.out.print("Film adi: ");
        filmler[filmSayisi] = scanner.nextLine();

        System.out.print("Sure (dk): ");
        filmSureleri[filmSayisi] = scanner.nextInt();
        scanner.nextLine(); // dummy read

        System.out.print("Tur: ");
        filmTurleri[filmSayisi] = scanner.nextLine();

        filmSayisi++;
        System.out.println("Film basariyla eklendi.");
    }

    static void musteriEkle() {
        if (musteriSayisi >= 20) {
            System.out.println("Maksimum musteri sayisina ulasildi.");
            return;
        }
        System.out.print("Musteri adi: ");
        musteriler[musteriSayisi] = scanner.nextLine();

        System.out.print("Email: ");
        musterilerEmail[musteriSayisi] = scanner.nextLine();

        musteriSayisi++;
        System.out.println("Musteri basariyla eklendi.");
    }

    static void biletOlustur() {
        if (musteriSayisi == 0 || filmSayisi == 0) {
            System.out.println("Once film ve musteri eklenmeli.");
            return;
        }

        System.out.println("Musteriler:");
        for (int i = 0; i < musteriSayisi; i++) {
            System.out.println(i + ". " + musteriler[i] + " - " + musterilerEmail[i]);
        }
        System.out.print("Musteri numarasi secin: ");
        int musteriIndex = scanner.nextInt();

        System.out.println("Filmler:");
        for (int i = 0; i < filmSayisi; i++) {
            System.out.println(i + ". " + filmler[i] + " (" + filmTurleri[i] + ", " + filmSureleri[i] + "dk)");
        }
        System.out.print("Film numarasi secin: ");
        int filmIndex = scanner.nextInt();

        if (biletler[musteriIndex][filmIndex] == 1) {
            System.out.println("Bu musteri zaten bu filme bilet almis.");
        } else {
            biletler[musteriIndex][filmIndex] = 1;
            System.out.println("Bilet basariyla olusturuldu.");
        }
    }

    static void filmleriListele() {
        System.out.println("\n--- Film Listesi ---");
        for (int i = 0; i < filmSayisi; i++) {
            System.out.println((i + 1) + ". " + filmler[i] + " | Tur: " + filmTurleri[i] + " | Sure: " + filmSureleri[i] + " dk");
        }
    }

    static void musterileriListele() {
        System.out.println("\n--- Musteri Listesi ---");
        for (int i = 0; i < musteriSayisi; i++) {
            System.out.println((i + 1) + ". " + musteriler[i] + " | Email: " + musterilerEmail[i]);
        }
    }

    static void biletleriListele() {
        System.out.println("\n--- Bilet Listesi ---");
        for (int i = 0; i < musteriSayisi; i++) {
            System.out.print(musteriler[i] + ": ");
            boolean biletVar = false;
            for (int j = 0; j < filmSayisi; j++) {
                if (biletler[i][j] == 1) {
                    System.out.print(filmler[j] + ", ");
                    biletVar = true;
                }
            }
            if (!biletVar) {
                System.out.print("Henuz bilet alinmamis.");
            }
            System.out.println();
        }
    }
}
